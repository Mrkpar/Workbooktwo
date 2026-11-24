# Workbook 1 – Programozási alapok

52 kérdés • Magyar tanulóanyag

Az alkalmazás jelenlegi magyar kérdései és kidolgozott válaszai, témakörök szerint. A kérdéscímek a kvíz rövidített megfogalmazását követik. A programkódok az eredeti programozási nyelven szerepelnek.

## Adatok alapjai

### 1. Miben különbözik az objektum, a tömb és a primitív JavaScriptben?

**Válasz:**

Az objektum névvel ellátott tulajdonságokat tárol, a tömb sorrendbe rendezett elemeket indexel, a primitív egyetlen megváltoztathatatlan alapérték. A tömb is objektum, de listákhoz való.

**Hétköznapi példa:**

Egy személy adatlapja objektum, a bevásárlólista tömb, az életkor száma primitív.

**Kódpélda:**

```
const person = {name: 'Anna', age: 28}; const list = ['milk', 'bread']; const age = 28;
```

### 2. Hogyan olvasod ki egy objektum adott kulcsához tartozó értéket?

**Válasz:**

Pontjelöléssel vagy szögletes zárójellel: obj.name vagy obj['name']. Változóban tárolt kulcshoz obj[key] kell; a hiányzó saját vagy örökölt tulajdonság értéke undefined.

**Hétköznapi példa:**

Az adatlap név mezőjét közvetlenül is kérheted, vagy egy cetlire írt mezőnév alapján keresheted.

**Kódpélda:**

```
const user = {name: 'Anna'}; const key = 'name'; console.log(user.name, user[key]);
```

### 3. Mi a kulcs–érték pár, és miben tér el a tömb indexelésétől?

**Válasz:**

Objektumban kulcs alapján érsz el értéket, tömbben jellemzően nullától kezdődő sorszámmal. Az objektum mezőnevei jelentést adnak; a tömb indexe a lista pozícióját jelöli.

**Hétköznapi példa:**

A ruhatári névcímke kulcs, a színházi sorban elfoglalt sorszám index.

**Kódpélda:**

```
const car = {color: 'red'}; const colors = ['red', 'blue']; console.log(car.color, colors[0]);
```

### 4. Mikor választanál objektumot, és mikor tömböt?

**Válasz:**

Egy összetartozó tulajdonságokkal leírt dologhoz objektumot, több elem rendezett listájához tömböt választok. Tömb elemei lehetnek objektumok is.

**Hétköznapi példa:**

Egy recept neve és sütési ideje objektumba illik; a heti receptek sorozata tömbbe.

**Kódpélda:**

```
const recipe = {name: 'Soup', minutes: 20}; const menu = [recipe, {name: 'Toast', minutes: 5}];
```

### 5. Hogyan kéred le egy tömb első és utolsó elemét?

**Válasz:**

Az első elem arr[0], az utolsó arr[arr.length - 1] vagy arr.at(-1). Üres tömbnél ezek undefined értéket adnak.

**Hétköznapi példa:**

A számozást nullán kezdő sorban az utolsó ember sorszáma mindig eggyel kisebb a létszámnál.

**Kódpélda:**

```
const a = ['A', 'B', 'C']; console.log(a[0], a[a.length - 1], a.at(-1));
```

### 6. Nevezz meg öt gyakran használt JavaScript-primitívet példával!

**Válasz:**

string: szöveg; number: szám; boolean: igaz/hamis; undefined: nincs megadott érték; null: szándékos hiány. További primitívek a bigint és a symbol; az objektum nem primitív.

**Hétköznapi példa:**

Név: szöveg, ár: szám, fizetve: igaz/hamis; kitöltetlen mező lehet undefined, szándékosan törölt választás null.

**Kódpélda:**

```
const name = 'Anna', price = 10, paid = true; let missing; const selection = null;
```

## Algoritmusok alapjai

### 7. Milyen értékadó operátorok vannak JavaScriptben?

**Válasz:**

Az = értéket rendel változóhoz. Összetett változat például +=, -=, *=, /=, %=, **=: műveletet végez és visszaírja az eredményt. Az = nem összehasonlítás.

**Hétköznapi példa:**

A pénztárca összegét beállítod, majd a fizetésnél levonod belőle a vásárlást.

**Kódpélda:**

```
let balance = 100; balance -= 20; balance += 5; // 85
```

### 8. Sorolj fel aritmetikai operátorokat JavaScriptben!

**Válasz:**

A + összead, a - kivon, a * szoroz, a / oszt, a % maradékot számol, a ** hatványoz. A ++ és -- eggyel növel vagy csökkent. Szövegeknél a + összefűzhet.

**Hétköznapi példa:**

Tíz sütit háromfelé osztva a % megmondja, hány süti marad az egyenlő kiosztás után.

**Kódpélda:**

```
console.log(10 / 3, 10 % 3, 2 ** 3); // about 3.33, 1, 8
```

### 9. Milyen összehasonlító operátorok vannak JavaScriptben?

**Válasz:**

A === és !== típuskonverzió nélkül vizsgál egyenlőséget és eltérést; a == és != konvertálhat típust. A <, >, <= és >= relációt vizsgál. Objektumoknál az egyenlőség az azonosságot, nem a mezők tartalmát vizsgálja.

**Hétköznapi példa:**

A szigorú beléptető a jegy számát és típusát is ellenőrzi, nem fogad el automatikusan hasonló feliratot.

**Kódpélda:**

```
console.log(5 === '5', 5 == '5', 3 < 4); // false, true, true
```

### 10. Melyek a logikai operátorok, és hogyan működnek?

**Válasz:**

A && az ÉS, a || a VAGY, a ! a tagadás. Rövidzárasan értékelnek; && és || egy operandust ad vissza, nem feltétlenül booleant. A ?? csak null vagy undefined esetén választ alapértéket.

**Hétköznapi példa:**

Belépéshez jegy ÉS személyi kell; kedvezményhez diák VAGY nyugdíjas státusz elég.

**Kódpélda:**

```
const allowed = hasTicket && hasId; const label = input ?? 'Guest';
```

### 11. Mi a különbség a for, for...of és for...in ciklus között?

**Válasz:**

A for saját kezdőértéket, feltételt és léptetést használ. A for...of iterálható értékeket, például tömbelemeket jár be. A for...in felsorolható szöveges tulajdonságkulcsokat jár be, örökölteket is; tömb elemeihez általában for...of jobb.

**Hétköznapi példa:**

A for a sorszámokat számolja, a for...of a kosár tárgyait veszi elő, a for...in a fiókok címkéit olvassa.

**Kódpélda:**

```
for (let i=0;i<3;i++) console.log(i); for (const x of ['a','b']) console.log(x); for (const k in {name:'Anna'}) console.log(k);
```

### 12. Hogyan számolsz tömbátlagot beépített metódus nélkül?

**Válasz:**

Ciklussal összeadom az elemeket, majd elosztom az elemszámmal. Üres tömbre külön szabály kell, mert nincs értelmezett átlag; például nullt adok vissza.

**Hétköznapi példa:**

A közös számla összegét elosztod a résztvevők számával; nulla résztvevő között nem osztasz.

**Kódpélda:**

```
const a=[2,4,6]; let sum=0; for(let i=0;i<a.length;i++) sum+=a[i]; const average=a.length ? sum/a.length : null;
```

## Függvények alapjai

### 13. Mi a függvény, és mire használjuk?

**Válasz:**

A függvény meghívható, újrahasználható kódrészlet. Paramétereket fogadhat, feladatot végezhet és return segítségével értéket adhat vissza. Csökkenti az ismétlést és nevet ad a műveletnek.

**Hétköznapi példa:**

A kávégép ugyanazt a folyamatot futtatja minden rendelésnél, más beállításokkal.

**Kódpélda:**

```
function double(x) { return x * 2; } console.log(double(4)); // 8
```

### 14. Milyen szintaktikai részekből áll egy JavaScript-függvény?

**Válasz:**

Egy deklaráció részei: function kulcsszó, név, zárójelben paraméterlista, kapcsos zárójelben törzs. A return opcionális; kifejezett visszatérési érték nélkül undefined lesz az eredmény. Nyílfüggvénynél eltér a jelölés.

**Hétköznapi példa:**

A recept neve a függvénynév, hozzávalói a paraméterek, lépései a törzs, elkészült étele a visszatérési érték.

**Kódpélda:**

```
function add(a, b) { return a + b; } const twice = x => x * 2;
```

### 15. Hogyan adsz át argumentumot egy függvénynek?

**Válasz:**

Híváskor zárójelben adom az argumentumokat; a függvény paraméterei veszik át az értékeket. Az átadás érték szerint történik: objektumnál a referenciaérték másolódik, ezért a közös objektum mezője módosulhat.

**Hétköznapi példa:**

A kávégép beállításneve a paraméter, az általad kiválasztott két cukor a konkrét argumentum.

**Kódpélda:**

```
function greet(name) { return 'Hello ' + name; } greet('Anna');
```

### 16. Miben különbözik a függvénydeklaráció és a függvénykifejezés?

**Válasz:**

Deklaráció: function f() {}. Kifejezés: const f = function() {}. A függvénydeklaráció általában a deklaráció előtt is hívható a hatókörében; a const változóba tett kifejezés csak az inicializálása után.

**Hétköznapi példa:**

Az előre regisztrált szolgáltatást már keresheted, de a frissen telepített gépet csak üzembe helyezés után használhatod.

**Kódpélda:**

```
hello(); function hello(){ return 'hi'; } const bye = function(){ return 'bye'; }; bye();
```

### 17. Mi a callback függvény?

**Válasz:**

Másik függvénynek átadott függvény, amelyet az meghívhat. Callback lehet szinkron, például map esetén, vagy később futó, például eseménykezelőnél. Általában a függvényt adom át, nem a hívás eredményét.

**Hétköznapi példa:**

A futárnak megadod, mit tegyen érkezéskor: ezt a teendőt ő hajtja végre a megfelelő pillanatban.

**Kódpélda:**

```
[1,2,3].map(n => n * 2); button.addEventListener('click', () => console.log('clicked'));
```

### 18. Mi a lokális és globális változó hatóköre?

**Válasz:**

A lokális változó csak a saját hatóköréből és annak belső hatóköreiből érhető el. A globális tágabb körben látható; modul legfelső szintje nem automatikusan globális. A let és const blokk-, a var függvényhatókörű.

**Hétköznapi példa:**

A szobád fiókja helyi tároló; a közös hirdetőtáblát a ház több lakója is eléri.

**Kódpélda:**

```
let globalCount=0; function run(){let localCount=1; globalCount+=localCount;} // localCount is not accessible outside run
```

## Beépített eszközök

### 19. Milyen beépített szövegkezelő metódusokat használsz?

**Válasz:**

trim eltávolítja a szélső szóközöket, toUpperCase nagybetűssé alakít, includes részszöveget keres, slice részt emel ki, replace cserél, split tömbre bont. A string változtathatatlan: ezek nem írják át helyben az eredetit.

**Hétköznapi példa:**

Egy címkét megtisztítasz és újranyomtatsz; az eredeti címkén nem változnak meg maguktól a betűk.

**Kódpélda:**

```
const s=' hello '; console.log(s.trim().toUpperCase(), s.includes('ell'), s.slice(1,3), s.replace('hello','hi'), 'a,b'.split(','));
```

### 20. Sorolj fel legalább öt tömbmetódust működéssel és példával!

**Válasz:**

push a végére tesz, pop leveszi az utolsót; map átalakított új tömböt, filter szűrt új tömböt készít; reduce egy eredménnyé összesít; slice másolatot vagy részletet ad. push és pop módosítja az eredetit.

**Hétköznapi példa:**

A kosárba teszel vagy kiveszel; a másolatból csak gyümölcsöket válogatsz, végül kiszámolod az összárat.

**Kódpélda:**

```
const a=[1,2]; a.push(3); a.pop(); a.map(x=>x*2); a.filter(x=>x>1); a.reduce((s,x)=>s+x,0); a.slice(0,1);
```

### 21. Hogyan végzel matematikai műveleteket beépített JavaScript-eszközökkel?

**Válasz:**

A Math objektum eszközei: round kerekít, floor lefelé és ceil felfelé kerekít, abs abszolút értéket, sqrt négyzetgyököt ad, min/max szélsőértéket keres, random 0 és 1 közötti, 1-et kizáró pszeudovéletlen számot ad.

**Hétköznapi példa:**

A számológép külön gombokat ad gyökvonásra, kerekítésre és abszolút értékre.

**Kódpélda:**

```
Math.round(2.6); Math.floor(-2.2); Math.ceil(2.2); Math.abs(-5); Math.sqrt(9); Math.max(2,7); Math.random();
```

### 22. Milyen beépített eszközök segítenek számok átalakításában és ellenőrzésében?

**Válasz:**

Number egész szöveget próbál számmá alakítani; parseInt egész, parseFloat tizedes számkezdetet olvas. Number.isNaN NaN-t, Number.isInteger egész számot ellenőriz. toFixed formázott szöveget ad, nem számot.

**Hétköznapi példa:**

A kassza számként számol, de a nyugtán két tizedesjegyű szövegként jeleníti meg az árat.

**Kódpélda:**

```
Number('12'); parseInt('12px',10); parseFloat('3.5kg'); Number.isNaN(NaN); Number.isInteger(3); (2.5).toFixed(2);
```

### 23. Miben különbözik a for ciklus és a forEach?

**Válasz:**

A for explicit vezérlést ad, break és continue használható. A forEach callbacket futtat a tömb meglévő elemein; hagyományos break nem használható, és az async callbackek Promise-ait sem várja meg automatikusan.

**Hétköznapi példa:**

A for esetén te vezeted a sort és megállhatsz; a forEach kioszt egy feladatot minden tagnak.

**Kódpélda:**

```
for(const x of [1,2,3]){if(x===2) break;} [1,2,3].forEach(x=>console.log(x));
```

## Fájlok és JSON

### 24. Miben különbözik a JavaScript-adat és a JSON?

**Válasz:**

A JSON szöveges adatcsere-formátum; objektumot, tömböt, szöveget, véges számot, booleant és nullt ír le. Nincs benne függvény vagy undefined, a kulcsokat dupla idézőjel veszi körül. A JavaScript futásidejű értékek köre ennél tágabb.

**Hétköznapi példa:**

A JSON egy kitöltött szállítólevél, a JavaScript-objektum a programban ténylegesen kezelt csomag.

**Kódpélda:**

```
const text = '{"name":"Anna","age":28}'; const data = JSON.parse(text); JSON.stringify(data);
```

### 25. Hogyan lesz egy JSON-fájl tartalmából JavaScript-adat?

**Válasz:**

Beolvasom a fájl szövegét, majd JSON.parse segítségével feldolgozom. Böngészőben fetch után response.json is használható. A hibás JSON kivételt okozhat, és az adatok szerkezetét is ellenőrizni kell.

**Hétköznapi példa:**

A receptet először elhozod a polcról, utána elolvasod és értelmezed; a lap még nem maga a kész étel.

**Kódpélda:**

```
const response = await fetch('/data.json'); if(!response.ok) throw Error('HTTP error'); const data = await response.json();
```

## DOM és megjelenítés

### 26. Miben különbözik egy JavaScript-objektum és a DOM?

**Válasz:**

Egy általános objektum alkalmazásadatokat tárol. A DOM a dokumentum csomópontokból álló fája, böngészős API-val; az elemek maguk is objektumok. Sima adatobjektum átírása önmagában nem módosítja a DOM-ot.

**Hétköznapi példa:**

A vendéglista adatai és a falra tett ülésrend külön dolog; az adatlap átírása nem festi át magától a táblát.

**Kódpélda:**

```
const data={title:'Hello'}; document.querySelector('h1').textContent=data.title;
```

### 27. Hogyan változtatod meg egy HTML-elem szövegét JavaScriptből?

**Válasz:**

Kiválasztom az elemet, ellenőrzöm, hogy létezik, majd beállítom a textContent értékét. A kód az elem létrejötte után fusson. HTML beszúrásához más API kell; nem megbízható szöveget ne adj innerHTML-nek.

**Hétköznapi példa:**

Megkeresed a megfelelő bolti árcédulát, és csak annak a feliratát cseréled ki.

**Kódpélda:**

```
const title = document.querySelector('h1'); if(title) title.textContent = 'Hello!';
```

## Eseménykezelés

### 28. Mi az eseményfigyelő JavaScriptben?

**Válasz:**

Egy eseményhez regisztrált callback, amely a bekövetkező eseményre reagál. addEventListener adja hozzá; nem kell folyamatosan ciklusban ellenőrizni, történt-e kattintás.

**Hétköznapi példa:**

A csengőre váró ember csak a csengetéskor megy ajtót nyitni.

**Kódpélda:**

```
button.addEventListener('click', () => console.log('Hello'));
```

### 29. Hogyan változik egy elem tartalma kattintásra?

**Válasz:**

Megkeresem az elemet, click eseményfigyelőt adok hozzá, és a callbackben átírom a textContent értékét. A figyelőt egyszer regisztrálom, nem minden kattintáskor újra.

**Hétköznapi példa:**

A csengő gombját összekötöd a lámpával: lenyomáskor megjelenik az új jelzés.

**Kódpélda:**

```
const b=document.querySelector('button'); b.addEventListener('click',()=>{ b.textContent='Clicked!'; });
```

### 30. Hogyan éred el a kattintott elemet az eseménykezelőben?

**Válasz:**

event.target az eredeti célpont; event.currentTarget az az elem, amelyhez az éppen futó figyelőt kötöttük. Belső ikonra kattintva a két elem eltérhet. Nyílfüggvényben a this nem az esemény célpontjából származik.

**Hétköznapi példa:**

A csengő pontos gombja a target, a csengőrendszert kezelő ajtópanel a currentTarget.

**Kódpélda:**

```
button.addEventListener('click',e=>{ console.log(e.target,e.currentTarget); });
```

## CSS alapok

### 31. Mi a block, inline és inline-block megjelenítés közti különbség?

**Válasz:**

A block normál elrendezésben új sort kezd és jellemzően kitölti az elérhető szélességet. Az inline a szöveggel folyik, width/height nem úgy méretezi, mint egy dobozt. Az inline-block sorban marad, de szélessége és magassága állítható.

**Hétköznapi példa:**

A block egy külön polc, az inline egy szó a mondatban, az inline-block egy méretezhető kitűző a szöveg mellett.

**Kódpélda:**

```
.panel { display:block; } .word { display:inline; } .badge { display:inline-block; width:80px; height:30px; }
```

### 32. Mi a position: relative és absolute különbsége?

**Válasz:**

A relative az elem eredeti helyéhez képest tolható, miközben a helye megmarad a normál elrendezésben. Az absolute kikerül a normál folyamból, és tipikusan a legközelebbi pozicionált őshöz igazodik.

**Hétköznapi példa:**

Relative: arrébb húzod a széket, de a helyét nem foglalják el. Absolute: egy matricát a doboz sarkához rögzítesz.

**Kódpélda:**

```
.card { position:relative; } .badge { position:absolute; top:8px; right:8px; }
```

