# Keyboard shortcuts
- Use arrow keys for single steps.
- Hold Ctrl with arrows to jump word by word.
- Use Home and End to reach start or end of a line.
- Hold Shift with arrows to select text.
- Combine Ctrl+Shift with arrows to select words quickly.
- Ctrl+D selects the next occurrence of a symbol.
- Alt+Click adds multiple cursors for simultaneous editing.
- Ctrl+P opens quick file search.
- Type part of a filename and press Enter to open it.
- Ctrl+W closes the current file.
- Ctrl+\ splits the editor into two.
- Ctrl+1 and Ctrl+2 move focus between split groups.
- Ctrl+` opens or toggles the terminal.
- Use Ctrl+1 to focus the editor again.
- Use Tab in the terminal for file and folder autocompletion.
- Use the Up Arrow in the terminal to recall previous commands.

# Hasznos oldalak
# Terminál
1. Egyszerű futtatás: java filename.java
2. Jshell (~ghci)  
```    
    > jshell  
    jshell> /open filename.java  
    jshell> main()  
    chcp 65001 -> utf8-ra rakja a terminált 
```

# Alap cuccok
## Kiírás
IO.println(“szöveg”*.formatted(_)* + változó);  
IO.print(_); -> nincs sortörés
Fájlba:
- létrehozás: PrintWriter pw = new PrintWriter(filename); 
- írás: pw.println(string);
## Beolvasás
IO.readln("Ez kiprintelődik a terminálra mielőtt beírod az inputot");  
BufferedReader típus segítségével:  
BufferedReader br = new BufferedReader(new FileReader(filename));
# Változók
> Nem mindegy, hogy kis vagy nagybetűsek:(

típus név = ...;
### var

### String
| Feladat | Metódus | 
| ----- | -----|
|Összehasonlítás | s1.equals(s2)|
|Rész | s.substring(ettől eddig)|
|Csere | s.replaceAll(mit, mire)|
|Kisbetűssé alakítás | s.toLowerCase() |
|Hossz|s.length()|
|n. betű| s.charAt(n)|
|Hozzáfűzés| s+=mit|

```
    "Egy soros String"
    """ több 
    soros 
    String """