### 33. Mi a CSS dobozmodell?

**Válasz:**

Az elem content, padding, border és margin rétegekből áll. A padding belső, a margin külső térköz. box-sizing: border-box esetén a megadott width a tartalmat, paddingot és bordert együtt tartalmazza, a margint nem.

**Hétköznapi példa:**

A csomagban az áru a content, a szivacs padding, a karton border, a dobozok közti rés margin.

**Kódpélda:**

```
.box { box-sizing:border-box; width:200px; padding:16px; border:2px solid; margin:10px; }
```

### 34. Mely CSS-tulajdonságok szabályozzák a betűket és a szöveget?

**Válasz:**

font-family a betűcsalád, font-size a méret, font-weight a vastagság, font-style a dőlés. color a szín, line-height a sormagasság, text-align az igazítás, text-decoration például az aláhúzás, letter-spacing a betűköz.

**Hétköznapi példa:**

Egy meghívó tervezésekor kiválasztod a betűtípust, méretet, vastagságot és a sorok távolságát.

**Kódpélda:**

```
.title { font-family:Arial,sans-serif; font-size:24px; font-weight:700; color:navy; line-height:1.4; text-align:center; }
```

### 35. Hogyan adsz hozzá és veszel le CSS-osztályt JavaScriptből?

**Válasz:**

Kiválasztom az elemet, majd classList.add vagy classList.remove műveletet használok. A toggle kapcsol, a contains ellenőrzi a tagságot. Így nem kell felülírni az összes meglévő osztályt.

**Hétköznapi példa:**

A kabátra felteszel vagy leveszel egy kitűzőt anélkül, hogy az összes többit lecserélnéd.

**Kódpélda:**

```
const el=document.querySelector('.card'); el.classList.add('active'); el.classList.remove('hidden'); el.classList.toggle('selected');
```

## JavaScript sajátosságok

### 36. Mit jelent az érték és a referencia másolása JavaScriptben?

**Válasz:**

Primitív hozzárendelésekor az alapértéket másolod. Objektumnál a referenciaérték másolódik, ezért két változó ugyanarra az objektumra mutathat. Egyik változó új objektumra állítása nem írja át a másikat.

**Hétköznapi példa:**

Két ember ugyanannak a lakásnak a címét kapja: az egyik által átrendezett lakást a másik is úgy látja.

**Kódpélda:**

```
const a={x:1}; const b=a; b.x=2; console.log(a.x); // 2
```

### 37. Mi módosítható és mi megváltoztathatatlan JavaScriptben?

**Válasz:**

Az objektumok és tömbök általában helyben módosíthatók, a primitívek megváltoztathatatlanok. Egy változó új értékre állítása nem a régi primitív átírása. A const a kötést védi, nem az objektum belsejét; a közös referencia miatt a módosítás másutt is látszhat.

**Hétköznapi példa:**

Egy közösen szerkesztett füzetbe beleírhatsz; egy kimondott szót már csak egy új szóval válthatsz fel.

**Kódpélda:**

```
const a=[1]; a.push(2); let s='cat'; s=s.toUpperCase(); // a changed; a new string was assigned
```

### 38. A null objektum vagy primitív JavaScriptben?

**Válasz:**

A null primitív érték, szándékos hiányt jelöl. A typeof null eredménye történeti okból 'object', de ettől a null nem objektum és nem lehet mezőket olvasni róla.

**Hétköznapi példa:**

Az üres parkolóhely nem autó, még ha a régi nyilvántartás autó kategóriába sorolja is.

**Kódpélda:**

```
console.log(typeof null); // 'object' (historical quirk)
console.log(null === null); // true
```

### 39. Mit jelent az undefined?

**Válasz:**

Az undefined primitív érték, jellemzően még meg nem adott értéket jelöl. Ilyen a nem inicializált változó, a hiányzó objektumtulajdonság vagy a visszatérési érték nélküli függvény eredménye. Egy egyáltalán nem deklarált név használata viszont ReferenceErrort okozhat.

**Hétköznapi példa:**

Az üresen hagyott űrlapmezőhöz még nem adtak választ; ez nem ugyanaz, mint a szándékos nincs választás.

**Kódpélda:**

```
let x; console.log(x, {}.missing); // undefined, undefined
```

### 40. Mikor használj var, let és const deklarációt?

**Válasz:**

const legyen az alap, ha nem rendeled újra a változót; let, ha új értéket kap. Mindkettő blokkhatókörű. var függvényhatókörű és régebbi viselkedésű, modern kódban általában kerülendő. const objektum mezője ettől még módosítható.

**Hétköznapi példa:**

A const rögzített címke ugyanazon dobozon; a doboz tartalma változhat. A let címkét másik dobozra is átrakhatod.

**Kódpélda:**

```
const user={name:'Anna'}; user.name='Eva'; let count=0; count++;
```

### 41. Mi a hoisting JavaScriptben?

**Válasz:**

A deklarációk hatóköri kötései már a kód végrehajtása előtt létrejönnek. A var undefined-ként inicializált, a függvénydeklaráció hívható. let és const esetén az inicializálásig temporal dead zone van: korábbi hozzáférés hibát okoz. A kód fizikailag nem mozdul el.

**Hétköznapi példa:**

A tanár előre felírja a névsort, de néhány szekrény csak a kiosztás pillanatában nyitható.

**Kódpélda:**

```
console.log(x); var x=3; // undefined
// console.log(y); let y=3; // ReferenceError
```

## Git

### 42. Miért hasznos a verziókezelés?

**Válasz:**

Nyomon követi a változásokat, visszakereshető előzményt és visszaállítási lehetőséget ad. Ágakon párhuzamosan dolgozhatunk, és a módosítások összevethetők, egyesíthetők. A commit értelmes, rögzített munkapont.

**Hétköznapi példa:**

Egy dokumentum számozott mentéseihez képest azt is látod, ki mit változtatott, és a külön munkák összeilleszthetők.

**Kódpélda:**

```
git status
git add app.js
git commit -m "Add greeting"
git log --oneline
```

### 43. Mi a különbség Git és GitHub között?

**Válasz:**

A Git elosztott verziókezelő, helyben és internet nélkül is használható. A GitHub Git-repók tárhelye és együttműködési platform, például pull requestekkel és hibajegyekkel. Githez nem kötelező GitHub.

**Hétköznapi példa:**

A Git a fényképező és az albumkezelő; a GitHub egy hely, ahol megosztod az albumot másokkal.

**Kódpélda:**

```
git init
git status
# A local Git repository works without a GitHub account.
```

### 44. Mire való a távoli Git-repozitórium?

**Válasz:**

Megosztási és szinkronizációs pont a külön klónok között. push feltölti a helyi commitokat, fetch letölti a távoli referenciák frissítéseit, pull be is integrálhatja őket. Segíti az együttműködést és a másolatok megőrzését.

**Hétköznapi példa:**

A közös polcra mindenki felteszi a kész jegyzeteit, mások pedig elhozzák az új változatokat.

**Kódpélda:**

```
git remote -v
git fetch origin
git push origin main
```

### 45. Mikor keletkezik merge conflict?

**Válasz:**

Ha a Git nem tudja automatikusan összeegyeztetni a változásokat, például ugyanazt a sort eltérően írták át vagy egyik oldalon törölték a módosított fájlt. A kívánt tartalmat kézzel rendezni, tesztelni és a feloldást rögzíteni kell.

**Hétköznapi példa:**

Két szerkesztő ugyanazt a mondatot máshogyan javítja; valakinek el kell döntenie a végleges változatot.

**Kódpélda:**

```
git status
# Edit conflicted files, remove conflict markers, test.
git add app.js
git commit
```

## Terminál

### 46. Hogyan futtatsz JavaScript-fájlt terminálból?

**Válasz:**

Telepített Node.js esetén node fájlnév.js paranccsal, a megfelelő könyvtárból vagy teljes elérési úttal. A Node környezetben a böngésző DOM-ja, például document, alapból nem érhető el.

**Hétköznapi példa:**

A recepthez megfelelő konyha kell: a Node a terminálban futó JavaScript környezete, nem böngészőablak.

**Kódpélda:**

```
node app.js
# app.js: console.log('Hello');
```

### 47. Mely billentyűvel állítasz le terminálban futó folyamatot?

**Válasz:**

Általában Ctrl+C megszakítást küld az előtérben futó folyamatnak. A program kezelheti ezt a jelzést; nem minden helyzetben azonos a kényszerített leállítással.

**Hétköznapi példa:**

A stopgomb jelzi a gépnek, hogy fejezze be a munkát; a gép még elvégezheti a biztonságos leállítást.

**Kódpélda:**

```
node server.js
# Press Ctrl+C to interrupt the foreground process.
```

### 48. Hogyan hívod elő az előző terminálparancsot?

**Válasz:**

Interaktív shellben általában a felfelé nyíl előhívja az előző parancsot. Többször lenyomva régebbieket kapsz; Ctrl+R sok shellben keres az előzményben. Futtatás előtt ellenőrizd a felidézett parancsot.

**Hétköznapi példa:**

Mint amikor a telefonon az előző tárcsázott számot hívod elő, de még ellenőrzöd, kit hívsz.

**Kódpélda:**

```
# Press Up Arrow to recall the previous command, then Enter to run it.
```

### 49. Hogyan lépsz a szülőkönyvtárba terminálból?

**Válasz:**

A cd .. paranccsal egy szinttel feljebb lépek. A .. a szülőkönyvtárat jelöli, a . az aktuálisat. Ez könyvtárváltás, nem fájltörlés.

**Hétköznapi példa:**

Egy szobából visszamész az azt tartalmazó folyosóra.

**Kódpélda:**

```
cd ..
```

## Hibakeresés

### 50. Milyen módszereket használsz hibakereséskor?

**Válasz:**

Reprodukálom a hibát, elolvasom az üzenetet és a stack trace-t, kisebb példára szűkítem. Naplózással, breakpointtal, léptetéssel és változóvizsgálattal ellenőrzöm a feltételezéseimet. A javítást releváns teszttel igazolom.

**Hétköznapi példa:**

A szerelő először előidézi a zajt, majd részenként ellenőrzi a gépet; nem találomra cserél mindent.

**Kódpélda:**

```
console.log({input, result});
debugger; // pauses when a debugger is attached
```

### 51. Mit jelent a step over, step into és step out?

**Válasz:**

Step over végrehajtja a következő utasítást anélkül, hogy belépnénk a meghívott függvénybe. Step into belép a hívásba. Step out futtatja az aktuális függvény hátralévő részét és visszatér a hívóhoz.

**Hétköznapi példa:**

Egy éttermi feladatot rábízol a konyhára (over), bemész megnézni a lépéseket (into), vagy kivárod a végét és visszamész a pulthoz (out).

**Kódpélda:**

```
const result = calculate(5); // step into inspects calculate; step over runs it; step out leaves its frame
```

### 52. Hogyan kezded a hibakeresést egy konkrét sornál?

**Válasz:**

Breakpointot teszek az editor vagy DevTools megfelelő sorára, elindítom debuggerrel a programot és előidézem a futást. A végrehajtás megáll a sor végrehajtása előtt; ekkor változókat és hívási vermet vizsgálhatok. A debugger utasítás is megállíthat csatlakoztatott debugger mellett.

**Hétköznapi példa:**

Megállót jelölsz ki a busznak: amikor odaér, megáll, és megnézheted, kik vannak rajta.

**Kódpélda:**

```
function calculate(x){ debugger; return x*2; } calculate(3);
```

# Workbook 2 – Webfejlesztés

109 kérdés • Magyar tanulóanyag

Az alkalmazás jelenlegi magyar kérdései és kidolgozott válaszai, témakörök szerint. A kérdéscímek a kvíz rövidített megfogalmazását követik. A programkódok az eredeti programozási nyelven szerepelnek.

## JavaScript nyelvi elemek

### 1. Mi az ECMAScript?

**Válasz:**

Az ECMAScript a nyelvi szabvány, a JavaScript annak megvalósítása környezeti API-kkal.

**Hétköznapi példa:**

A szabvány a recept, a megvalósítás az azt követő konyha.

**Kódpélda:**

```
const x = 1;
```

### 2. Mi a blokk- és függvényhatókör?

**Válasz:**

let és const blokkhatókörű; var függvényhatókörű, nem az if blokkhoz kötött.

**Hétköznapi példa:**

Szobakulcs vagy egész emeletre szóló kulcs.

**Kódpélda:**

```
if (true) { let x = 1; }
```

### 3. Mire jó a template literal?

**Válasz:**

Backtick közé írt szöveg, ${kifejezés} interpolációval és többsoros szöveggel.

**Hétköznapi példa:**

A névre szóló kártyán a sablonba behelyettesíted a címzettet.

**Kódpélda:**

```
const s = `Hello ${name}`;
```

### 4. Mit csinál a spread?

**Válasz:**

A ... elemeket vagy saját felsorolható tulajdonságokat bont ki. A másolat sekély, a beágyazott objektumok közösek maradhatnak.

**Hétköznapi példa:**

A címjegyzék másolása nem épít új házakat.

**Kódpélda:**

```
const copy = [...items];
```

### 5. Mi a destrukturálás?

**Válasz:**

Objektummezőket vagy tömbelemeket emel ki változókba; nem mély másolás.

**Hétköznapi példa:**

Kipakolod a kenyeret és tejet a szatyorból.

**Kódpélda:**

```
const {name} = user; const [first] = items;
```

### 6. Mikor érvényes az alapértelmezett paraméter?

**Válasz:**

Hiányzó vagy undefined argumentumnál; null nem váltja ki.

**Hétköznapi példa:**

Méretválasztás nélkül közepes kávét kapsz.

**Kódpélda:**

```
function greet(name='Guest') { return name; }
```

### 7. Mire valók az ES-modulok?

**Válasz:**

export/import révén osztanak meg kódot fájlok között saját hatókörrel; rendezettebb és újrahasználható lesz a kód.

**Hétköznapi példa:**

Külön fiókokból veszed elő a szükséges eszközt.

**Kódpélda:**

```
export const add = (a,b) => a+b;
```

### 8. CommonJS vagy ES-modul?

**Válasz:**

CommonJS require/module.exports alapú; ES-modul import/export alapú és statikusan elemezhető. Dinamikus import() is létezik.

**Hétköznapi példa:**

Menet közbeni eszközkérés vagy előre megadott eszközlista.

**Kódpélda:**

```
const x=require('./x'); // CJS
```

### 9. Mi a magasabb rendű függvény?

**Válasz:**

Függvényt fogad argumentumként vagy függvényt ad vissza.

**Hétköznapi példa:**

A munkavezető tárgyak mellett munkautasítást is kap.

**Kódpélda:**

```
const twice = fn => x => fn(fn(x));
```

### 10. Map, filter és reduce: melyik mire jó?

**Válasz:**

map átalakít, filter kiválogat, reduce felhalmozott eredményt számol.

**Hétköznapi példa:**

Minden almát szeletelsz, csak a jót válogatod ki, vagy összeméred őket.

**Kódpélda:**

```
[1,2].map(x=>x*2)
```

### 11. Hogyan működik a filter?

**Válasz:**

Új tömböt ad a feltételnek megfelelő elemekkel; objektumokat nem klónoz.

**Hétköznapi példa:**

Csak az érett paradicsomokat teszed kosárba.

**Kódpélda:**

```
[1,2,3].filter(x=>x>1)
```

### 12. Mit csinál a reduce?

**Válasz:**

Az akkumulátorból és aktuális elemből épít eredményt. Kezdőérték megadásával üres tömb is kezelhető.

**Hétköznapi példa:**

A kasszás minden árat hozzáad a végösszeghez.

**Kódpélda:**

```
[2,3].reduce((sum,x)=>sum+x,0)
```

## Hálózat és fetch

### 13. Mire jó az URL query string?

**Válasz:**

A ? utáni kulcs-érték párok például keresést, szűrést és lapozást adnak meg. Ne kerüljön bele titok.

**Hétköznapi példa:**

A kérőlapon a termék mellé szűrési feltételeket írsz.

**Kódpélda:**

```
/books?page=2&lang=hu
```

### 14. Mire szolgál a fetch?

**Válasz:**

Aszinkron HTTP-kérést indít, Promise-t ad Response-ra; a törzs beolvasása külön lépés.

**Hétköznapi példa:**

Rendelés, csomagátvétel, majd külön kicsomagolás.

**Kódpélda:**

```
const r = await fetch('/api');
```

### 15. Async/await vagy then?

**Válasz:**

Mindkettő Promise-alapú. Az await olvasható lépéssort ad try/catch mellett; a then callback-láncot használ. Egyik sem teszi szinkronná a hálózatot.

**Hétköznapi példa:**

Ugyanazt a szállítást értesítésekkel vagy lépéssorral követed.

**Kódpélda:**

```
try { const r=await fetch('/api'); } catch(e) { console.error(e); }
```

### 16. Mi az aszinkron működés?

**Válasz:**

Hálózatra vagy időzítőre várva más munka folytatódhat. Nem jelenti minden JavaScript-kód párhuzamos futását.

**Hétköznapi példa:**

Amíg sül a pizza, megterítesz.

**Kódpélda:**

```
setTimeout(()=>console.log('Later'),1000);
```

### 17. Hogyan dolgozod fel a fetch válaszát?

**Válasz:**

Státuszellenőrzés után await json(), text() vagy blob(). A törzs normálisan egyszer olvasható.

**Hétköznapi példa:**

Ellenőrzöd a csomag címkéjét, majd kibontod.

**Kódpélda:**

```
if (!r.ok) throw Error('HTTP'); const data=await r.json();
```

### 18. Hogyan kezeli a fetch a hibákat?

**Válasz:**

Hálózati hiba elutasíthatja a Promise-t, de 404/500 önmagában nem. Ellenőrizni kell az ok vagy status értékét.

**Hétköznapi példa:**

A futár hibátlanul átadhat egy „nincs készleten” levelet.

**Kódpélda:**

```
if (!response.ok) throw Error(String(response.status));
```

### 19. Miből áll egy URL?

**Válasz:**

Séma, hoszt, opcionális port, útvonal, query és fragment. A fragment nem része a HTTP-kérésnek.

**Hétköznapi példa:**

Cím és kiegészítő kézbesítési megjegyzések.

**Kódpélda:**

```
https://example.com:443/books?page=2#chapter
```

## Reszponzív dizájn

### 20. Mi a reszponzív dizájn?

**Válasz:**

Kijelző- és tartalommérethez alkalmazkodó, olvasható és kezelhető felület.

**Hétköznapi példa:**

Kis szobában is elférő összecsukható asztal.

**Kódpélda:**

```
img { max-width:100%; height:auto; }
```

### 21. Mi a mobile-first?

**Válasz:**

Kis képernyőre tervezünk először, majd nagyobbnál bővítünk, például min-width queryvel.

**Hétköznapi példa:**

Először a hátizsákba férő lényeg, utána az extrák.

**Kódpélda:**

```
@media(min-width:48rem) { .grid { display:grid; } }
```

### 22. Hogyan ellenőrzöd több képernyőn az oldalt?

**Válasz:**

DevTools eszköznézettel, ablakátméretezéssel és valódi eszközökkel; zoomot és túlcsordulást is ellenőrizz.

**Hétköznapi példa:**

A ruhát több méretű emberen is felpróbálod.

**Kódpélda:**

```
DevTools → Device toolbar
```

### 23. Milyen technikák teszik reszponzívvá az oldalt?

**Válasz:**

Rugalmas Grid/Flexbox, relatív méretek, töréspontok, tördelés, folyékony képek és viewport meta.

**Hétköznapi példa:**

Átrendezhető bútorok, nem a falhoz betonozott székek.

**Kódpélda:**

```
grid-template-columns:repeat(auto-fit,minmax(16rem,1fr));
```

### 24. Mit csinál a media query?

**Válasz:**

Környezeti feltételek, például szélesség alapján kapcsol CSS-szabályokat.

**Hétköznapi példa:**

Hidegben kabátot, melegben pólót választasz.

**Kódpélda:**

```
@media(max-width:600px) { nav { flex-wrap:wrap; } }
```

### 25. Mi a Flexbox?

**Válasz:**

Egydimenziós elrendezés fő- és kereszttengellyel, rugalmas mérettel és igazítással.

**Hétköznapi példa:**

Egy polcon osztod el a tárgyakat és a szabad helyet.

**Kódpélda:**

```
display:flex; gap:1rem;
```

### 26. Hogyan hibakeresel Flexboxot?

**Válasz:**

DevTools layout overlay, computed stílusok, konténer- és itemtulajdonságok vizsgálata.

**Hétköznapi példa:**

Vonalzóval megnézed a polc beosztását.

**Kódpélda:**

```
Inspect → Layout → Flex overlay
```

### 27. Mi a flex container és item?

**Válasz:**

A display:flex elem a konténer, közvetlen gyerekei az itemek; a közös és egyedi méretezési szabályok külön helyen vannak.

**Hétköznapi példa:**

A polc a konténer, a könyvek az itemek.

**Kódpélda:**

```
.row {display:flex} .row>article {flex:1}
```

## JavaScript OOP

### 28. Class vagy konstruktorfüggvény JavaScriptben?

**Válasz:**

Mindkettő prototípusokra épül. A class rendezettebb szintaxist és szigorúbb szabályokat ad, például new nélkül nem hívható.

**Hétköznapi példa:**

Új vagy régi formájú terv ugyanarra az építési mechanizmusra.

**Kódpélda:**

```
class Person { constructor(name){this.name=name;} }
```

### 29. Mit csinál a new?

**Válasz:**

Objektumot hoz létre, prototípust kapcsol és konstruktorát ezzel a this értékkel hívja. Explicit objektum-visszatérés felülválthatja az eredményt.

**Hétköznapi példa:**

Új terméket gyárt és elvégzi az induló beállításokat.

**Kódpélda:**

```
const person=new Person('Ada');
```

### 30. Mikor fut a constructor?

**Válasz:**

Példányosításkor inicializál. Leszármazottban this előtt super() szükséges.

**Hétköznapi példa:**

A tagsági kártyát átadáskor töltöd ki.

**Kódpélda:**

```
constructor(name){this.name=name;}
```

### 31. Mik a class metódusai?

**Válasz:**

Függvények: a szokásos példánymetódus a prototípuson, a static az osztályon található.

**Hétköznapi példa:**

A mosógép műveletei a mosás és öblítés.

**Kódpélda:**

```
class Dog { speak(){return 'Woof';} }
```

### 32. Mik a class mezői?

**Válasz:**

Állapotot tároló tulajdonságok. Példánymező objektumhoz, static mező osztályhoz tartozik.

**Hétköznapi példa:**

A bicikli színe adat, a gyorsítás művelet.

**Kódpélda:**

```
class Counter { value=0; }
```

### 33. Mi az öröklés JavaScriptben?

**Válasz:**

Tulajdonságok és metódusok keresése a prototípusláncon keresztül; a class is erre épül.

**Hétköznapi példa:**

Hiányzó helyi szabályt a központi kézikönyvben keresel.

**Kódpélda:**

```
Object.getPrototypeOf(instance)
```

### 34. Mire való az extends?

**Válasz:**

Leszármazott osztályt készít; super segítségével szülőkonstruktor vagy -metódus érhető el.

**Hétköznapi példa:**

A speciális bicikli a megszokott modell tudását bővíti.

**Kódpélda:**

```
class Cat extends Animal {}
```

## Express

### 35. Hogyan kommunikál kliens és szerver?

**Válasz:**

A kliens kér, a szerver feldolgoz és válaszol; késleltetéssel és hibákkal számolni kell.

**Hétköznapi példa:**

Vendég rendel, konyha elkészít és visszaküldi az ételt.

**Kódpélda:**

```
GET /menu → JSON response
```

### 36. Mi egy HTTP-kérés és -válasz szerkezete?

**Válasz:**

Kérés: metódus, célpont, fejlécek, opcionális törzs. Válasz: státusz, fejlécek, opcionális törzs.

**Hétköznapi példa:**

A boríték címzése és a benne lévő levél külön adat.

**Kódpélda:**

```
POST /recipes; Content-Type:application/json
```

### 37. Mi az Express.js?

**Válasz:**

Node.js webes keretrendszer routinghoz, middleware-hez és kérés/válasz kezeléshez; nem adatbázis.

**Hétköznapi példa:**

Éttermünk munkarendje a megfelelő pulthoz irányít.

**Kódpélda:**

```
app.get('/hello',(req,res)=>res.send('Hello'));
```

### 38. Mi az Express middleware?

**Válasz:**

Függvény a feldolgozási láncban req/res/next argumentumokkal. Beépített példák: json(), urlencoded(), static().

**Hétköznapi példa:**

A csomag ellenőrzőpontokon halad át.

**Kódpélda:**

```
app.use(express.json());
```

### 39. Hogyan regisztrálsz middleware-t?

**Válasz:**

app.use() vagy útvonalargumentum segítségével; a regisztrálási sorrend számít.

**Hétköznapi példa:**

Az ellenőrzőpontokat haladási sorrendbe rakod.

**Kódpélda:**

```
app.use('/api',logger);
```

### 40. Hogyan szolgál ki statikus fájlt az Express?

**Válasz:**

express.static(könyvtár) middleware-rel, opcionális URL-előtag alatt.

**Hétköznapi példa:**

Önkiszolgáló polcon előre elkészített termékek vannak.

**Kódpélda:**

```
app.use('/assets',express.static('public'));
```

### 41. Mit csinál az express.json()?

**Válasz:**

Megfelelő Content-Type esetén a JSON-törzset req.body-ba parse-olja. Az üzleti tartalmat külön validálni kell.

**Hétköznapi példa:**

Kibontja a levelet, de nem ellenőrzi minden állítását.

**Kódpélda:**

```
app.use(express.json());
```

### 42. Hogyan halad az Express kérés/válasz ciklusa?

**Válasz:**

Sorrendben futnak az illeszkedő middleware-ek és handlerek választ küldésig vagy hibakezelésig.

**Hétköznapi példa:**

A kérés a fogadópulttól a konyháig halad.

**Kódpélda:**

```
app.use(logger); app.get('/x',handler);
```

### 43. Hogyan működik az Express routing?

**Válasz:**

A HTTP-metódus és útvonal együtt választ kezelőt; GET és POST ugyanott külön művelet lehet.

**Hétköznapi példa:**

Egy banki ablaknál befizetni és egyenleget kérni más művelet.

**Kódpélda:**

```
app.get('/recipes',list); app.post('/recipes',create);
```

### 44. res.send vagy res.json?

**Válasz:**

send többféle tartalmat küld, json JSON-t szerializál megfelelő Content-Type-pal. A státusz res.status()-szal állítható.

**Hétköznapi példa:**

Általános csomag vagy szabványos adatlap.

**Kódpélda:**

```
res.status(201).json({id:1});
```

### 45. Mit csinál a next()?

**Válasz:**

Továbbadja a vezérlést; next(error) hibakezeléshez irányít. Válaszküldés zárhatja le a kört.

**Hétköznapi példa:**

Az ügyintéző a következő kollégának adja az iratot.

**Kódpélda:**

```
if (!allowed) return res.sendStatus(403); next();
```

### 46. Mik a route paraméterek?

**Válasz:**

Dinamikus útvonalszakaszok, például :id; req.params.id tartalmazza. Nem azonos req.query-val.

**Hétköznapi példa:**

Az utcanév mellett változó házszám.

**Kódpélda:**

```
app.get('/users/:id',(req,res)=>res.send(req.params.id));
```

## REST és űrlapok

### 47. Melyek a gyakori HTTP-státuszok?

**Válasz:**

200 siker, 201 létrehozva, 204 nincs törzs, 400 hibás kérés, 401 hitelesítés kell, 403 tiltott, 404 hiányzik, 500 szerverhiba.

**Hétköznapi példa:**

A rendelés visszajelzése lehet sikeres, hiányos vagy hibás.

**Kódpélda:**

```
res.status(404).json({error:'Not found'});
```

### 48. Mire jók a HTTP-fejlécek?

**Válasz:**

Metaadatok: Content-Type formátum, Accept elvárt típus, Authorization hitelesítés, Cache-Control gyorsítótárazás.

**Hétköznapi példa:**

A „törékeny” címke nem a csomag tartalma.

**Kódpélda:**

```
Content-Type: application/json
```

### 49. Mire valók a HTTP-metódusok?

**Válasz:**

GET olvas, POST feldolgoz/létrehoz, PUT cserél, PATCH részlegesen módosít, DELETE töröl; az API-szerződés számít.

**Hétköznapi példa:**

Irattári olvasás, hozzáadás, csere, javítás és törlés.

**Kódpélda:**

```
GET /recipes; DELETE /recipes/1
```

### 50. Miben különbözik a GET és POST?

**Válasz:**

GET biztonságos olvasás, tipikusan queryvel. POST törzsben küldhet adatot és módosíthat. Önmagában nem titkosítottabb.

**Hétköznapi példa:**

Étlapot nézni más, mint rendelni.

**Kódpélda:**

```
fetch('/recipes',{method:'POST',body:JSON.stringify(data)})
```

### 51. PATCH vagy PUT?

**Válasz:**

PATCH részleges módosítás. PUT reprezentációcsere és idempotens; PATCH idempotenciája a művelettől függ.

**Hétköznapi példa:**

Egy sort javítasz vagy teljes új adatlapot adsz.

**Kódpélda:**

```
PATCH /users/1 {"name":"Ada"}
```

### 52. Hogyan működik a DELETE?

**Válasz:**

Eltávolítást kér, jogosultságellenőrzéssel. Ismétlése azonos kívánt állapotú, bár a státuszkód eltérhet.

**Hétköznapi példa:**

Kétszer kéred a cetli levételét: végül nincs ott.

**Kódpélda:**

```
DELETE /recipes/42
```

### 53. Mi a REST és a korlátai?

**Válasz:**

Erőforrások és egységes interfész; kliens-szerver, állapotmentesség, cache, rétegzettség és opcionális code-on-demand.

**Hétköznapi példa:**

Minden kérvény teljes; nem kell emlékezni az előző beszélgetésre.

**Kódpélda:**

```
GET /recipes/42 → representation
```

### 54. Milyen egy recept CRUD API-ja?

**Válasz:**

POST /recipes létrehoz, GET /recipes/1 olvas, PUT/PATCH /recipes/1 módosít, DELETE /recipes/1 töröl. Az útvonal erőforrást jelöl.

**Hétköznapi példa:**

Ugyanazon mappacímen más műveleteket végzel.

**Kódpélda:**

```
GET /recipes/1; PATCH /recipes/1
```

### 55. Hogyan kezeled a form submitot JS-ben?

**Válasz:**

submit eseménynél preventDefault(), majd FormData, validálás és elküldés.

**Hétköznapi példa:**

Postázás előtt átnézed a levelet.

**Kódpélda:**

```
form.addEventListener('submit',e=>{e.preventDefault();});
```

### 56. Milyen elemekből áll egy használható HTML-form?

**Válasz:**

form, nevezett vezérlők, kapcsolt label és submit. action/method a hagyományos beküldést szabályozza.

**Hétköznapi példa:**

Kérdőív mezőkkel, címkékkel és leadási lehetőséggel.

**Kódpélda:**

```
<form><input name="city"><button>Send</button></form>
```

### 57. Mit jelent a required?

**Válasz:**

Böngészőoldali kötelezőmező-ellenőrzés. Megkerülhető, ezért szerveroldali validálás is kell.

**Hétköznapi példa:**

A csillagozott mezőt az ügyintézőnek is ellenőriznie kell.

**Kódpélda:**

```
<input type="email" required>
```

### 58. Miben térnek el az input típusok?

**Válasz:**

text szöveg, number szám, email email-formátum; checkbox független választás, azonos nevű radio egyet választ csoportból.

**Hétköznapi példa:**

Egy menü választható, de több extra kérhető.

**Kódpélda:**

```
<input type="radio" name="menu" value="vegan">
```

### 59. Mire jó az input name?

**Válasz:**

A beküldött adat kulcsa. Name nélküli vezérlő általában kimarad a natív FormData-ból.

**Hétköznapi példa:**

Névtelen válasznál nem tudni, melyik mezőhöz tartozik.

**Kódpélda:**

```
<input name="city" value="Budapest">
```

### 60. Hogyan kapcsolsz labelt inputhoz?

**Válasz:**

A for az input id-jára mutat, vagy a label tartalmazza az inputot.

**Hétköznapi példa:**

A ruhatári biléta a megfelelő fogasra mutat.

**Kódpélda:**

```
<label for="city">City</label><input id="city">
```

### 61. Hogyan adsz hozzá dinamikus formmezőt?

**Válasz:**

DOM-elemeket létrehozva/törölve, vagy Reactben állapotból renderelve, megőrizve a labelt és validálást.

**Hétköznapi példa:**

Új vendéghez új sor a jelentkezési lapon.

**Kódpélda:**

```
const input=document.createElement('input'); form.append(input);
```

### 62. Hogyan küldhető el a formadat?

**Válasz:**

FormData közvetlenül, vagy objektummá alakítva JSON-ként. Ismétlődő nevekhez getAll, fájlokhoz multipart kellhet.

**Hétköznapi példa:**

A tartalomhoz megfelelő borítékot választasz.

**Kódpélda:**

```
JSON.stringify(Object.fromEntries(new FormData(form)))
```

## React

### 63. Mi a React?

**Válasz:**

Komponensalapú deklaratív UI-könyvtár, state és props alapján. Nem teljes backend.

**Hétköznapi példa:**

LEGO-elemekből épül a felület.

**Kódpélda:**

```
function Welcome(){return <h1>Hello</h1>;}
```

### 64. Mi a virtuális DOM?

**Válasz:**

A felület memóriabeli leírása, amely segít a DOM-frissítések megállapításában. Nem mindig automatikusan gyorsabb.

**Hétköznapi példa:**

Átrendezés előtt terven nézed, melyik bútort kell mozgatni.

**Kódpélda:**

```
state → render → commit
```

### 65. Mi a komponensalapú architektúra?

**Válasz:**

Újrahasználható komponensek propsot kapnak, állapotot kezelhetnek és egymásba építhetők.

**Hétköznapi példa:**

Kenyér, sajt és feltét együtt szendvics.

**Kódpélda:**

```
<Layout><Profile /></Layout>
```

### 66. Mi a JSX?

**Válasz:**

JavaScript-szintaxiskiterjesztés HTML-szerű jelöléssel, buildkor JS-hívásokká alakul. Kapcsos zárójelben kifejezés áll.

**Hétköznapi példa:**

Olvasható rendelőlapból konyhai munkalap készül.

**Kódpélda:**

```
const title=<h1>{user.name}</h1>;
```

### 67. Mik a propsok?

**Válasz:**

Szülőtől kapott, csak olvasható bemenetek; a gyerek nem módosítja közvetlenül.

**Hétköznapi példa:**

A szakács nem írja át titokban a rendelést.

**Kódpélda:**

```
<Profile name="Ada" />
```

### 68. Hogyan használod a props destrukturálást?

**Válasz:**

A paraméterből vagy props objektumból kiemeled a mezőket.

**Hétköznapi példa:**

A csomagból külön kiveszed a névkártyát.

**Kódpélda:**

```
function Profile({name}){return <h2>{name}</h2>;}
```

### 69. Hogyan ad visszajelzést a gyerek callback prop segítségével?

**Válasz:**

A szülő függvényt ad át, a gyerek eseménykor meghívja, a szülő frissíti az állapotot.

**Hétköznapi példa:**

Csengőt nyomsz, és a szülő intézkedik.

**Kódpélda:**

```
<Button onChoose={()=>setSelected(true)} />
```

### 70. Mi a props spreading?

**Válasz:**

{...obj} külön propokként adja át a mezőket; azonos névnél a sorrend számít.

**Hétköznapi példa:**

Egész adatlapot másolsz át egyszerre.

**Kódpélda:**

```
<Profile {...user} name="Override" />
```

### 71. Hogyan adsz default propsot?

**Válasz:**

Paraméteralapértékkel, például {size=20}; hiányzó/undefined értékre működik, nullra nem.

**Hétköznapi példa:**

Méretkérés nélkül alapméretű kávé.

**Kódpélda:**

```
function Avatar({size=40}){return <img width={size} />;}
```

### 72. Miért ne módosítsd a propsot/state-et közvetlenül?

**Válasz:**

Új értéket készítünk, hogy az előző snapshot megmaradjon és a változás felismerhető legyen.

**Hétköznapi példa:**

Új szerződésváltozat, nem a régi kiradírozása.

**Kódpélda:**

```
setUser(p=>({...p,name:'Ada'}));
```

### 73. Mi a state és props különbsége?

**Válasz:**

A state saját, setterrel frissülő memória; a props kívülről kapott bemenet.

**Hétköznapi példa:**

Rendelés a props, készültségi állapot a state.

**Kódpélda:**

```
const [count,setCount]=useState(0);
```

### 74. Mire jók a useState és useEffect hookok?

**Válasz:**

useState állapotot kezel; useEffect külső rendszerrel szinkronizál render után, szükség esetén cleanup-pal. Hookot ne hívj feltételesen.

**Hétköznapi példa:**

Számláló és értesítési előfizetés: utóbbit távozáskor lemondod.

**Kódpélda:**

```
useEffect(()=>{const id=setInterval(tick,1000);return ()=>clearInterval(id);},[]);
```

### 75. Mi a reconciliation?

**Válasz:**

Render-leírások összevetése típus és key alapján, majd a szükséges DOM-módosítások commitja.

**Hétköznapi példa:**

Csak a megváltozott bevásárlótételeket intézed.

**Kódpélda:**

```
items.map(x=><li key={x.id}>{x.name}</li>)
```

### 76. Hogyan frissítesz beágyazott state-et?

**Válasz:**

Minden megváltozott szinten új objektum készül; előző értéktől függő változtatásnál updater kellhet.

**Hétköznapi példa:**

A módosított laphoz új mappaváltozat is készül.

**Kódpélda:**