```

#### StringBuilder (import java.io.*)
Hozzáfűzés: s.append(mit)

### int
Konverzió (String -> int): int x = Integer.parseInt(szöveg);

##### Formatted
"szöveg %_".formatted(\_);
- %s -> string
- %f -> float
- %d -> decimal

# Adatszerkezetek
### Tömb
| Feladat | Metódus | 
| ----- | -----|
| Első elem | t[0]   |
| N. elem | t[n]  |
| Hossz | t.length |
| Üres-e | t.isEmpty() |

### Enum
public enum Név {ADAT1, ADAT2, ADAT3 stb}  
hivatkozás egy tagjára: Név.ADATX  
típusa: var  
hányadik a felsorolásban (0-tól indexel): e.ordinal()
összehasonlítás: n.ADAT1 == n.ADAT2  
>n.ADAT1 == m.ADAT2 -> NEM FORDUL LE

for (var rank : Rank.values()) {_}

### Record
public record Név(típus1 név1, típus2 név2) {_}

**példányosítás**:  
típus-Név/var  
típus név(pl. r) = new Név(név1, név2);

**hivatkozás az adattagokra**:  
r.név1()  
r.név2()

**rekord dekonstruálása (~mintaillesztés)**:
```
switch (duo){  
    case Duo(Person(var name1, var age1), var p2) when age1 > x -> _;  
    stb.
}
```

### List
List<típus> név = new List<típus>();  
List<típus> név = List.of(elem1, elem2, stb.);

| Feladat | Metódus | 
| ----- | -----|
| N. elem | l.get(n)  |
| Hossz | t.size() |
| Üres-e | t.isEmpty() |

>~~int~~ -> Integer

### ArrayList

### HashMap (import java.util.*)
HashMap\<kulcs típusa, érték típusa\>

> NEM BEJÁRHATÓ -> EntrySetté kell alakítani

inicializáció: new HashMap<>(*);  
(\*) lehet: 
- () -> üres HashMap
- (x) -> x egy létező HashMap

| Feladat | Metódus | 
| ----- | -----|
| kulcs keresése | hm.containsKey(keresett kulcs)  |
| kulcs hozzáadása/lecserélése | hm.put(hozzáadandó kulcs, érték) |
| Érték | hm.get(kulcs) |
|Átalakítás EntrySet-té|hm.entrySet()|
|getOrDefault|hm.getOrDefault(kulcs, default visszatérési érték ha a kulcs nem létezik)|


### HashSet (import java.util.*)
HashSet\<típus\>

inicializáció: new HashSet<>(*);  
(\*) lehet: 
- () -> üres HashSet
- (x) -> x egy létező HashSet
- (Set.of(_))

| Feladat | Metódus | 
| ----- | -----|
| benne van-e egy bizonyos elem | hs.contains(keresett elem)  |
| elem hozzáadása | hs.add(hozzáadandó elem) |
| több elem hozzáadása | hs.addAll() |

### Entry, EntrySet (import java.util.Map.Entry)
> HashMap egy kulcs-érték párja az Entry és ezekből több az EntrySet (~bejárható HashMap)
Entry\<kulcs típusa, érték típusa\> 

Bejárás:  
`for (Entry<kulcs típusa, érték típusa> e : es) {_}`

| Feladat | Metódus | 
| ----- | -----|
| Kulcs | e.getKey() |
| Érték | e.getValue() |

# Függvények
láthatóság (static) visszatérési_érték név(paraméterek) {törzs}
### Main
public class Filename{
    public static void main(String... args) {_}
    vagy
    public static void main() {_}
}


## Argumentumok
változók: típus név  
tömbök: típus... név  
>FONTOS: a tömb mindig az utolsó paraméter!!

pl. boolean... data

## Parancssori argumentumok
void main(String... args) {törzs}

Első argumentum: args[0]  
N. argumentum: args[n]  
Argumentumok száma: args.length

# Osztályok
> nagybetűvel kezdjük a nevüket

láthatóság: public/private

láthatóság class Név {_}

lehetnek adattagjai: láthatóság típus név;  
konstruktora: láthatóság Osztály_neve(paraméterek) {\_}  
és metódusai: láthatóság visszatérési_érték név(paraméterek) {\_}

Példányosítás:  
new Osztály_neve(paraméterek);

# Ciklusok, elágazások
### for 
for (int i = _; i < _; i++) {_}

"foreach"  
for (típus var : vars) {_}

### if else
if () {}  
else if () {}  
else {}

alternatíva: feltétel ? haigaz : hahamis

### try..catch..
try(utasítások ami alatt hibát dobhat){  
    utasítások amiket akkor csinál meg, amikor nem kap hibát  
}

try {utasítások ami alatt hibát dobhat}  
catch(hiba amit el kell kapni) {mit csináljon ha elkapta ezt a hibát}
> több catch is lehet!


# Csomagkezelés
File elejére:  
`package elérési.útvonal.a.gyökér.könyvtárból;`

Ekkor a fájl: elérési/útvonal/a/gyökér/könyvtárból/Osztály_neve.java

Teljes minősített név: elérési.útvonal.a.gyökér.könyvtárból.Osztály_neve

# Importálás
import _;  
lehet importálni saját magunk által készített classt, ezt az `import teljes_minősített_név` segíségével tehetjük meg

- module java.base; -> egyszerűsített programban már benne van eleve
- java.io.* -> IOExeption, BufferedReader stb.
- java.util.* -> HashMap, HashSet stb..


# Tesztelés

> Time és a hozzátartozó tesztek elérhetőek lesznek a ZHn, érdemes használni!
## Funkcionális tesztek
```
@Test  
void testName(param) { // throws Ex -> checked exeptionre
    _
}
```  

```
@ParameterizedTest
@CsvSource(textBlock = """
    x1, y1
    x2, y2
    stb.
""")
void test_Name(típus x, típus y){
    _
} //mindegyik soron végigmegy, soronként vizsgál
```

**Használható függvények**:  
assertEquals(elvárt, tényleges)  
assertFalse(logikai állítás)
fail("hibaüzenet") -> akkor használjuk, ha hibát kellett volna kapnunk, de nem kaptunk

```
try-catch használata hibadobás tesztelésére:  
try {
    művelet aminek hibát kéne dobnia
    fail("Nem dobott hibát pedig kellett volna");
}
catch (hiba){
    semmi/újabb teszt -> ha ide elér akkor tényleg dobott hibát
}
```

## Struktúrális tesztek
> Feladat: class felépítése struktúrális tesztből

| Metódus | Mit jelent | 
| ----- | -----|
| hasConstructor(withArgsLikeAllFields) | olyan konstruktorral rendelkezik, aminek paraméterei az osztály adattagjainak felelnek meg |
| hasUsualModifiers | (?????) |
| hasMethod("név", withParams("név1: típus1")).thatreturns("típus") | olyan *típus* típusú, *név* nevű metódussal rendelkezik, aminek paraméterei a withparamsban van meghatározva |
| .thatReturnsNothing | visszatérési értéke void |
| theClass("text.to.numbers.SingleLineFile") | text.to.numbers packageben van benne a SingleLineFile class |
|hasConstructor(withNoParams())|alapértelmezett konstruktor jó, nem kell külön konstruktor|
| .thatThrows("x") | *x* exceptiont dob ami kiterjed a metóduson kívülre is (checked) <br> public típus Név(param)) throws x|
|.hasField("név: típus")| *típus* típusú, *név* nevű adattaggal rendelkezik|


|  |  | 
| ----- | -----|
| N. elem | l.get(n)  |
| Hossz | t.size() |
| Üres-e | t.isEmpty() |

## Tesztelés futtatása
> Tesztelés előtt fordítunk!! (javac elérési/út)

> Bele kell rakni a teszteléshez szükséges fileokat (check.cmd, checkagent6.jar, checkthat6.jar, junit6all.jar) a gyökérmappába amiben tesztelünk

.\check.cmd elérési\út\TesztFájlNeve.java teljes.minősített.Név  
pld: .\check.cmd .\famous\sequence\FibonacciTest.java famous.sequence.FibonacciTest

# Generikusok
[W3Schools link](https://www.w3schools.com/Java/java_generics.asp)

class Név<T> 


> kizárólag referencia típusokat fogad el! -> ~~int~~ -> Integer

> T bármi lehet, 

### Generikus metódusok
bármilyen T típussal működik  
public static <T> void printArray(T[] array) {_}