```
setUser(p=>({...p,address:{...p.address,city:'Pécs'}}));
```

### 77. Miért kell új tömb a setternek?

**Válasz:**

Új referencia segíti a változás felismerését és megőrzi a régi snapshotot; push a régit módosítaná.

**Hétköznapi példa:**

Új listát adsz át a régi csendes átírása helyett.

**Kódpélda:**

```
setItems(p=>[...p,newItem]);
```

### 78. Hogyan renderelsz feltételesen?

**Válasz:**

if-fel, ternárissal vagy && kifejezéssel más JSX-et adsz vissza. null nem jelenít meg tartalmat.

**Hétköznapi példa:**

Nyitva vagy zárva táblát teszel ki.

**Kódpélda:**

```
return loggedIn ? <Profile/> : <Login/>;
```

### 79. Controlled vagy uncontrolled input?

**Válasz:**

Controlled value/checked state-ből és onChange-dzsel; uncontrolled értéke a DOM-ban él.

**Hétköznapi példa:**

Központilag vezérelt vagy helyben írható tábla.

**Kódpélda:**

```
<input value={name} onChange={e=>setName(e.target.value)}/>
```

### 80. Hogyan olvasod az uncontrolled form értékeit?

**Válasz:**

Beküldéskor FormData-val vagy refen át a DOM-ból.

**Hétköznapi példa:**

Leadáskor olvasod le a papírkérdőívet.

**Kódpélda:**

```
new FormData(event.currentTarget).get('name')
```

### 81. Hogyan kapcsolsz React labelt inputhoz?

**Válasz:**

htmlFor értéke egyezzen az input id-jával, vagy a label tartalmazza az inputot.

**Hétköznapi példa:**

Az azonos számú biléta a megfelelő fogast jelöli.

**Kódpélda:**

```
<label htmlFor="email">Email</label><input id="email"/>
```

### 82. Hogyan készül React select?

**Válasz:**

Controlled: value/onChange. Uncontrolled: defaultValue. A kiválasztást a selecten, nem option selecteddel állítjuk.

**Hétköznapi példa:**

Központi választás vagy helyben kitöltött menülap.

**Kódpélda:**

```
<select defaultValue="hu"><option value="hu">Magyar</option></select>
```

### 83. Mire való a Vite dev proxy?

**Válasz:**

Kijelölt útvonalakat továbbít a backendhez. Relatív /api URL-t használj; productionben külön konfiguráció kell.

**Hétköznapi példa:**

A recepció továbbkapcsol a megfelelő osztályhoz.

**Kódpélda:**

```
server:{proxy:{'/api':'http://localhost:3001'}}
```

### 84. Mi az utasítás és kifejezés különbsége?

**Válasz:**

Kifejezés értéket ad, utasítás végrehajtást szervez. JSX kapcsos zárójelben kifejezés kell, nem közvetlen if.

**Hétköznapi példa:**

A válasz érték, a teendősor utasítás.

**Kódpélda:**

```
<span>{score>0?'Yes':'No'}</span>
```

## Tesztelés

### 85. Mi egy teszteset?

**Válasz:**

Meghatározott bemenet, körülmény és elvárt eredmény egy viselkedéshez.

**Hétköznapi példa:**

Megnyomod a kapucsengőt, és csörgést vársz.

**Kódpélda:**

```
expect(add(2,3)).toBe(5);
```

### 86. Miért hasznos a unit teszt?

**Válasz:**

Gyors visszajelzés kis egységekről, regresszióvédelem és refaktorálási segítség; nem teljes hibamentességi bizonyíték.

**Hétköznapi példa:**

Külön ellenőrzöd a biciklilámpát összeszerelés előtt.

**Kódpélda:**

```
expect(total([])).toBe(0);
```

### 87. Mi az assertion?

**Válasz:**

Elvárt feltételt ellenőriz, eltéréskor megbuktatja a tesztet.

**Hétköznapi példa:**

A mérleg ellenőrzi, valóban egy kiló-e a csomag.

**Kódpélda:**

```
expect(2+2).toBe(4); expect(()=>fail()).toThrow();
```

### 88. Mi az arrange–act–assert?

**Válasz:**

Előkészítés, művelet végrehajtása, eredmény ellenőrzése.

**Hétköznapi példa:**

Hozzávalók, sütés, kóstolás.

**Kódpélda:**

```
const x=2; const r=double(x); expect(r).toBe(4);
```

### 89. Mi a code coverage?

**Válasz:**

A tesztben futott sorokat, ágakat vagy függvényeket méri. A 100% sem garantál jó assertionöket.

**Hétköznapi példa:**

Minden szobában jártál, de nem próbáltál ki minden konnektort.

**Kódpélda:**

```
vitest run --coverage
```

### 90. Hogyan tesztelsz aszinkron kódot Vitesttel?

**Válasz:**

Return vagy await a Promise-ra, hogy a futtató megvárja; resolves/rejects is használható.

**Hétköznapi példa:**

Értékelés előtt megvárod a szállítást.

**Kódpélda:**

```
await expect(load()).resolves.toEqual({ok:true});
```

### 91. Mi a setup és teardown?

**Válasz:**

beforeEach/beforeAll előkészít, afterEach/afterAll takarít, hogy a tesztek ne osszanak nem kívánt állapotot.

**Hétköznapi példa:**

Főzés előtt és után tiszta munkapult.

**Kódpélda:**

```
afterEach(()=>vi.restoreAllMocks());
```

### 92. Mikor toBe és mikor toEqual?

**Válasz:**

toBe Object.is szerint hasonlít; toEqual mély szerkezetet. Két külön azonos tartalmú objektum toEqual lehet.

**Hétköznapi példa:**

Ugyanaz a bögre vagy két egyező mintájú bögre?

**Kódpélda:**

```
expect({a:1}).toEqual({a:1});
```

## Firebase adatbázis

### 93. Mi a Firebase Realtime Database?

**Válasz:**

Felhős NoSQL JSON-fa valós idejű szinkronizálással, SDK-kkal és biztonsági szabályokkal.

**Hétköznapi példa:**

Közös tábla mindenkinél frissül.

**Kódpélda:**

```
onValue(ref(db,'scores'),s=>render(s.val()));
```

### 94. Hogyan tárol adatot a Realtime Database?

**Válasz:**

Hierarchikus kulcs-érték JSON-fában, útvonalakkal, nem SQL-táblákban.

**Hétköznapi példa:**

Fiókok útvonala vezet a keresett irathoz.

**Kódpélda:**

```
users/u1/name → 'Ada'
```

### 95. Milyen a Firebase REST CRUD?

**Válasz:**

.json útvonalakon GET olvas, POST kulcsot készít, PUT cserél, PATCH részlegesen módosít, DELETE töröl.

**Hétköznapi példa:**

Egy irattári rekesz több művelettel kezelhető.

**Kódpélda:**

```
GET https://DATABASE.firebaseio.com/users.json
```

### 96. Mire valók a Firebase Security Rules?

**Válasz:**

.read/.write hozzáférést és .validate adatfeltételeket szabályoz. Kliensellenőrzés nem helyettesíti.

**Hétköznapi példa:**

Portás a hozzáférést, ügyintéző az adatlapot ellenőrzi.

**Kódpélda:**

```
".read": "auth != null"
```

### 97. Miért gond a mély beágyazás?

**Válasz:**

Felesleges nagy letöltést és bonyolult jogosultságot okozhat. Lapítás, ID-hivatkozások és célzott denormalizálás segít.

**Hétköznapi példa:**

Egy lapért ne vidd haza az egész irattárat.

**Kódpélda:**

```
posts/p1 {authorId:'u1'}
```

## Hitelesítés

### 98. Miért kell authentication?

**Válasz:**

Megállapítja a személyazonosságot; a műveleti jogosultság külön ellenőrzés.

**Hétköznapi példa:**

Az igazolvány nem nyitja ki automatikusan az összes ajtót.

**Kódpélda:**

```
signInWithEmailAndPassword(auth,email,password)
```

### 99. Milyen funkciói vannak a hitelesítésnek?

**Válasz:**

Regisztráció, be/ki jelentkezés, session/token, jelszó-visszaállítás, esetleg többtényezős ellenőrzés.

**Hétköznapi példa:**

Belépő kiadása, ellenőrzése és pótlása.

**Kódpélda:**

```
createUserWithEmailAndPassword(auth,email,password)
```

### 100. Honnan tudja a szerver, hogy be vagy jelentkezve?

**Válasz:**

Ellenőrzött sessionből vagy aláírt tokenből, lejárat és kibocsátó vizsgálatával. Bemondott név nem bizonyíték.

**Hétköznapi példa:**

A portás valódi belépőt ellenőriz.

**Kódpélda:**

```
Authorization: Bearer <ID_TOKEN>
```

### 101. Authentication vagy authorization?

**Válasz:**

Előbbi: ki vagy? Utóbbi: mit tehetsz? Mindkettőt megbízható oldalon ellenőrizzük.

**Hétköznapi példa:**

Személyi igazolvány és laborbelépési jogosultság.

**Kódpélda:**

```
authenticated && resource.ownerId===user.id
```

### 102. Hogyan inicializálod a Firebase Authot?

**Válasz:**

initializeApp(config), majd getAuth(app), utána bejelentkezési műveletek.

**Hétköznapi példa:**

Épületnyitás, majd beléptetőpult beállítása.

**Kódpélda:**

```
const app=initializeApp(config); const auth=getAuth(app);
```

### 103. Hogyan érvényesít jogosultságot a Firebase?

**Válasz:**

auth.uid és tulajdonos vagy szerepkör összevetésével Security Rules-ban. Alapértelmezett tiltásból indulj.

**Hétköznapi példa:**

Csak a tulajdonos bilétája nyitja a szekrényt.

**Kódpélda:**

```
".write": "auth != null && auth.uid === $uid"
```

### 104. Milyen Firebase Auth providerek vannak?

**Válasz:**

Email/jelszó, Google, GitHub, Apple, telefon és anonim belépés például; konfigurálni kell őket.

**Hétköznapi példa:**

Többféle elfogadott igazolvány ugyanahhoz a bejárathoz.

**Kódpélda:**

```
new GoogleAuthProvider()
```

## Webalkalmazások

### 105. Mire való a React Router?

**Válasz:**

URL-eket rendel kliensoldali nézetekhez teljes újratöltés nélkül; a szervernek a mély linkeket is kezelnie kell.

**Hétköznapi példa:**

Teremváltás a múzeum elhagyása nélkül.

**Kódpélda:**

```
<Route path="/profile" element={<Profile/>}/>
```

### 106. Miért kell buildelni?

**Válasz:**

JSX/TS átalakítás, függőségfeldolgozás és optimalizált böngészős csomagok készítése.

**Hétköznapi példa:**

Előkészített hozzávalókból kiszállítható étel.

**Kódpélda:**

```
npm run build
```

### 107. Dev és production különbsége?

**Válasz:**

Dev gyors visszajelzés/HMR. Production optimalizált kiadás megfelelő konfigurációval és biztonsággal.

**Hétköznapi példa:**

Próbaelőadás vagy közönség előtti kész műsor.

**Kódpélda:**

```
npm run dev; npm run build
```

### 108. Hogyan deployolsz Firebase appot?

**Válasz:**

Build, Firebase CLI inicializálás és deploy. Hostingkönyvtár, SPA rewrite és biztonsági szabályok is kellenek.

**Hétköznapi példa:**

Kiállítást kész helyszínre viszel belépési szabályokkal.

**Kódpélda:**

```
firebase init hosting; firebase deploy
```

### 109. Mire jó a React Context?

**Válasz:**

Közös értékeket ad mély komponenseknek propsláncolás nélkül, például téma/nyelv. Nem adatbázis.

**Hétköznapi példa:**

Közös fali óra, nem kollégákon át továbbmondott idő.

**Kódpélda:**

```
useContext(ThemeContext)
```

# Workbook 3 – Java, OOP és SQL

80 kérdés • Magyar tanulóanyag

Az alkalmazás jelenlegi magyar kérdései és kidolgozott válaszai, témakörök szerint. A kérdéscímek a kvíz rövidített megfogalmazását követik. A programkódok az eredeti programozási nyelven szerepelnek.

## Java ökoszisztéma

### 1. Mi a JVM?

**Válasz:**

A JVM Java bájtkódot futtat, memóriát és szemétgyűjtést kezel. Az adott platformhoz megfelelő JVM kell.

**Hétköznapi példa:**

Szabványos receptkártyát értő kávégép.

**Kódpélda:**

```
java Hello
```

### 2. Mit jelent a Java fordítás?

**Válasz:**

A javac a .java forrásból ellenőrzés után .class bájtkódot készít; ez nem futtatás.

**Hétköznapi példa:**

A receptet gépi munkalappá alakítod, de még nem főzöl.

**Kódpélda:**

```
javac Hello.java
```

### 3. Mi a bájtkód?

**Válasz:**

A JVM köztes utasításai, nem egy konkrét CPU gépi kódja. A JVM értelmezheti vagy JIT-tel natívra fordíthatja.

**Hétköznapi példa:**

Kotta, amit különböző előadók játszhatnak.

**Kódpélda:**

```
.java → .class → JVM
```

### 4. JRE és JDK különbsége?

**Válasz:**

JRE futtatási környezet; JDK futtatás mellé fejlesztőeszközöket, például javac-ot ad. Külön JRE-csomag nem mindig érhető el.

**Hétköznapi példa:**

Felszerelt konyha vagy konyha és receptfejlesztő műhely.

**Kódpélda:**

```
javac -version
```

### 5. Mi az Iterable?

**Válasz:**

Bejárható objektum szerződése, iterator() metódussal; a for-each tudja használni.

**Hétköznapi példa:**

Névsor, amelyen egyesével végighaladhatsz.

**Kódpélda:**

```
for(String x: names) { System.out.println(x); }
```

### 6. Mi a Collection?

**Válasz:**

Elemek csoportjának interfésze, az Iterable leszármazottja. List, Set és Queue ide tartozik; Map nem.

**Hétköznapi példa:**

Kosár több elemmel, többféle rendezési szabállyal.

**Kódpélda:**

```
Collection<String> c = new ArrayList<>();
```

### 7. Mi a Map?

**Válasz:**

Egyedi kulcsokhoz értékeket rendel; nem Collection leszármazott. Egy kulcshoz egy aktuális érték tartozik.

**Hétköznapi példa:**

Ruhatári sorszámhoz tartozó kabát.

**Kódpélda:**

```
map.put("Ada", 10); map.get("Ada");
```

### 8. List, Set és Queue különbsége?

**Válasz:**

List sorrendezett, duplikációt enged. Set egyediséget biztosít. Queue feldolgozási sorrendet ad, amely nem mindig FIFO.

**Hétköznapi példa:**

Bevásárlólista, egyedi tagsági névsor, ügyfélsor.

**Kódpélda:**

```
List.of("a","a"); Set.of("a","b");
```

### 9. ArrayList vagy LinkedList?

**Válasz:**

ArrayList indexelése O(1), középső beszúrás eltolást igényel. LinkedList csomópontokat láncol, indexelt elérése O(n); ismert helyen kapcsolás olcsó.

**Hétköznapi példa:**

Számozott szekrények vagy egymásra mutató kártyák.

**Kódpélda:**

```
List<String> list = new ArrayList<>();
```

### 10. Rendezettek a Setek?

**Válasz:**

Implementációfüggő: HashSet nem garantál sorrendet, LinkedHashSet beszúrási, TreeSet rendezett sorrendet ad.

**Hétköznapi példa:**

Egy zsák, érkezési névsor és ábécés névsor különbözik.

**Kódpélda:**

```
Set<Integer> sorted = new TreeSet<>();
```

## Nyelvi elemek

### 11. Milyen vezérlési utasítások vannak Javában?

**Válasz:**

Elágazások if/switch, ciklusok for/while/do-while, break/continue/return és kivételkezelés try/catch/throw.

**Hétköznapi példa:**

Reggeli rutin: ha esik esernyő, amíg nem kész pakolás.

**Kódpélda:**

```
if(ready) return;
```

### 12. Miben térnek el a ciklusok?

**Válasz:**

while elöl tesztel, do-while hátul és legalább egyszer fut; for inicializál/feltételt néz/léptet; for-each elemeket jár be.

**Hétköznapi példa:**

Mosogatás amíg van tányér; kóstolás legalább egyszer.

**Kódpélda:**

```
for(int i=0;i<3;i++) { System.out.println(i); }
```

### 13. Miben térnek el a feltételes szerkezetek?

**Válasz:**

if-else általános boolean feltétel, switch esetválasztás, ?: két érték közötti kifejezés. Nyilas switchnél nincs átesés.

**Hétköznapi példa:**

Öltözködési döntés, mosógépprogram és rövid igen/nem választás.

**Kódpélda:**

```
String result=ok?"Yes":"No";
```

### 14. Mi a while?

**Válasz:**

Minden kör előtt ellenőriz, igaz feltételnél fut; akár egyszer sem hajtódik végre.

**Hétköznapi példa:**

Csak addig mosogatsz, amíg maradt piszkos tányér.

**Kódpélda:**

```
while(i<3) { i++; }
```

### 15. Hogyan lépsz ki egy ciklusból?

**Válasz:**

break a legbelső ciklusból/switchből lép ki; continue csak következő iterációra ugrik. return a metódust zárja.

**Hétköznapi példa:**

Megtalált kulcs után abbahagyod a keresést.

**Kódpélda:**

```
if(found) break;
```

### 16. Mit jelent a var?

**Válasz:**

Helyi változó statikus típusát a fordító a kezdőértékből következteti. Nem dinamikus, nem automatikusan final.

**Hétköznapi példa:**

A doboz címkéjét a tartalmából töltöd ki, de a címke rögzül.

**Kódpélda:**

```
var n=3; n=4;
```

### 17. Mi a lambda Javában?

**Válasz:**

Funkcionális interfész egy absztrakt metódusának tömör megvalósítása. Viselkedést adhatunk át, például rendezéshez.

**Hétköznapi példa:**

A pincérnek átadott rövid munkautasítás.

**Kódpélda:**

```
names.sort((a,b)->a.compareTo(b));
```

## Típusrendszer

### 18. Mik a primitív típusok?

**Válasz:**

byte, short, int, long, float, double, char, boolean. A char 16 bites UTF-16 kódegység.

**Hétköznapi példa:**

Egyszerű adatlapmezők: életkor, magasság, igen/nem.

**Kódpélda:**

```
int age=20; boolean ready=true;
```

### 19. Primitív és referenciatípus különbsége?

**Válasz:**

Primitív értéket, referencia objektumhivatkozást vagy nullt tárol. Java mindig érték szerint ad át, a referenciát is másolja.

**Hétköznapi példa:**

Szám másolása vagy egy lakcím másolása: utóbbi nem másolja a házat.

**Kódpélda:**

```
Player b=a; // same referenced object
```

### 20. Mi az osztály?

**Válasz:**

Objektumok állapotát és viselkedését meghatározó típus, mezőkkel, metódusokkal, konstruktorokkal.

**Hétköznapi példa:**

Ház tervrajza, nem maga a ház.

**Kódpélda:**

```
class Player { int score; }
```

### 21. Mi az objektum?

**Válasz:**

Futásidejű példány saját identitással és állapottal; tömbök is objektumok.

**Hétköznapi példa:**

A tervből épített konkrét ház.

**Kódpélda:**

```
Player p=new Player();
```

### 22. Mi a konstruktor?

**Válasz:**

Példányt inicializál, neve az osztály neve, nincs visszatérési típusa. Túlterhelhető.

**Hétköznapi példa:**

Tagsági kártyát kitöltesz kiadáskor.

**Kódpélda:**

```
Player(String n) { name=n; }
```

### 23. Mi az enum?

**Válasz:**

Előre meghatározott, véges névvel ellátott értékkészletet képviselő típus, mezőkkel és metódusokkal is bővíthető.

**Hétköznapi példa:**

A közlekedési lámpa megengedett színei.

**Kódpélda:**

```
enum Light { RED, YELLOW, GREEN }
```

### 24. Class és enum különbsége?

**Válasz:**

Osztályból szokásosan új példányokat készíthetsz; enum példányai a deklarált konstansokra korlátozottak.

**Hétköznapi példa:**

Házterv sok házhoz, lámpaszínek rögzített listája.

**Kódpélda:**

```
Light l=Light.RED;
```

### 25. Class és record különbsége?

**Válasz:**

A record adathordozó speciális final osztály: komponensek, accessorok, equals/hashCode/toString generálódnak. A final referencia nem teszi mélyen immutábilissá.

**Hétköznapi példa:**

Előre nyomtatott adatlap a teljesen szabad jegyzetfüzettel szemben.

**Kódpélda:**

```
record Point(int x,int y) {}
```

### 26. Mi az interfész és miért hasznos?

**Válasz:**

Szerződés, amely megadja az elvárt műveleteket; külön megvalósítások felcserélhetőségét és csatoláscsökkentést segíti.

**Hétköznapi példa:**

Szabványos konnektor többféle készülékhez.

**Kódpélda:**

```
interface Payable { void pay(); }
```

### 27. Mi az öröklés?

**Válasz:**

Leszármazott osztály átvesz és bővíthet/felülírhat örökölhető viselkedést; valódi is-a kapcsolatot modellezzen.

**Hétköznapi példa:**

Speciális jármű is jármű, de saját viselkedéssel.

**Kódpélda:**

```
class Dog extends Animal {}
```

### 28. Van többszörös öröklés Javában?

**Válasz:**

Osztályból egy közvetlen ős lehet, de több interfész implementálható; ütköző default metódust fel kell oldani.

**Hétköznapi példa:**

Egy fő tervből épülsz, de több szabványnak megfelelhetsz.

**Kódpélda:**

```
class Robot implements Movable, Chargeable {}
```

### 29. Mi a static tag?

**Válasz:**

Az osztályhoz, nem egy példányhoz tartozik. Static nem jelent módosíthatatlanságot.

**Hétköznapi példa:**

Közös osztálytermi számláló a saját füzetek mellett.

**Kódpélda:**

```
static int count=0;
```

### 30. Használhat static metódus példánytagot?

**Válasz:**

Igen, megfelelő objektumreferencián át; nincs saját this statikus környezetben.

**Hétköznapi példa:**

Az ügyintéző csak konkrét diák iratával éri el annak adatait.

**Kódpélda:**

```
static int read(Player p){return p.score;}
```

### 31. Mit jelent a final?

**Válasz:**

Változó egyszer kap értéket, metódus nem felülírható, osztály nem örökölhető. Az objektum belseje még változhat.

**Hétköznapi példa:**

A címkártyát nem irányítod át, de a ház bútorait átrendezheted.

**Kódpélda:**

```
final List<String> x=new ArrayList<>(); x.add("Ada");
```

### 32. Mit jelent az abstract?

**Válasz:**

Absztrakt osztály nem példányosítható közvetlenül; absztrakt metódusnak nincs törzse és konkrét leszármazott valósítja meg.

**Hétköznapi példa:**

Egy befejezetlen tervet a konkrét háztípusnak kell kiegészítenie.

**Kódpélda:**

```
abstract class Shape { abstract double area(); }
```

### 33. Mi az overloading?

**Válasz:**

Azonos név, eltérő paraméterlista. Csak a visszatérési típus eltérése nem elég; a fordító választ szignatúrát.

**Hétköznapi példa:**

Rendelés egy étellel vagy étellel és itallal.

**Kódpélda:**

```
int sum(int a,int b); double sum(double a,double b);
```

### 34. Mi az overriding?

**Válasz:**

Örökölt példánymetódus kompatibilis felülírása; a futásidejű objektumtípus dönt. Static metódus elrejtődik, nem felülíródik.

**Hétköznapi példa:**

Biciklis és autós futár másképp kézbesít.

**Kódpélda:**

```
@Override public String toString(){return "Player";}
```

### 35. Overloading vagy overriding?

**Válasz:**

Túlterhelés eltérő paraméterlista, fordításkori választás; felülírás örökölt példánymetódus új viselkedése, futásidejű választás.

**Hétköznapi példa:**

Más adatlistájú foglalás vagy más dolgozó által végzett takarítás.

**Kódpélda:**

```
sum(int,int) vs sum(double,double)
```

### 36. Mi a null?

**Válasz:**

Nem jelöl objektumot; nem üres String vagy nulla. Primitívhez nem rendelhető, példánymetódus hívása rajta NullPointerException.

**Hétköznapi példa:**

Üres telefonszámmező: nincs kit hívni.

**Kódpélda:**

```
String s=null; // s.length() throws
```

### 37. Mik a hozzáférési módosítók?

**Válasz:**

public legszélesebb, protected csomag és leszármazott szabályokkal, package-private csomag, private szűk belső elérés. Osztály- és modulláthatóság is számít.

**Hétköznapi példa:**

Nyilvános faliújság, részlegi irat és belső fiók.

**Kódpélda:**

```
private int score; public int getScore(){return score;}
```

### 38. Mi az alap hozzáférés osztálytag esetén?

**Válasz:**

Módosító nélkül package-private, ugyanazon csomagból érhető el. Interfészre eltérő szabályok vannak.

**Hétköznapi példa:**

Külön jelölés nélküli részlegen belüli üzenet.

**Kódpélda:**

```
class Player { int score; }
```

### 39. Mire jó az equals?

**Válasz:**

Logikai egyenlőség az osztály szabályai szerint. Object alapból azonosságot néz; felülíráskor hashCode szerződésére is ügyelj.

**Hétköznapi példa:**

Két külön kártya azonos tagságot is jelenthet.

**Kódpélda:**

```
"Java".equals("Java")
```

### 40. Mi a == és equals különbsége?

**Válasz:**

Referenciánál == objektumazonosságot, equals osztály szerinti egyenlőséget néz. Primitív == értéket hasonlít.

**Hétköznapi példa:**

Ugyanaz a bögre vagy egyforma feliratú bögrék?

**Kódpélda:**

```
new String("x").equals(new String("x")) // true
```

### 41. Mi a long és Long különbsége?

**Válasz:**

long primitív 64 bites egész; Long referencia típusú wrapper, lehet null és használható generikus gyűjteményben. Autoboxing köztük átalakít.

**Hétköznapi példa:**

Egy szám vagy a számot tartalmazó felcímkézett doboz.

**Kódpélda:**

```
List<Long> ids = new ArrayList<>();
```

### 42. Melyik tárol nagyobb számot: long vagy Long?

**Válasz:**

Ugyanaz a 64 bites előjeles tartományuk, −2^63-tól 2^63−1-ig. Long nem növeli meg.

**Hétköznapi példa:**

A díszdoboz nem növeli meg a beleférő mérőskálát.

**Kódpélda:**

```
Long.MAX_VALUE == 9223372036854775807L
```

### 43. Mondj java.util alcsomagokat!

**Válasz:**

Például java.util.concurrent, java.util.stream, java.util.function, java.util.regex. Az ArrayList osztály, nem csomag; a wildcard import nem rekurzív.

**Hétköznapi példa:**

Könyvtári részlegek és a bennük lévő könyvek nem ugyanazok.

**Kódpélda:**

```
import java.util.stream.Stream;
```

## Tervezési elvek

### 44. Mi a Single Responsibility Principle?

**Válasz:**

Egy modulnak egy összefüggő felelőssége, egy változási oka legyen; nem azt jelenti, hogy csak egy metódusa lehet.

**Hétköznapi példa:**

A szakács főz, a könyvelő számláz.

**Kódpélda:**

```
InvoiceCalculator + InvoiceRepository
```

### 45. Mi az Interface Segregation Principle?

**Válasz:**

A kliens ne függjön nem használt műveletektől; kisebb, célzott interfészeket használjunk.

**Hétköznapi példa:**

A kenyérpirítónak nem kell nyomtatási gomb.

**Kódpélda:**

```
interface Printable { void print(); }
```

### 46. Miért composition over inheritance?

**Válasz:**

Objektumok együttműködésével állítunk össze viselkedést merev öröklési hierarchia helyett, ha nincs valódi is-a kapcsolat.

**Hétköznapi példa:**

Az autóban motor van; az autó nem egy motor.

**Kódpélda:**

```
class Car { private Engine engine; }
```

### 47. Mi a model class?

**Válasz:**

A tartomány adatát és kapcsolódó szabályait reprezentálja; például User vagy Order. Nem szükségszerűen csak mezőkből áll.

**Hétköznapi példa:**

A rendelés adatlapja tartalmazza a tételeket és állapotot.

**Kódpélda:**

```
class Order { List<Item> items; }
```

### 48. Mi a service class?

**Válasz:**

Üzleti műveleteket valósít meg vagy koordinál modellek és repositoryk között. Nem kizárólag adattároló.

**Hétköznapi példa:**

Az ügyintéző több irat és részleg munkáját fogja össze.

**Kódpélda:**

```
orderService.placeOrder(request);
```

### 49. Mi az Open/Closed Principle?

**Válasz:**

Bővítésre nyitott, módosításra zárt: új viselkedést stabil kód átírása nélkül lehet hozzáadni megfelelő absztrakcióval.

**Hétköznapi példa:**

Új feltétet adhatsz a pizzához a sütő átépítése nélkül.

**Kódpélda:**

```
interface Discount { double apply(double price); }
```

### 50. Mi a Liskov Substitution Principle?

**Válasz:**

Az altípus helyettesíthesse az alaptípust a szerződés és elvárt viselkedés megsértése nélkül.

**Hétköznapi példa:**

A csereizzó ugyanabban a foglalatban az elvárt módon működjön.

**Kódpélda:**

```
List<String> xs = new ArrayList<>();
```

### 51. Mi a Dependency Inversion Principle?

**Válasz:**

Magas és alacsony szintű modulok absztrakciótól függjenek, ne a magas szint a konkrét részlettől. A DI megvalósítási eszköz lehet.

**Hétköznapi példa:**

A készülék konnektorszabványtól függ, nem egy konkrét erőműtől.

**Kódpélda:**

```
Service(Repository repository) { this.repository=repository; }
```

### 52. Mik a GoF tervezési minták?

**Válasz:**

Visszatérő objektumorientált problémák bevált megoldásleírásai, például Strategy, Factory Method, Observer, Adapter; nem kész univerzális kód.

**Hétköznapi példa:**

Bevált építészeti elrendezések, nem minden házhoz ugyanaz a terv.

**Kódpélda:**

```
Strategy: interchangeable pricing algorithms
```

### 53. Milyen kockázatai vannak a GoF mintáknak?

**Válasz:**

Túlhasználatuk fölös absztrakciót, bonyolultságot és karbantartási terhet okozhat. Valós problémára válassz mintát.

**Hétköznapi példa:**

Egy polchoz nem kell felhőkarcoló tartószerkezete.

**Kódpélda:**

```
Simple condition before introducing a strategy hierarchy
```

### 54. Mi a YAGNI?

**Válasz:**

You Aren't Gonna Need It: ne építs előre nem szükséges funkciót; a jelenlegi követelményeket teljesítsd.

**Hétköznapi példa:**

Ne építs garázst egy elképzelt jövőbeli busznak.

**Kódpélda:**

```
Implement today's required export, not ten unused formats
```

### 55. Mi a SLAP?

**Válasz:**

Single Level of Abstraction Principle: egy metódus lépései nagyjából azonos absztrakciós szinten legyenek.

**Hétköznapi példa:**

A recept fő lépései közé ne keverj csavarhúzó-gyártási részleteket.

**Kódpélda:**

```
validate(); calculate(); save();
```

### 56. Mi a KISS?

**Válasz:**

A követelményt teljesítő legegyszerűbb érthető megoldást válaszd, nem a szükséges hibakezelés elhagyását.

**Hétköznapi példa:**

Bevásárlólista egy cetlin, nem tízlépcsős engedélyezés.

**Kódpélda:**

```
Readable helper methods instead of clever one-liners
```

### 57. Mi a Repository Pattern?

**Válasz:**

Adatelérést rejtő absztrakció, amely tartományi objektumok gyűjteményszerű elérését adja, elválasztva a tárolási részleteket.

**Hétköznapi példa:**

Könyvtárostól kéred a könyvet, nem te keresed a raktári rendszert.

**Kódpélda:**

```
repository.findById(id);
```

### 58. Mi a CRUD interfész?

**Válasz:**

Create, Read, Update, Delete műveletek szerződése; megvalósítása többféle tároló mögött lehet.

**Hétköznapi példa:**

Irattár: hozzáadás, olvasás, javítás, törlés.

**Kódpélda:**

```
create(x); find(id); update(x); delete(id);
```

## Unit tesztelés

### 59. Miért jó a unit teszt?

**Válasz:**

Kis egységek gyors ellenőrzése, regressziójelzés, refaktorálási biztonság. Integrációs tesztet nem vált ki.

**Hétköznapi példa:**

Csengőt külön próbálsz ki, de végül a biciklit is teszteled.

**Kódpélda:**

```
assertEquals(4,add(2,2));
```

### 60. Mi a JUnit?

**Válasz:**

Java automatizált tesztkeretrendszer annotációkkal, assertionökkel és futtatással; Jupiter például @Test-et használ.

**Hétköznapi példa:**

Automata ellenőrzőpad előre megadott elvárásokkal.

**Kódpélda:**

```
@Test void adds(){assertEquals(4,2+2);}
```

### 61. Mi a paraméterezett teszt?

**Válasz:**

Ugyanazt a tesztlogikát több bemenettel és elvárt eredménnyel futtatja, ismételt kód nélkül.

**Hétköznapi példa:**

Ugyanazon mérlegen több csomagot ellenőrzöl.

**Kódpélda:**

```
@ParameterizedTest @ValueSource(ints={1,2,3})
```

### 62. Milyen NUnit-paraméterezési lehetőségek vannak?

**Válasz:**

NUnit a .NET világához tartozik: TestCase, TestCaseSource, Values, Range, ValueSource és kombinációs attribútumok. Java megfelelője lehet JUnit paraméterezés.

**Hétköznapi példa:**

Másik műhelyben más néven fut ugyanaz a többmintás ellenőrzés.

**Kódpélda:**

```
[TestCase(2,3,5)] // NUnit / C#
```

### 63. Mi a mocking?

**Válasz:**

Tesztdupla helyettesít függőséget és elvárt interakciókat ellenőrizhet, hogy a vizsgált egység izolálható legyen.

**Hétköznapi példa:**

Próbapartnerrel gyakorolsz a valódi ügyfél helyett.

**Kódpélda:**

```
verify(emailSender).send(message);
```

### 64. Mock, stub és fake különbsége?

**Válasz:**

Stub előre adott válaszokat ad; mock interakciós elvárásokat ellenőriz; fake egyszerű működő helyettesítő, például memóriabeli repository. Terminológia eszközfüggő lehet.

**Hétköznapi példa:**

Bemondott válasz, ellenőrző próbapartner és működő játékbolt.

**Kódpélda:**

```
FakeRepository stores test records in memory
```

## SQL adatbázisok

### 65. Mi a relációs adatbázis előnye és hátránya?

**Válasz:**

Táblák, kapcsolatok és megszorítások biztosítanak rendezett adatot, SQL-t és tranzakciókat; kötött séma és összetett joinok költséget jelenthetnek.

**Hétköznapi példa:**

Kapcsolt, szabályozott nyilvántartások, nem szabad cetlik.

**Kódpélda:**

```
Customers(id) ← Orders(customer_id)
```

### 66. Hogyan kapcsolsz entitásokat relációs modellben?

**Válasz:**

Idegen kulccsal; 1:N-nél az N oldalon, N:M-nél jellemzően kapcsolótáblával és két FK-val.

**Hétköznapi példa:**

Diákok és kurzusok között beiratkozási lista.

**Kódpélda:**

```
enrolments(student_id,course_id)
```

### 67. Mi az adatbázistábla?

**Válasz:**

Séma szerinti oszlopok és sorok halmaza. Sorok sorrendje ORDER BY nélkül nem garantált.

**Hétköznapi példa:**

Nyilvántartó füzet azonos mezőkkel minden bejegyzésnél.

**Kódpélda:**

```
users(id,name,email)
```

### 68. Mi a primary key?

**Válasz:**

Egy sort egyedileg azonosító nem null kulcs, egy vagy több oszlopból.

**Hétköznapi példa:**

Egyedi személyi azonosító, nem csak keresztnév.

**Kódpélda:**

```
id INTEGER PRIMARY KEY
```

### 69. Mi a foreign key?

**Válasz:**

Másik vagy ugyanazon tábla megfelelő kulcsára hivatkozó megszorítás, referenciális integritást biztosít.

**Hétköznapi példa:**

A rendelés ügyfélszáma létező ügyfélhez tartozzon.

**Kódpélda:**

```
customer_id REFERENCES customers(id)
```

### 70. Mit jelent az SQL?

**Válasz:**

Structured Query Language: relációs adatok definíciójára, lekérdezésére és módosítására használt nyelv.

**Hétköznapi példa:**

Szabványos kérvény-nyelv az irattár számára.

**Kódpélda:**

```
SELECT name FROM users;
```

### 71. Mondj SQL-adatbázisokat!

**Válasz:**

PostgreSQL, MySQL, SQLite, Microsoft SQL Server és Oracle Database például. A szolgáltatás és a konkrét SQL-dialektus eltérhet.

**Hétköznapi példa:**

Külön könyvtárak hasonló, de nem teljesen azonos szabályrendszerrel.

**Kódpélda:**

```
SQLite local file; PostgreSQL server
```

### 72. Mik az SQL-adattípusok?

**Válasz:**

Oszlopok tárolt értékeit szabályozzák: egész, szöveg, dátum, decimális stb. Típusnév és viselkedés adatbázisonként eltérhet, SQLite különösen rugalmas.

**Hétköznapi példa:**

Külön doboz számnak, szövegnek és dátumnak, gyártónként eltérő címkével.

**Kódpélda:**

```
name VARCHAR(100), price DECIMAL(10,2)
```

### 73. Mik az SQL constraints?

**Válasz:**

Adatintegritási szabályok: PRIMARY KEY, FOREIGN KEY, UNIQUE, NOT NULL, CHECK. Nem csak UI-validálás.

**Hétköznapi példa:**

A raktári kapu nem engedi be a szabálytalan csomagot.

**Kódpélda:**

```
age INTEGER CHECK(age>=0)
```

### 74. Hogyan érsz el SQL-adatbázist Javából?

**Válasz:**

JDBC és adatbázis-driver segítségével Connection, PreparedStatement, ResultSet használható; ORM is épülhet rá. Paraméterezés véd az SQL-injectiontől.

**Hétköznapi példa:**

Szabványos csatlakozóhoz megfelelő adaptert választasz.

**Kódpélda:**

```
connection.prepareStatement("SELECT * FROM users WHERE id=?");
```

### 75. Hogyan hozol létre SQL-táblát?

**Válasz:**

CREATE TABLE név (oszlop típus megszorítás, ...). A séma határozza meg a sorok szerkezetét.

**Hétköznapi példa:**

Üres nyilvántartó füzetet készítesz elő oszlopcímekkel.

**Kódpélda:**

```
CREATE TABLE users(id INTEGER PRIMARY KEY, name TEXT NOT NULL);
```

### 76. Hogyan szúrsz be SQL-sort?

**Válasz:**

INSERT INTO tábla (oszlopok) VALUES (értékek); paraméterekkel biztonságos adatot átadni.

**Hétköznapi példa:**

Új bejegyzés kerül a nyilvántartásba.

**Kódpélda:**

```
INSERT INTO users(name) VALUES (?);
```

### 77. Hogyan módosítasz SQL-sort?

**Válasz:**

UPDATE tábla SET oszlop=érték WHERE feltétel. WHERE nélkül minden sor érintett lehet.

**Hétköznapi példa:**

Egy megadott sorszámú bejegyzést javítasz.

**Kódpélda:**

```
UPDATE users SET name=? WHERE id=?;
```

### 78. Hogyan törölsz SQL-sorokat?

**Válasz:**

DELETE FROM tábla WHERE feltétel. WHERE nélkül minden sor törlődhet; a tábla megmarad.

**Hétköznapi példa:**

Kiveszel bejegyzéseket, de a füzetet nem dobod ki.

**Kódpélda:**

```
DELETE FROM users WHERE id=?;
```

### 79. Hogyan kérdezel le SQL-ben?

**Válasz:**

SELECT oszlopok FROM tábla, opcionális WHERE, GROUP BY, HAVING, ORDER BY és lapozás. ORDER BY ad garantált sorrendet.

**Hétköznapi példa:**

Megkéred az irattárost a megadott feltételű névsorra.

**Kódpélda:**

```
SELECT name FROM users WHERE active=1 ORDER BY name;
```

### 80. Hogyan és mikor joinolsz SQL-táblákat?

**Válasz:**

Kapcsolódó adatokat JOIN ... ON feltétellel egyesítesz. INNER csak egyezőket, LEFT a bal oldal összes sorát is megtartja nullokkal.

**Hétköznapi példa:**

Ügyféllistához rendeled a rendeléseket, akár rendelés nélküli ügyfelekkel is.

**Kódpélda:**

```
SELECT u.name,o.id FROM users u LEFT JOIN orders o ON o.user_id=u.id;
```

# Workbook 4 – Haladó DevOps

52 kérdés • Magyar tanulóanyag

A workbook-4.zip fájlban található docs/module_advanced_devops.md összes kérdésének magyar kidolgozása, az eredeti sorrendben. Minden kérdéshez válasz, hétköznapi példa és kód- vagy gyakorlati példa tartozik. A parancsok szemléltető példák; Linuxot, illetve a megfelelő eszközök telepítését és szükség esetén beállított felhőhozzáférést feltételeznek.

## Linux

### 1. Milyen virtualizációs technológiákat ismersz?

Válasz:
A virtualizáció fizikai erőforrásokból elkülönített futtatási környezeteket hoz létre. Virtuális gépeknél egy hypervisor kezeli a vendégrendszereket, amelyek saját kernellel működnek. Az 1-es típusú hypervisor közvetlenül a hardveren működik, például VMware ESXi; a 2-es típus egy gazda operációs rendszeren fut, például VirtualBox. Linuxon gyakori a KVM és QEMU együttese. A konténerek operációs rendszer szintű virtualizációt használnak: elkülönített folyamatok, amelyek a gazda kernelét osztják meg. Példák: Docker és LXC.

Hétköznapi példa:
A virtuális gépek külön házak saját berendezésekkel; a konténerek egy közös épület külön lakásai, közös alapinfrastruktúrával.

Gyakorlati példa:
    docker run --rm hello-world
Ez konténert indít. A VirtualBoxban létrehozott Ubuntu ezzel szemben teljes vendég operációs rendszer.

### 2. Milyen parancssori szövegfeldolgozó eszközöket ismersz?

Válasz:
A cat fájltartalmat ír ki, a less lapozva jelenít meg. A head és tail a fájl elejét, illetve végét mutatja. A grep mintára keres, a sed szöveget alakít át, az awk mezőket és sorokat dolgoz fel. A cut oszlopokat emel ki, a sort rendez, a uniq szomszédos ismétlődéseket kezel, a wc sorokat, szavakat vagy bájtokat számol. A pipe (|) egyik parancs kimenetét a következő bemenetére kapcsolja.

Hétköznapi példa:
Egy névsort először megszűrsz, majd sorba rendezel, végül megszámolod a megmaradt neveket.

Kódpélda:
    grep 'ERROR' app.log | sort | uniq -c
    tail -f app.log
    awk -F, '{print $1}' users.csv
Az utolsó példa egyszerű, idézőjelekbe tett vesszőket nem tartalmazó CSV-re megfelelő.

### 3. Hogyan időzítenél egy parancsot minden vasárnap éjfélre?

Válasz:
Cronnal ismétlődő feladatot állítok be. A crontab öt időmezője: perc, óra, hónap napja, hónap, hét napja. A vasárnap 00:00 azt jelenti, hogy szombatról vasárnapra virradó éjfélkor fut. A cron környezete korlátozott lehet, ezért teljes elérési utakat és naplózást használok. Az időzítésnél ellenőrzöm a használt időzónát. Alternatíva a systemd timer.

Hétköznapi példa:
Beállítasz egy heti ébresztőt vasárnap 00:00-ra.

Kódpélda:
    crontab -e
Majd a felhasználó crontabjába:
    0 0 * * 0 /home/anna/scripts/backup.sh >> /home/anna/backup.log 2>&1

### 4. Hogyan ellenőrzöd a memóriát, a lemezterületet és a CPU-erőforrásokat?

Válasz:
A free -h a memória és swap állapotát mutatja; az available oszlop segít megbecsülni az új alkalmazások számára használható memóriát. A df -h a fájlrendszerek szabad helyét, a du könyvtárak helyfoglalását mutatja. A lscpu a CPU felépítését, az nproc az elérhető feldolgozóegységek számát jelzi. A top vagy htop az aktuális terhelést és folyamatokat mutatja. A szabad kapacitás és a pillanatnyi kihasználtság külön fogalom.

Hétköznapi példa:
Megnézed, mekkora a raktár, mennyi üres polc van, és mennyire elfoglaltak a dolgozók.

Kódpélda:
    free -h
    df -h
    du -sh /var/log
    lscpu
    nproc
    top

### 5. Mi a hard link és a szimbolikus link?

Válasz:
A hard link ugyanahhoz az inode-hoz, vagyis fájlrendszerbeli objektumhoz ad másik nevet. Az egyik név törlése után a másikon elérhető marad az adat; a tárhely akkor szabadulhat fel, ha nincs több hard link és nyitott hivatkozás. Hard link általában nem mutathat másik fájlrendszerre, könyvtárra pedig rendszerint nem készíthető. A szimbolikus link külön objektum, amely egy elérési utat tárol. Mutathat könyvtárra és más fájlrendszerre is; a cél törlésekor törött link maradhat.

Hétköznapi példa:
A hard link ugyanannak a szobának egy másik bejárata. A szimbolikus link egy útbaigazító tábla a szobához.

Kódpélda:
    ln eredeti.txt masik-nev.txt
    ln -s eredeti.txt hivatkozas.txt
    ls -li

### 6. Mik a szolgáltatások Linuxban?

Válasz:
A szolgáltatások rendszerfeladatokat ellátó, rendszerint háttérben működő programok, például webszerverek, SSH-kiszolgálók vagy naplógyűjtők. Sok disztribúcióban a systemd kezeli őket service unitokkal: elindítja, leállítja, felügyeli, és igény szerint újraindítja őket. A start most indítja el a szolgáltatást, az enable az automatikus indításhoz kapcsolódó beállítást végzi el. Léteznek rövid életű, egyszeri feladatot végző szolgáltatások is.

Hétköznapi példa:
Az épület portása folyamatosan dolgozik a háttérben; a vezetőség szabályozza, mikor álljon szolgálatba.

Kódpélda:
    systemctl status nginx
    sudo systemctl start nginx
    sudo systemctl enable nginx
    journalctl -u nginx -n 50

### 7. Hogyan működnek a Linux-jogosultságok, és hogyan adsz csak a tulajdonosnak olvasási és írási jogot?

Válasz:
Az alapmodell három kategóriát használ: tulajdonos (user), csoport (group), mindenki más (others). Mindegyikhez olvasás (r=4), írás (w=2), végrehajtás (x=1) rendelhető. Fájlnál a 600 azt jelenti, hogy a tulajdonos olvashat és írhat, a többiek nem kapnak jogot. Könyvtáraknál az x a belépést és útvonalbejárást jelenti. A root vagy megfelelő képességű folyamatok hozzáférését ez önmagában nem zárja ki; ACL-ek is befolyásolhatják a hozzáférést.

Hétköznapi példa:
Csak a saját fiókod kulcsát adod magadnak, a munkatársak és vendégek nem kapnak hozzá kulcsot.

Kódpélda:
    chmod 600 titok.txt
    ls -l titok.txt
Az alapjogok megjelenése: -rw-------

### 8. Mi a különbség a Gi, Gb és GB között?

Válasz:
A kis b bitet, a nagy B bájtot jelöl; 1 bájt = 8 bit. A G a decimális giga előtag: 10^9. A Gi a bináris gibi előtag: 2^30. Így 1 GB = 1 000 000 000 bájt, 1 Gb = 1 000 000 000 bit, 1 GiB = 1 073 741 824 bájt. A Gi önmagában előtag; Kubernetesben memória megadásakor például az 1Gi bináris bájtmennyiséget jelöl. Hálózati sebességnél a Gb/s és GB/s között nyolcszoros különbség van.

Hétköznapi példa:
Nem mindegy, hogy a csomag darabszámát vagy dobozszámát számolod, és egy dobozba hány darab fér.

Gyakorlati példa:
1 Gb/s elméletileg 125 MB/s, protokolltöbblet nélkül.
1 GiB körülbelül 1,074 GB.

### 9. Milyen ismert Linux-konfigurációs fájlokat ismersz?

Válasz:
Az /etc/passwd felhasználói alapadatokat, az /etc/shadow jelszóhash-eket és kapcsolódó adatokat, az /etc/group csoportokat tartalmaz. Az /etc/fstab fájlrendszerek csatolását írja le. Az /etc/hosts helyi névfeloldást, az /etc/resolv.conf DNS-feloldási beállításokat tartalmazhat. Az SSH-kiszolgáló beállítása gyakran /etc/ssh/sshd_config. A sudo szabályai /etc/sudoers és /etc/sudoers.d/ alatt vannak. A shell beállításai lehetnek ~/.bashrc és /etc/profile alatt. Egyes fájlokat szolgáltatások automatikusan generálnak.

Hétköznapi példa:
Az épületnek külön lakónyilvántartása, kulcskezelési szabályzata és közműbeállítása van.

Kódpélda:
    cat /etc/hosts
    cat /etc/fstab
    sudo visudo
A sudo szabályait a visudo szintaxisellenőrzése mellett célszerű szerkeszteni.

### 10. Mire való a set beépített parancs, és mely kapcsolói gyakoriak?

Válasz:
Bashben a set shellopciókat és pozicionális paramétereket állít be; argumentumok nélkül változókat és függvényeket is megjelenít. A set -e bizonyos sikertelen parancsoknál kilépteti a shellt, de vannak kivételei, például feltételvizsgálatokban. A set -u hibát jelez nem beállított változó használatakor. A set -x kiírja a végrehajtott parancsokat, ezért titkokat is naplózhat. A set -o pipefail mellett a pipeline hibásnak számít, ha bármelyik tagja hibázik; státusza a jobbról első hibázó parancsé. A + kapcsoló kikapcsolja az adott opciót.

Hétköznapi példa:
Beállítod a munkafolyamat szabályait: mit tegyen hiba, hiányzó adat vagy ellenőrzési igény esetén.

Kódpélda:
    #!/usr/bin/env bash
    set -euo pipefail
    name="Anna"
    printf 'Szia, %s!\n' "$name"
    set -- alma korte
    printf '%s\n' "$1"

## Hálózatok

### 11. Mi a MAC-cím?

Válasz:
A MAC-cím az adatkapcsolati rétegben használt hálózati interfészazonosító, Ethernet esetén jellemzően 48 bites. Hat hexadecimális bájtként írjuk le. A helyi hálózaton a keretek kézbesítésében és a switch továbbítási táblájában van szerepe. Nem azonos az IP-címmel, és nem végponttól végpontig tartó internetes cím. Lehet gyárilag kiosztott vagy helyileg módosított, például adatvédelmi célból véletlenszerűsített.

Hétköznapi példa:
Egy épületen belül használt belső azonosító segít megtalálni a megfelelő munkaállomást.

Kódpélda:
    ip link show
Példa MAC-címre: 02:42:ac:11:00:02

### 12. Mi a különbség a 127.0.0.1 és 0.0.0.0 címre kötés között?

Válasz:
Szerver indításakor a bind megadja, mely helyi címen fogadjon kapcsolatokat. A 127.0.0.1 a loopback cím: az adott gépről, illetve hálózati névtérből érhető el. A 0.0.0.0 IPv4 wildcard: minden helyi IPv4 interfészen figyel. Ez önmagában nem garantál internetes elérést, mert tűzfal, útvonal, NAT és konténeres portkivezetés is számít. IPv6-nál a megfelelő wildcard cím a ::, viselkedése a beállításoktól is függ.

Hétköznapi példa:
Az egyik ügyfélszolgálat csak az irodán belüli hívásokat fogadja, a másik minden bekötött vonalon elérhető.

Kódpélda:
    python3 -m http.server 8000 --bind 127.0.0.1
    python3 -m http.server 8000 --bind 0.0.0.0
A két parancs alternatíva; ugyanazon a porton ne egyszerre futtasd őket.

### 13. Melyek az OSI-modell rétegei?

Válasz:
Az OSI hét rétegre bontja a hálózati kommunikáció feladatait, alulról felfelé:
1. Fizikai: bitek átvitele kábelen, rádión vagy optikai közegen.
2. Adatkapcsolati: helyi keretek, MAC-címzés, Ethernet.
3. Hálózati: logikai címzés és útvonalválasztás, például IP.
4. Szállítási: folyamatok közti szállítás, például TCP és UDP.
5. Viszony: kommunikációs munkamenetek kezelése.
6. Megjelenítési: adatformátumok, kódolás, tömörítés és titkosítás fogalmi helye.
7. Alkalmazási: alkalmazások hálózati protokolljai, például HTTP és DNS.
A valós internetes protokollok nem mindig illeszkednek pontosan a réteghatárokhoz.

Hétköznapi példa:
A levél tartalma, borítékolása, címzése, szállítása és fizikai mozgatása külön feladat.

Gyakorlati példa:
Egy HTTPS-kérés fogalmi útja: HTTP → TLS → TCP → IP → Ethernet → fizikai közeg. HTTP/3 esetén QUIC és UDP szerepel a szállításban.

### 14. Mi a különbség a router és a switch között?

Válasz:
A hagyományos, 2. rétegbeli switch egy helyi hálózaton MAC-címek alapján továbbít Ethernet-kereteket. A router különböző IP-hálózatok között, útválasztási táblával továbbít csomagokat. A switch VLAN-okkal több helyi hálózatot is elkülöníthet. A VLAN-ok közötti IP-forgalomhoz útválasztás kell. Léteznek 3. rétegbeli switchek, amelyek routerfunkciót is végeznek. Az otthoni router gyakran switch, Wi-Fi-hozzáférési pont és tűzfal is egyben.

Hétköznapi példa:
A switch az épületen belüli küldeményeket osztja szét, a router más épületek felé irányítja a szállítást.

Kódpélda:
    ip route
Az alapértelmezett útvonal mutatja, mely átjáró felé megy a másként nem ismert célok forgalma.

### 15. Mi a különbség a TCP és az UDP között?

Válasz:
A TCP kapcsolatközpontú, rendezett bájtfolyamot biztosít hibafelismeréssel, újraküldéssel, folyamszabályozással és torlódásvezérléssel. Nem őrzi meg az alkalmazási üzenetek határait. Az UDP önálló datagramokat küld kapcsolatfelépítés nélkül; önmagában nem garantálja a kézbesítést, sorrendet vagy ismétlésmentességet. Kisebb protokolltöbblete hasznos lehet valós idejű kommunikációnál. Az alkalmazás UDP fölött is megvalósíthat megbízhatóságot, például QUIC használatával.

Hétköznapi példa:
TCP: számozott küldemények, amelyek hiányzó darabjait újrakérik. UDP: gyorsan elküldött képeslapok visszaigazolás nélkül.

Gyakorlati példa:
SSH: TCP. DNS: gyakran UDP, de TCP-t is használ. HTTP/3: QUIC UDP fölött.

### 16. Mi a VPN?

Válasz:
A Virtual Private Network távoli gépeket vagy hálózatokat kapcsol össze logikailag elkülönített kapcsolattal. A gyakori VPN-megoldások titkosított és hitelesített alagutat építenek nyilvános hálózaton. Remote-access VPN-nél egy felhasználó kapcsolódik a céges hálózathoz; site-to-site esetben két hálózat kapcsolódik össze. Példák: WireGuard, OpenVPN és IPsec. A full tunnel minden megfelelő forgalmat, a split tunnel csak meghatározott célok forgalmát tereli a VPN-be. A VPN önmagában nem biztosít teljes anonimitást.

Hétköznapi példa:
Egy közúton haladó, lezárt céges járat összeköti az otthonodat az iroda belső rendszerével.

Gyakorlati példa:
VPN-kapcsolat után elérhetővé válhat egy belső 10.0.0.20 című szerver, amely nyilvános internetről nem érhető el.

### 17. Mi a DNS?

Válasz:
A Domain Name System elosztott, hierarchikus névrendszer. Nevekhez rekordokat rendel: A az IPv4-címet, AAAA az IPv6-címet, CNAME másik nevet, MX levelezési kiszolgálót, TXT szöveges adatot tárol. A kliens rendszerint rekurzív feloldót kérdez, amely szükség esetén a gyökér-, felső szintű és autoritatív névszerverek felé keres. A válaszokat TTL alapján gyorsítótárazhatják. A DNS nem kizárólag webcímek IP-címre fordítására szolgál.

Hétköznapi példa:
Névjegyzékben egy ember neve alapján keresed ki az elérhetőségét.

Kódpélda:
    dig example.com A
    dig example.com MX
    nslookup example.com

### 18. Mi a DHCP?

Válasz:
A Dynamic Host Configuration Protocol automatikusan ad hálózati beállításokat, például IP-címet, hálózati maszkot, átjárót és DNS-kiszolgálót. DHCPv4 esetén a kezdeti folyamat tipikusan DORA: Discover, Offer, Request, Acknowledge. A cím időkorlátos bérletként, lease-ként érkezik, amely megújítható. Foglalással egy kliens rendszerint ugyanazt a címet kaphatja. DHCPv4 szerverportja UDP 67, kliensportja UDP 68. IPv6 esetén DHCPv6 és SLAAC is használható.

Hétköznapi példa:
A recepció érkezéskor kioszt egy szobaszámot és megadja a ház használatához szükséges tudnivalókat.

Kódpélda:
    ip address show
    ip route
Ezekkel ellenőrizhető a kapott cím és az útvonal; önmagukban nem bizonyítják, hogy az adat DHCP-ből származik.

### 19. Milyen ismert portokat ismersz?

Válasz:
A port a gépen belüli hálózati végpont azonosításában segít. A TCP és UDP külön portnévteret használ. Gyakori alapértelmezések:
- 20/TCP: FTP aktív adatkapcsolat; 21/TCP: FTP vezérlés.
- 22/TCP: SSH, illetve rajta SFTP.
- 25/TCP: SMTP szerverek között; 587/TCP: levélbeküldés.
- 53/UDP és TCP: DNS.
- 67–68/UDP: DHCPv4.
- 80/TCP: HTTP.
- 110/TCP: POP3; 143/TCP: IMAP.
- 123/UDP: NTP.
- 443/TCP: HTTPS; 443/UDP: jellemzően HTTP/3.
- 465/TCP: implicit TLS-es levélbeküldés; 993/TCP: IMAPS.
- 3306/TCP: MySQL; 5432/TCP: PostgreSQL.
- 3389/TCP és UDP: RDP.
A portszám önmagában nem bizonyítja, mely alkalmazás fut mögötte.

Hétköznapi példa:
Az IP-cím az épület címe, a port az ügyintéző ablakszáma.

Kódpélda:
    ss -tuln

### 20. Melyek a privát IP-címtartományok?

Válasz:
Az RFC 1918 szerinti privát IPv4-tartományok:
- 10.0.0.0/8: 10.0.0.0–10.255.255.255.
- 172.16.0.0/12: 172.16.0.0–172.31.255.255.
- 192.168.0.0/16: 192.168.0.0–192.168.255.255.
Ezeket belső hálózatok használhatják, és a nyilvános interneten nem globálisan útválaszthatók. Interneteléréshez IPv4-nél gyakran NAT kell. A 127.0.0.0/8 loopback, a 169.254.0.0/16 link-local, nem RFC 1918 privát tartomány. IPv6-ban a unique local címek tartománya fc00::/7.

Hétköznapi példa:
Két külön cégnél is lehet 101-es iroda: a belső szám csak a saját épületében egyértelmű.

Gyakorlati példa:
192.168.1.10 privát cím; 172.32.1.10 nem tartozik az RFC 1918 tartományaihoz.

### 21. Hány használható cím van a 192.168.1.0/24 hálózatban?

Válasz:
Az IPv4-cím 32 bites, a /24 ebből 24 hálózati bitet jelöl, így 8 bit marad a hostrészre. Összesen 2^8 = 256 cím van. Hagyományos IPv4-alhálózatban a .0 hálózati cím, a .255 broadcast cím, így 254 hostcím használható: 192.168.1.1–192.168.1.254. AWS VPC alhálózatban öt címet tart fenn az AWS, ezért ott egy /24-ben 251 kiosztható cím marad.

Hétköznapi példa:
Egy 256 férőhelyes teremben két hely külön jelölési feladatot kap, ezért hagyományosan 254 marad a résztvevőknek.

Gyakorlati példa:
Maszk: 255.255.255.0.
Hagyományos használható hostok: 256 - 2 = 254.
AWS VPC-ben: 256 - 5 = 251.

### 22. Milyen hálózati hibakereső eszközöket ismersz?

Válasz:
A ping ICMP-elérhetőséget és késleltetést vizsgál; sikertelensége nem feltétlenül jelenti a gép leállását. A traceroute, tracepath és mtr az útvonal vizsgálatában segít. Az ip címeket, interfészeket és útvonalakat kezel. Az ss socketeket és figyelő portokat mutat. A dig és nslookup DNS-t vizsgál. A curl alkalmazási szintű, például HTTP-kérést küld. Az nc portelérést tesztelhet. A tcpdump és Wireshark csomagokat elemez.

Hétköznapi példa:
Külön ellenőrzöd az utat, a kaput és az ügyintézőt: attól, hogy az épület elérhető, a szolgáltatás még lehet hibás.

Kódpélda:
    ping -c 4 example.com
    ip route
    dig example.com
    curl -I https://example.com
    nc -vz example.com 443
    sudo tcpdump -ni any port 53

### 23. Mire való az ARP protokoll?

Válasz:
Az Address Resolution Protocol helyi IPv4-hálózaton egy IP-címhez keresi meg a hozzá tartozó adatkapcsolati, jellemzően MAC-címet. A kérés broadcastként indulhat, a megfelelő gép válaszol, az eredmény a szomszédtáblába kerül. Távoli cél esetén a gép jellemzően az átjáró MAC-címét keresi meg, nem a távoli szerverét. IPv6 az ARP helyett Neighbor Discovery protokollt használ. Az ARP önmagában nem hitelesít, ezért hamis válaszokkal vissza lehet élni.

Hétköznapi példa:
Az irodában megkérdezed: „Ki ül ennél a belső címen?”, és a megfelelő ember jelentkezik.

Kódpélda:
    ip neigh show

### 24. Melyek az AWS alapvető hálózati összetevői?

Válasz:
A VPC logikailag elkülönített virtuális hálózat. A subnet egy rendelkezésre állási zónában lévő címtartomány. A route table határozza meg a célhálózatok felé vezető útvonalakat. Az internet gateway internetkapcsolatot tesz lehetővé; IPv4 interneteléréshez megfelelő nyilvános cím és útvonal is kell. A nyilvános NAT gateway privát alhálózatok kimenő IPv4-interneteléréséhez használható megfelelő beállításokkal. A security group interfészhez kapcsolódó, a NACL alhálózati forgalomszűrés. VPC endpointtal támogatott szolgáltatások privát útvonalon érhetők el. VPC peering, Transit Gateway, VPN és Direct Connect hálózatokat kapcsolhat össze. A Route 53 DNS-t, az Elastic Load Balancing forgalomelosztást biztosít.

Hétköznapi példa:
A VPC egy telephely, az alhálózatok épületrészek, az útvonaltáblák útjelzők, a szűrők beléptetők.

Gyakorlati példa:
Internet → internet gateway → publikus load balancer → privát subnetben futó alkalmazás → privát adatbázis.

## Biztonság

### 25. Mi a tárolás közbeni és az átvitel közbeni titkosítás, és hogyan valósul meg AWS-ben?

Válasz:
Az encryption at rest a tárolt adatokat védi, például lemezeken, objektumtárban és mentésekben. AWS-példák: EBS-, S3- és RDS-titkosítás, gyakran KMS-kulcsokkal. Az encryption in transit az átvitel alatt védi az adatot, például HTTPS/TLS, TLS-es adatbázis-kapcsolat vagy VPN segítségével. Egy TLS-t lezáró load balancer után a backend kapcsolat titkosítását külön kell beállítani. A kulcskezelés és hozzáférés-szabályozás mindkét esetben fontos.

Hétköznapi példa:
Tároláskor zárható széfben tartod az iratot; szállításkor zárt, ellenőrzött csomagban küldöd.

Gyakorlati példa:
S3-objektum szerveroldali titkosítással tárolva, letöltése HTTPS-kapcsolaton. Az adat így tárolás és átvitel alatt is védelmet kap.

### 26. Melyik AWS-szolgáltatás felel a monitorozásért és naplógyűjtésért?

Válasz:
Az Amazon CloudWatch gyűjt és jelenít meg metrikákat, a CloudWatch Logs naplókat fogad és kereshetővé teszi őket. Dashboardok és riasztások készíthetők, például tartósan magas CPU-használatra. EC2-n a memóriahasználat és az operációs rendszer naplói jellemzően külön agentet vagy saját adatküldést igényelnek. A CloudWatch az üzemállapot megfigyelésére szolgál; az AWS-fiók API-aktivitásának auditálására elsősorban a CloudTrail való.

Hétköznapi példa:
A műszerfal mutatja a gép hőmérsékletét és hibajelzéseit, és riaszt, ha baj van.

Gyakorlati példa:
Egy CloudWatch alarm jelez, ha az EC2 CPUUtilization metrika több egymást követő mérési időszakban a beállított küszöb fölé kerül.

### 27. Mi a bastion host, és hogyan valósítható meg AWS-ben?

Válasz:
A bastion host megerősített belépési gép, amelyen keresztül belső szerverek adminisztrációja végezhető. Hagyományosan publikus subnetben futó EC2-példány, amelynek SSH-elérése szűk forráscímtartományra korlátozott. A privát gépek SSH-forgalmát a bastion security groupjától engedélyezhetjük. Fontos a frissítés, naplózás és szigorú hozzáférés. AWS Systems Manager Session Manager megfelelő IAM- és hálózati beállítások mellett bejövő SSH-port és publikus szervercím nélkül is adhat adminisztrációs hozzáférést.

Hétköznapi példa:
A védett épület belső helyiségeibe az ellenőrzött portán keresztül lépsz be.

Kódpélda:
    ssh -J admin@bastion.example.com ubuntu@10.0.2.15
Ez SSH ProxyJump segítségével a bastionon keresztül éri el a belső gépet.

### 28. Mi a különbség a security group és a NACL között?

Válasz:
A security group hálózati interfészekhez kapcsolódik, állapottartó (stateful), és engedélyező szabályokat tartalmaz. Egy engedélyezett kapcsolat válaszforgalmát az állapotkövetés kezeli. A Network ACL az alhálózat szintjén működik, állapotmentes (stateless), engedélyező és tiltó szabályai is lehetnek. Számsorrendben az első illeszkedő szabály dönt; a válaszforgalomhoz külön megfelelő szabály kell. Security groupban nincs ilyen első találatig tartó szabálysorrend. A NACL-eknél az ideiglenes kliensportokra is gondolni kell.

Hétköznapi példa:
A security group olyan ajtóőr, aki emlékszik a beengedett beszélgetésre; a NACL minden áthaladó csomagot külön szabálylista szerint ellenőriz.

Gyakorlati példa:
HTTPS-szervernél a security group beengedheti a 443-as portot, a válasz állapot alapján távozhat. NACL esetén a bejövő 443 mellett a megfelelő kimenő kliensportokat is engedélyezni kell.

### 29. Melyik AWS-szolgáltatás követi a fiókban végzett műveleteket?

Válasz:
Az AWS CloudTrail az AWS-fiók aktivitását és számos API-hívását rögzíti: ki, mikor, milyen műveletet, mely erőforráson és milyen eredménnyel végzett. A menedzsmentesemények például konfigurációváltozásokat mutatnak. Az adateseményeket, például az S3 objektumszintű hozzáféréseket a kívánt lefedettséghez külön konfigurálni kell. A naplózás tartósságához és kiterjedéséhez megfelelő trail vagy más támogatott tárolási megoldás szükséges. Nem helyettesíti az alkalmazás saját naplózását.

Hétköznapi példa:
A belépési és műveleti napló megmutatja, ki nyitott ajtót vagy módosított beállítást.

Gyakorlati példa:
Egy váratlanul törölt EC2-példánynál a TerminateInstances eseményt keresem, majd ellenőrzöm a hívó identitását és időpontját.

### 30. Mi a különbség a szimmetrikus és aszimmetrikus titkosítás között?

Válasz:
Szimmetrikus titkosításnál ugyanaz a titkos kulcs kell a titkosításhoz és visszafejtéshez; gyors, ezért nagy adatmennyiségnél gyakori, például AES esetén. Aszimmetrikus eljárásnál összetartozó nyilvános és privát kulcs van. Titkosításra alkalmas sémában a nyilvános kulccsal védett adat a privát kulccsal fejthető vissza. Digitális aláírásnál a privát kulccsal készített aláírást a nyilvános kulccsal ellenőrzik. Nem minden aszimmetrikus algoritmus alkalmas minden feladatra. A modern protokollok gyakran kombinálják a módszereket.

Hétköznapi példa:
Szimmetrikus: közösen ismert széfkulcs. Aszimmetrikus titkosítás: bárki bedobhat lezárt üzenetet, de csak a tulajdonos nyithatja ki.

Gyakorlati példa:
A TLS tipikusan aszimmetrikus módszerekkel hitelesít és állapodik meg kulcsokban, majd gyors szimmetrikus titkosítással védi az adatforgalmat.

### 31. Mi a legkisebb jogosultság elve, és hogyan alkalmazható AWS-ben?

Válasz:
A Principle of Least Privilege szerint egy identitás csak a feladatához szükséges műveleteket, erőforrásokat és időtartamot kapja meg. IAM policyban szűk Action-, Resource- és szükség szerint Condition-beállításokat használunk. Kerüljük a fölösleges adminisztrátori és csillagos jogosultságokat. Előnyös az ideiglenes hitelesítés, a szerepkörök, a hozzáférések rendszeres felülvizsgálata és az IAM Access Analyzer használata. Az explicit deny felülírja az allow engedélyt.

Hétköznapi példa:
A futárnak a csomagátadóhoz adsz belépést, nem az egész épület főkulcsát.

Kódpélda:
    {
      "Version": "2012-10-17",
      "Statement": [{
        "Effect": "Allow",
        "Action": "s3:GetObject",
        "Resource": "arn:aws:s3:::pelda-tananyag/public/*"
      }]
    }
Ez objektumolvasást enged az adott prefix alatt; listázási jogot nem ad.

### 32. Miben tér el az IAM role az IAM usertől, és mikor melyiket használod?

Válasz:
Az IAM user a fiókon belüli identitás, amelyhez hosszú életű hitelesítő adatok is tartozhatnak, például jelszó vagy access key. Az IAM role felvehető szerepkör: trust policy szabályozza, ki veheti fel, permissions policy pedig azt, mit tehet. Felvételekor ideiglenes hitelesítő adatok érkeznek. Role használható EC2- és Lambda-alkalmazásokhoz, fiókok közötti hozzáféréshez és föderált bejelentkezéshez. Embereknél általában IAM Identity Center vagy más föderáció célszerű; user inkább indokolt, régebbi integrációknál maradhat szükséges.

Hétköznapi példa:
A user névre szóló állandó igazolvány; a role időlegesen felvehető munkaköri jogosultság.

Gyakorlati példa:
Az EC2-n futó alkalmazás instance profile-on keresztül role-t kap S3-olvasáshoz, így nem kell access keyt a forráskódba tenni.

### 33. Hogyan működik az AWS megosztott felelősségi modellje?

Válasz:
Az AWS a felhő infrastruktúrájának biztonságáért felel: adatközpontok, fizikai eszközök és az általa üzemeltetett alaprétegek. Az ügyfél a felhőben használt adataiért, identitásaiért, jogosultságaiért és konfigurációiért felel. A pontos határ szolgáltatásfüggő. EC2-n az ügyfél feladata a vendég operációs rendszer és alkalmazás frissítése; S3-nál nem kezel szerver-OS-t, de a bucket-hozzáférést és az adatvédelmi beállításokat továbbra is neki kell szabályoznia. A menedzselt szolgáltatás nem szünteti meg az ügyfél felelősségét.

Hétköznapi példa:
A bérbeadó karbantartja az épületet, a bérlő szabályozza, kit enged be és mit tart a lakásban.

Gyakorlati példa:
AWS védi az EC2 fizikai gazdagépét; az ügyfél javítja a saját EC2-gépén futó sérülékeny webszervert.

## Konténerek és konténerorchesztráció

### 34. Mi a különbség a konténerek és a virtuális gépek között?

Válasz:
A virtuális gép virtualizált hardveren saját operációs rendszert és kernelt futtat. A konténer jellemzően elkülönített folyamatokat futtat a gazda kernelét megosztva; Linuxon namespace-ek és cgroupok segítik az izolációt és erőforrás-kezelést. A konténer általában kisebb és gyorsabban indul, a VM rendszerint erősebb elkülönítési határt ad. Egy image az alkalmazás és felhasználói környezete csomagja; a konténer annak futó példánya. Linux-konténerek Windowson gyakran egy köztes Linux VM-ben futnak.

Hétköznapi példa:
A VM külön ház saját gépészettel, a konténer közös épületben külön lakás.

Kódpélda:
    docker run --rm alpine uname -a
Ez a konténerben elérhető kerneladatokat mutatja; nem indít hozzá külön vendégkernelt.

### 35. Melyek a legfontosabb Dockerfile-utasítások?

Válasz:
A FROM alapimage-et választ. A WORKDIR munkakönyvtárat állít be. A COPY fájlokat másol; az ADD további funkciókat is tud, például helyi archívum kibontását, ezért egyszerű másolásra a COPY egyértelműbb. A RUN build közben futtat parancsot. Az ARG buildparaméter, az ENV környezeti változó alapértéke. A USER a felhasználót állítja. Az EXPOSE dokumentálja a portot, de nem teszi közzé a gazdagépen. Az ENTRYPOINT és CMD az indulást szabályozza. A HEALTHCHECK állapotellenőrzést írhat le.

Hétköznapi példa:
A Dockerfile egy csomag összeállítási és használatba vételi receptje.

Kódpélda:
    FROM python:3.12-slim
    WORKDIR /app
    COPY app.py .
    EXPOSE 8000
    CMD ["python", "app.py"]
Az app.py-nak a buildkörnyezetben léteznie kell, és a megfelelő címen és porton kell figyelnie.

### 36. Mi a különbség a CMD és az ENTRYPOINT között?

Válasz:
A CMD alapértelmezett indítási parancsot vagy argumentumokat ad, amelyeket a docker run image utáni argumentumai felülírhatnak. Az ENTRYPOINT meghatározza az alapként futó programot; exec formában a CMD hozzá ad alapargumentumokat. Az ENTRYPOINT a --entrypoint kapcsolóval módosítható. Az exec forma, például ["python", "app.py"], elkerüli a köztes shellt és segíti a jelzések megfelelő kezelését. Egy Dockerfile több CMD-je közül csak az utolsó érvényes.

Hétköznapi példa:
Az ENTRYPOINT a kiválasztott kávégép, a CMD az alapértelmezett italbeállítás, amely rendeléskor változtatható.

Kódpélda:
    ENTRYPOINT ["python", "app.py"]
    CMD ["--port", "8000"]
Az így épített image esetén:
    docker run --rm myapp --port 9000
A futó parancs: python app.py --port 9000.

### 37. Hogyan működik a Docker build gyorsítótárazása?

Válasz:
A builder a buildlépések korábbi eredményeit újrahasználhatja, ha a lépés és releváns bemenetei nem változtak. A COPY által érintett fájl változása érvénytelenítheti az adott lépést és az arra épülő lépéseket. Egy RUN parancsot nem feltétlenül futtat újra csak azért, mert egy külső csomagtár tartalma megváltozott. Érdemes a ritkán változó függőségleírókat előbb, a gyakran változó forrást később másolni. A .dockerignore csökkenti a buildkörnyezetet. A --no-cache kikapcsolja az adott build cache-használatát; az alapimage friss ellenőrzésére a --pull szolgál.

Hétköznapi példa:
Ha a torta alapja nem változott, új díszítéshez nem kell feltétlenül az alapot is újra elkészíteni.

Kódpélda:
    COPY requirements.txt .
    RUN pip install --no-cache-dir -r requirements.txt
    COPY . .
Így a forráskód változása önmagában nem igényli a függőségek újratelepítését.

### 38. Hogyan csökkenthető egy konténerimage mérete?

Válasz:
Megfelelően kicsi alapimage-et választok, és multi-stage builddel csak a futtatáshoz szükséges eredményt másolom a végső image-be. Kihagyom a buildeszközöket, tesztadatokat és fölösleges függőségeket. .dockerignore fájllal kizárom a szükségtelen bemeneteket. A letöltési cache-t és átmeneti fájlokat ugyanabban a RUN lépésben takarítom el, amelyben létrejöttek, mert későbbi törlésük az alsó image-rétegből nem távolítja el őket. Az Alpine nem minden alkalmazáshoz megfelelő a musl és egyéb kompatibilitási eltérések miatt.

Hétköznapi példa:
Az elkészült bútort szállítod ki, nem az egész műhelyt és a fűrészport.

Kódpélda:
    FROM golang:1.24 AS build
    WORKDIR /src
    COPY . .
    RUN CGO_ENABLED=0 go build -o /app .

    FROM scratch
    COPY --from=build /app /app
    ENTRYPOINT ["/app"]
A példa megfelelő Go-projektet feltételez. A program igényei szerint például CA-tanúsítványokat is másolni kellhet.

### 39. Milyen problémákat okozhat a latest tag használata?

Válasz:
A latest változtatható címke, nem garancia a legfrissebb, legstabilabb vagy legbiztonságosabb verzióra. Ugyanazzal a taggel később más image tölthető le, ezért romolhat a reprodukálhatóság, eltérhetnek a környezetek és nehezebb lehet a visszaállás. A már letöltött image nem frissül magától. Verziótag használata átláthatóbb, de az is módosítható; konkrét tartalom rögzítésére digest használható. A rögzített verziókat is rendszeresen frissíteni kell.

Hétköznapi példa:
Ha csak annyit rendelsz, hogy „a szokásos”, idővel más terméket kaphatsz ugyanarra a kérésre.

Gyakorlati példa:
Verzió szerinti hivatkozás: myapp:1.4.2.
Tartalom szerinti hivatkozás alakja: myapp@sha256:<konkrét-digest>.
A helyőrző helyére valódi image-digest kell.

### 40. Hogyan épül fel egy Kubernetes-klaszter?

Válasz:
A klaszter vezérlősíkból (control plane) és munkagépekből (worker node-okból) áll. A kube-apiserver a központi API. Az etcd tárolja a klaszter állapotadatait. A scheduler kiválasztja az új Podok node-ját. A controller-manager vezérlői a kívánt és tényleges állapotot egyeztetik. A node-on a kubelet gondoskodik a hozzárendelt Podok futtatásáról a konténerfuttatóval, például containerd-vel. A hálózatot CNI-megoldás biztosítja; a Service-forgalom kezelését gyakran kube-proxy vagy azt helyettesítő hálózati megoldás végzi. A Pod a legkisebb ütemezhető egység, egy vagy több konténerrel.

Hétköznapi példa:
A központ kiosztja a feladatokat, a telephelyek végrehajtják, a felügyelők ellenőrzik a kívánt állapotot.

Kódpélda:
    kubectl get nodes
    kubectl get pods -A

### 41. Miért felel a Deployment Kubernetes-objektum?

Válasz:
A Deployment deklaratívan kezeli a Podok kívánt állapotát, tipikusan állapotmentes alkalmazásoknál. ReplicaSeteken keresztül biztosítja a megadott példányszámot, és Pod-sablon változásakor szabályozott frissítést végezhet. Támogatja a rolling update-et és korábbi revízióra visszaállást. Nem biztosít önmagában stabil hálózati címet vagy tartós adatot; ezekhez további objektumok szükségesek. Sikertelen kiadás esetén nem garantál automatikus rollbacket: azt külön kezdeményezni vagy automatizálni kell.

Hétköznapi példa:
A műszakvezető gondoskodik három dolgozóról, és az új munkamódszert fokozatosan vezeti be.

Kódpélda:
    kubectl create deployment web --image=nginx:1.28 --replicas=3
    kubectl rollout status deployment/web
    kubectl rollout history deployment/web
Egy későbbi módosítás visszaállítására:
    kubectl rollout undo deployment/web

### 42. Milyen Kubernetes-probe-ok vannak, és mire valók?

Válasz:
A liveness probe azt ellenőrzi, hogy a konténer működőképes-e; ismételt hibánál a kubelet újraindítja a konténert az újraindítási szabályoknak megfelelően. A readiness probe azt vizsgálja, fogadhat-e forgalmat; hibánál a Pod nem számít kész végpontnak a normál Service-forgalomhoz. A startup probe az indulás sikerét ellenőrzi; amíg nem sikeres, a többi probe nem fut. Lassú indulásnál megakadályozhatja a korai liveness-újraindítást. Ellenőrzés lehet például HTTP, TCP, parancsfuttatás vagy támogatott gRPC health check.

Hétköznapi példa:
Startup: megnyitott-e már az étterem? Readiness: fogad-e vendéget? Liveness: működik-e még a konyha?

Kódpélda egy konténer specifikációjának részleteként:
    readinessProbe:
      httpGet:
        path: /ready
        port: 8080
      periodSeconds: 5
    livenessProbe:
      httpGet:
        path: /health
        port: 8080
      periodSeconds: 10
Az alkalmazásnak ezeket a végpontokat megfelelő jelentéssel kell megvalósítania.

### 43. Mi a különbség az erőforrás-request és -limit között?

Válasz:
A request az ütemezésnél figyelembe vett erőforrásigény; a scheduler ezt veti össze a node kiosztható kapacitásával. Nem jelenti azt, hogy a konténer mindig pontosan ennyit fogyaszt. A limit a futás közbeni felső korlát. CPU-limitnél a folyamat jellemzően korlátozást, throttlingot tapasztal; memórialimit túllépése OOM miatti leállításhoz vezethet. Az 500m CPU fél CPU-egység, a 256Mi memória 256 mebibájt. Memórianyomás esetén a node Podokat is kilakoltathat, ami külön jelenség a konténer memórialimitjétől.

Hétköznapi példa:
A request előre lefoglalt munkahely, a limit a legnagyobb engedélyezett hely- és géphasználat.

Kódpélda:
    resources:
      requests:
        cpu: "250m"
        memory: "128Mi"
      limits:
        cpu: "500m"
        memory: "256Mi"

### 44. Miért felel a Service Kubernetes-objektum?

Válasz:
A Service stabil hálózati elérési pontot ad egy változó Podcsoporthoz. Tipikusan label selectorral választja ki a Podokat, a hozzájuk tartozó végpontokat a rendszer követi. Így a kliensnek nem kell az újrainduló Podok IP-címeit ismernie. Gyakori típusok: ClusterIP a klaszteren belüli eléréshez, NodePort node-porton történő eléréshez, LoadBalancer külső terheléselosztó integrációhoz. Az ExternalName DNS-aliaszt ad. A Service nem indít Podokat, és önmagában nem alkalmazási szintű útválasztó.

Hétköznapi példa:
Az ügyfélszolgálat telefonszáma állandó, miközben a hívást fogadó dolgozók cserélődnek.

Kódpélda:
    apiVersion: v1
    kind: Service
    metadata:
      name: web
    spec:
      selector:
        app: web
      ports:
        - port: 80
          targetPort: 8080
A kiválasztott Podokon app: web label és 8080-on figyelő alkalmazás szükséges.

### 45. Mi a különbség a ConfigMap és a Secret között?

Válasz:
A ConfigMap nem bizalmas konfigurációt tárol, például szolgáltatáscímet vagy naplózási szintet. A Secret érzékeny adatokhoz való, például jelszóhoz, tokenhez vagy TLS-kulcshoz. Mindkettő átadható környezeti változóként vagy csatolt fájlként. A Secret data mezőjének Base64-kódolása nem titkosítás. Szükséges a hozzáférések szűkítése és a tárolási titkosítás megfelelő beállítása; egy alap Kubernetes-telepítésben nem feltétlenül titkosított az etcd-ben tárolt Secret. Külső titokkezelő is használható. A környezeti változóként átadott érték nem frissül automatikusan a már futó konténerben.

Hétköznapi példa:
A ConfigMap a nyitvatartási tábla, a Secret a korlátozottan hozzáférhető kulcsszekrény tartalma.

Kódpélda:
    kubectl create configmap app-config --from-literal=LOG_LEVEL=info
    kubectl create secret generic app-secret --from-file=password=./password.txt
A password.txt tartalmának és hozzáférésének védelméről külön gondoskodni kell.

## Infrastruktúra kódként

### 46. Mi az Infrastructure as Code, és mik az előnyei, hátrányai?

Válasz:
Az Infrastructure as Code (IaC) géppel feldolgozható leírásokkal kezeli az infrastruktúrát a kézi kattintgatás helyett. Deklaratív megközelítésben a kívánt állapotot írjuk le, az eszköz megtervezi a szükséges lépéseket. Előnye a verziókövetés, ellenőrizhetőség, automatizálhatóság, újrafelhasználás és környezetek következetes létrehozása. Hátránya a tanulási és karbantartási igény, a state és titkok kezelése, valamint az automatizált hibák nagy hatása. A kézi módosítások driftet, azaz eltérést okozhatnak a kód és a valóság között. Példák: Terraform és AWS CloudFormation.

Hétköznapi példa:
Egy épületet dokumentált tervrajz alapján építesz újra, nem emlékezetből.

Kódpélda Terraformhoz:
    resource "aws_vpc" "main" {
      cidr_block = "10.0.0.0/16"
    }
A részlet beállított AWS providert és megfelelő jogosultságot feltételez.

### 47. Melyek a Terraform-munkafolyamat alapvető parancsai?

Válasz:
A terraform init inicializálja a munkakönyvtárat, providereket, modulokat és backendbeállítást. A fmt egységesen formázza a kódot, a validate szintaktikai és belső konzisztencia-ellenőrzést végez, de nem bizonyítja a felhőműveletek sikerét. A plan változtatási tervet készít, az apply végrehajtja a jóváhagyott tervet. A destroy a konfiguráció által kezelt infrastruktúra törlésére szolgál, ezért csak szándékos megszüntetéskor használjuk. A show állapotot vagy mentett tervet jelenít meg.

Hétköznapi példa:
Előkészíted az eszközöket, ellenőrzöd a tervet, átnézed az árajánlatot, majd végrehajtod a munkát.

Kódpélda:
    terraform init
    terraform fmt
    terraform validate
    terraform plan -out=tfplan
    terraform apply tfplan
A mentett terv érzékeny adatot is tartalmazhat; védett helyen kell kezelni.

### 48. Mi a különbség a resource és a data source között Terraformban?

Válasz:
A resource blokk olyan erőforrást ír le, amelynek életciklusát a Terraform kezeli: létrehozhatja, módosíthatja és törölheti. A data source információt olvas egy meglévő erőforrásról vagy külső adatforrásból; önmagában nem veszi át annak teljes életciklus-kezelését. Például meglévő VPC-t lekérdezhetek, majd abban új subnetet hozhatok létre. Meglévő erőforrás kezelésbe vételéhez megfelelő resource-konfiguráció és import szükséges.

Hétköznapi példa:
A resource új lakás építésének és fenntartásának megbízása; a data source egy meglévő épület adatlapjának lekérése.

Kódpélda:
    data "aws_vpc" "existing" {
      id = var.vpc_id
    }

    resource "aws_subnet" "app" {
      vpc_id     = data.aws_vpc.existing.id
      cidr_block = "10.0.1.0/24"
    }
A megadott subnetcímtartománynak illeszkednie kell a tényleges VPC-hez, és nem ütközhet más subnettel.

### 49. Mit jelent a state Terraformban?

Válasz:
A state a Terraform által kezelt objektumok nyilvántartása: összeköti a konfigurációbeli erőforráscímeket a valós azonosítókkal, és attribútumokat, valamint metaadatokat tárol. A Terraform a konfiguráció, a state és a szolgáltatótól lekért állapot alapján tervez. Helyben gyakran terraform.tfstate fájlban van, csapatmunkához rendszerint távoli backend célszerű megfelelő hozzáférés-védelemmel és támogatott zárolással. A state érzékeny értékeket is tartalmazhat; a sensitive jelölés nem titkosítja automatikusan. Nem szokás Gitbe commitolni vagy kézzel átírni.

Hétköznapi példa:
A leltár összekapcsolja a tervben szereplő gépeket a tényleges gyári számukkal.

Kódpélda:
    terraform state list
    terraform state show aws_vpc.main
A második parancs csak akkor működik, ha ez az erőforráscím a state-ben szerepel.

### 50. Mik a modulok Terraformban?

Válasz:
A modul egy könyvtár Terraform-konfigurációinak együttese. A futtatás kiinduló könyvtára a root module; ebből module blokkokkal child module-ok hívhatók. Egy modul bemeneti változókkal paraméterezhető, erőforrásokat és további modulokat tartalmazhat, outputokkal adhat vissza értékeket. Így például egy VPC vagy alkalmazáskörnyezet újrafelhasználható egységgé szervezhető. A modul nem egyetlen .tf fájlt jelent: egy könyvtár .tf fájljai együtt alkotják a modult. A külső modulok verzióját célszerű rögzíteni.

Hétköznapi példa:
Egy kipróbált konyhatervet több lakásban felhasználsz, eltérő méretekkel és beállításokkal.

Kódpélda:
    module "network" {
      source   = "./modules/network"
      vpc_cidr = "10.0.0.0/16"
    }
A hivatkozott modulban deklarálni kell a vpc_cidr változót.

### 51. Melyek a Terraform metaargumentumai, és mire használhatók?

Válasz:
A metaargumentumok a Terraform saját vezérlési beállításai, nem egy konkrét felhőerőforrás szokásos mezői. A használhatóságuk blokktípustól függ.
- count: számozott példányok létrehozása, például három hasonló erőforrás vagy feltételes 0/1 példány.
- for_each: kulcsokkal azonosított példányok létrehozása mapből vagy stringhalmazból; stabil kulcsokkal jól kezelhető az elemek változása.
- depends_on: kifejezett függőség megadása, ha az attribútumhivatkozásokból nem következik. Normál esetben az automatikus függőségfelismerés előnyösebb.
- provider: erőforrásnál vagy támogatott blokkban kiválasztja a használt providerkonfigurációt, például másik régió aliasát.
- providers: module blokkban adja át a gyermekmodul providerkonfigurációit.
- lifecycle: életciklusszabályokat ad, például create_before_destroy, prevent_destroy, ignore_changes és replace_triggered_by. A prevent_destroy nem helyettesíti a felhőoldali törlésvédelmet, különösen ha a konfigurációt eltávolítják.
Újabb verziókban a lifecycle részeként action_trigger is elérhető támogatott actionök életciklus-eseményhez kötésére; használatát a rögzített Terraform- és providerverzió dokumentációjával kell egyeztetni.
Ugyanabban a blokkban count és for_each nem használható együtt.

Hétköznapi példa:
A terv mellett megadod, hány példány készüljön, milyen sorrendben, és mikor szabad lecserélni a régit.

Kódpélda:
    resource "aws_subnet" "app" {
      for_each = {
        a = "10.0.1.0/24"
        b = "10.0.2.0/24"
      }
      vpc_id     = aws_vpc.main.id
      cidr_block = each.value
    }
A subnetek kulcs alapján azonosíthatók: aws_subnet.app["a"] és aws_subnet.app["b"].

### 52. Hogyan érdemes felépíteni egy Terraform-projekt fájlszerkezetét?

Válasz:
Gyakori elrendezés: main.tf az alapösszeállításhoz, variables.tf a bemenetekhez, outputs.tf a kimenetekhez, providers.tf a providerkonfigurációhoz, versions.tf a Terraform- és providerkövetelményekhez, backend.tf az állapottároló beállításához. A fájlnevek többsége konvenció; a Terraform egy modul .tf fájljait együtt dolgozza fel. Nagyobb projektnél lehet network.tf vagy security.tf is. Újrafelhasználható részek kerülhetnek modules/ alá. A dev és prod külön root modult és külön state-et kaphat az elkülönítéshez. A .terraform/ könyvtárat, state-et, titkos .tfvars fájlokat és tervfájlokat nem szokás Gitbe tenni; a .terraform.lock.hcl fájlt általában igen.

Hétköznapi példa:
Külön rendezett dossziékban tartod a terveket, paramétereket és környezeti adatokat, a titkos iratokat védett helyen.

Gyakorlati példa:
    infrastructure/
      modules/
        network/
          main.tf
          variables.tf
          outputs.tf
      environments/
        dev/
          main.tf
          providers.tf
          versions.tf
          backend.tf
          variables.tf
          outputs.tf
        prod/
          main.tf
          providers.tf
          versions.tf
          backend.tf
          variables.tf
          outputs.tf
A külön környezetek backendjét úgy kell konfigurálni, hogy ne ugyanazt a state-et módosítsák.

## Hivatalos források további tanuláshoz

Linux/Bash – set:
https://www.gnu.org/software/bash/manual/html_node/The-Set-Builtin.html

Dockerfile és CMD/ENTRYPOINT:
https://docs.docker.com/reference/dockerfile/

Docker build cache:
https://docs.docker.com/build/cache/invalidation/

Docker image-építési gyakorlatok:
https://docs.docker.com/build/building/best-practices/

Kubernetes erőforrások:
https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/

Kubernetes Secrets:
https://kubernetes.io/docs/concepts/configuration/secret/

AWS VPC és security groupok:
https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html

AWS CloudTrail:
https://docs.aws.amazon.com/awscloudtrail/latest/userguide/WhatIsCloudTrail-Security.html

Terraform metaargumentumok:
https://developer.hashicorp.com/terraform/language/meta-arguments

Terraform lifecycle:
https://developer.hashicorp.com/terraform/language/meta-arguments/lifecycle

Terraform stílus és projektfelépítés:
https://developer.hashicorp.com/terraform/language/style
