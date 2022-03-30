# Anteckningar till 'Python As Fast as Possible - Learn Python in ~75 Minutes'
Länk till videon: https://www.youtube.com/watch?v=VchuKL44s6E

## Intendentioner
I Python använder man inte tex *;* för att avsluta rader, istället styrs allt via tab och intenderingar.

## Variabel och print
Variableltyp bestäms av vad som stoppas in i dem, det finns int, float, string och bolean. *int* är nummer, *float* är nummer med decimaler, *string* är text och *bolean* är true (1) eller false (0). Man kan använda både `'hej'` och `"hej"` för text/string.

```python
variabel = "innehåll i variabel"

print("text här", variabel, "mer text", annan_variabel)
```

## input
Använd funktionen input för att ta input från användaren, funktionen returnerar en string.

```python
name = input('Name: ')
age = input ('Age: ')

print('Hello', name.capitalize(), "you are", age.int(), "years old")
```
Här stoppar man in input i variablerna *name* och *age*. Sedan skrivs de ut med *print*-funktionen. name-variabeln modifieras med *capitalize*-funktionen och age med *int*-funktionen.

## Matte
```python
x = 9
y = 3.5
result = x - y
print(result)
```

För att ta input måste man göra om string till int, det kan göras med funktionen int() se nedan

```python
num = input('Number: ')
print(int(num) - 5)
```

## String method

hello = 'hello'
print(type(hello)) #talar om vilken class variabel har, i detta fal str

method är något med en .operator, tex .upper(), .lower() och .capitalize() som gäller för string. man kan även kedja de efter varandra, tex:

```python
hello = 'heLLo World'
print (hello.lower().count.('l'))
```

## Conditions & conditional operators
jämför två saker och ger true eller false

```python
== lika
!= inte lika med
<= mindre eller lika med
>= större eller lika med
< mindre än
> större än
```

```python
x = "hello"
y = 'hello'

print(x == y) #för att jämföra, ger bolean, i detta fall: True
```

**Chained conditionals**

Man kan använda: *and*, *or* och *not* (dessa kallas operators).
Not vänder resultatet, tex print(not True) ger False.
Not är först, sen and, sen or. ordning som operatörerna körs i. Det här kapitlet kan jag behöva se om.

```python
x = 7
y = 8
z = 0

result1 = x == y #sätter variabeln result1 till true om x och y är lika, annars false.
result2 = y > x #sätter variablen result2 till true om y är större än x, annars false.
result3 = z < x + 2 #sätter variablen result3 till true om z är mindre än x+2, annars false

result4 = result1 or result2 or result3 #or operator kollar först så det är bolean, detta stämmer här, om någon av dessa är true, blir result4 true.
print(result4)
```

## If / Else / Elif
Man kan ha bara *if*, *if och else*, *if och elif* eller *if, elif och else*.

Bara if:

```python
x = input('Name: ')

if x == 'Tim':
  print('You are great!')
  print()

print('Always do this')
```

Med else. Else kan bara användas efter if.

```python
x = input('Name: ')

if x == 'Tim':
  print('You are great!')
else:
  print('No')
```

För att kolla flera saker, flera namn tex, använd elif. Elif kan användas hur många gånger man vill men den måste komma efter if och innan else.

```python
x = input('Name: ')

if x == 'Tim':
  print('You are great!')
elif x == 'Joe':
  print('Bye Joe')
```

Flera och *if inside if*:

```python
x = input('Name: ')

if x == 'Tim':
  print('You are great Tim!')
  if y == 'Jackson':
    print('My man!')
elif x == 'Joe':
  print('Bye Joe')
elif x == 'Sarah':
  print('Hey Sarah')  
else:
  print('Who?')
```
## Collections
En ordnad eller o-ordnad grupp av *elements*, elements är någon datatyp. Tex *list* och *tumbles*

**List**
En lista är [] square bracket. Tex `x = []`. En lista är en *ordered collection* (ordnad samling). Det innebär att ordningen saker står i spelar roll och är beständig. Index betecknar en position i listan, första positionen är 0, nästa är 1 och sen 2, osv. Vill man veta sista positionen i index kan man kolla len(lista) och sen subtrahera 1. Man kan alltid ändra i listor, då variabeln endast är en referens till var datan lagras och inte en satt variabel. Vill man ha statiskt använder man *topals* istället, se längre ner för info om det. Man kan ha listor och topals i listor och listor i de listorna osv, tex `x = [[], (), [[], [], [3,4,5]]]`.

Några funktioner man kan göra med listor är (med `x = [4, True, 'hi']` som exempel):


- `len(x)` för att kolla längden, här 3
- `x.append('hello')` lägger till *hello* i slutet på listan.
- `x.extend([4,5,5,5,5,5,5])` lägger till en annan lista i slutet på *x*-listan
- `x.pop()` removes and returns the last element of the list. Dvs skriver 'hi' och tar sen bort det från listan.
- `x.pop(0)` tar bort och returnerar första elementet i listan.
- `x[]` för att titta på ett element i listan, tex `print(x[1])` för att skriva ut 'True' från exemplet.
- `x[0] = 'hello'` ändrar värdet på elementet på första plats "0" i listan.

```python
x = [4, True, 'hi'] #element behöver inte vara samma typ till skillnad från många andra språk.
print(x)
```

**Topal**
Topals är som listor men de är statiska och går inte att ändra på. Till skillnad från listor använder de () isället för [], tex `x = ()`. Eller med deta `x = (0,0,2,2)`. De fungerar som listor med skillnaden att vi inte kan append, remove, osv. Den kan inte ändras efter att den blivit definerad. Om den ska ändras så måste den omdefineras från grunden.

```python
x = (0,0,2,2)
print(x[0])
```

## For loops / while loops

*For loops* loopar ett givet antal gånger, *while loops* körs tills ett givet tillstånd är uppfyllt.
en for loop består av:
```python
for <variabel> in <något>:
  <gör grej>
```
Variabeln är en int. Det är en iterator eller räkne-variabel. Ofta använder man *i*. Jag tänker på det som att man tar första outputen i <något> och lägger in det i <variabel>, sedan gör man kommandot under, tex print(i). När man gjort det en gång hoppar man tillbaka till början och gör det igen tills det är slut på output.


Exempel på for loop för att printa nummer:
```python
for i in range(10): #for <någon int variabel>
  print(i)
```
Denna loop kommer räkna 0,1,..,9 och skriva ut det på var sin rad. Den går upp till 10 men inkluderar inte 10. *range* är en funktion som skapar en *collection* av number baserat på det input vi ger den. Input till range är: *start, stop, step*, så man kan ha upp till tre inputs. Det är vilket nummer man vill starta på, vilket nummer slutar vi på och hur stegar man. Om man bara sätter in en är det som standard *stop* och som standard startar man vid *0*. Standardordning är:
- stop
- start, stop
- start, stop, step
Om man gör:
```python
for i in range(1, 10): #
  print(i)
```
Så räknar den 1 till 9. Man kan göra `for i in range(10, -1, -1):` så går den från 10 ner till 0. Man kan göra `for i in range(8, 136, 8):` så går den 8, 16, 24, 32, ..., 128.

**Loopa genom en lista**
Tex
```python
for i in [3,4,42,3,2,4]:
  print(i):
```
Man kan även få samma resultat genom tex variabler såhär:
```python
x = [3,4,42,3,2,4]

for i in x:
  print(i)
```
För att få samma resultat men göra det lite mer komplext kan man printa ut det från dess indexposition såhär:
```python
x = [3,4,42,3,2,4]

for i in range(len(x)):
  print(x[i])
```
den kör *range* som alltså skapar en *collection* baserat på input. Input i detta fall är 6, det får man genom `len(x)`, där len kollar längden, i detta fall på antalet *element* i x-samlingen. Sedan används `print(x[i])` för att skriva ut ett tal från position *i* i samlingen *x*. Efter att den skrivit ut en börjar den om i loopen tills den får slut på elements. Range gör sedan 0-5. Här är mitt exempel som skriver ut detta tydligt:
```python
x = [3,4,42,3,2,4] #gör en samling och sätter variabeln x att peka på den.

print('Längden på samlingen länkad i variabeln x är: ' + str(len(x)) + '.\n') #räknar ut hur många element som finns i samlingen, här 6. Använder + för att koppla ihop strings, eftersom len(x) ger int omvandlar jag den med str() funktionen. \n ger ny rad.

print('Skriver ut indexposition och elementdata.\n')

print('Index', 'Data')
print('----------')
for i in range(len(x)): #tar range(6), vilket ger 0-5. Stoppar först in 0 i variabeln i, sen loopar, sen 1, sen loopar, osv.
  print(i, ' | ', x[i]) #skriver ut först indexpositionen som är i, sedan | och mellanslag, sedan element från samlingen x från position i
```
Detta kan göras enklare med en funktionen *enumerate*:
```python
x = [3,4,42,3,2,4]

for i, element in enumerate(x): #i och element är variabler, kan också vara i och e tex. enumerate-funktionen ger både indexposition och elementdata till respektive variabel.
  print(i, element)
```

**While Loops**
Tex `while condition == True:`
Som:
```python
i = 0

while i < 10:
  print('run')
  i += 1 #detta är samma som "i = i + 1", man kan även göra sånt som *=, /=, -=, osv.
```
Detta kommer köra 10 gånger och köra `print('run')` varje gång.
Man kan få samma resultat också såhär:
```python
i = 0

while True:
  print('run')
  i += 1
  if i = 10:
    break #break avslutar en loop.
```

## Slice Operator
Ex: `x[start:stop:step]`

Sllice låter en ta en bit (slice) av en collection tex en string eller list. Sedan kan du göra något med den. Slice är en *[]* med *:* och *nummer*. Det är *[start:stop:step]*, dvs man använder indexpositioner precis som i *range*-funktionen.

```python
x = [0,1,2,3,4,5,6,7,8]
y = ['hi', 'hello', 'goodybye', 'cya', 'sure']
s = "hello"

sliced = x[0:4:2] #startar på 0 och ska gå till 4 (men inte skriva ut 4), 2 steg i taget.

print(sliced)
```
Precis som range-funktionen behöver man inte skriva ut alla (start, stop, step). Gör man bara en är det stop, osv. Det ser ut såhär: `[:4]` för att starta i början och sluta på 4, `[2:]` börja på 2 och stoppa vid slutet. Så när man lämnar blankt är det antingen början, slutet eller 1 om det är step. Så `x[2:4:]` säger börja vid 2, sluta vid 4 och step by 1, man kan också skriva det `[2:4]`.

Annat exempel: `x[4:2-1]` börjar vid 4, slutar vid 2, går -1.

Backa i en lista: `x[::-1]`.

Allt detta fungerar i strängar också, tänk på indexpositon. Tex:
```python
s = "hello"

sliced = s[::-1]

print(sliced)
```

## Sets
Ett *set* är en oordnat samling av element. Ordning och dubletter osv spelar ingen roll. Fördelen med sets är att det är ett väldigt snabbt sett att göra lookups, ta bort och lägga till element. Använd sets när du inte bryr dig om ordning och position utan du vill bara veta om något finns eller inte finns. Fördelen mot collections är att om du tar bort något i en collection kommer alla andra element att flytta en plats.

För att göra en set: `x = set()`. Om man ska skapade den med innehåll från början kan man göra `s = {4,32,2,2}`, men inte annars för då gör man en *dictionary*.

```python
s = {4,32,2,2}
print(s)
```
Printar ut *32,2,4*, dvs en annan ordning än hur vi la in det och med bara en 2:a.

- Lägg till i set: `s.add()`.
- Ta bort: `s.remove()`.
- Kolla om något finns i set `print(33 in s)`, ger True

**Flera sets**
```python
s = {4,32,2,2}
s2 = {3,4,22,1}
print()
```
- Slå ihop: `print(s.union(s2))`
- s.difference
- s.intersections
- osv.


## Dictionaries
*Dicts* är ett par, en nyckel med ett värde:
*x = {'key': value}* tex `{'key': [3,4,2,5]}` för en lista. Nycklar (keys) behöver inte vara samma datatyp, de kan vara strings, int osv. Precis som *Sets* använder *Dicts* hashes och är därmed mycket snabbt, i princip hämtas data i realtid.

Hämta data:
```python
x = {'key': 4}
print(x['key'])
```
Kommer skriva ut 4.

Lägg in data:
```python
x = {'key': 4}

x['key2'] = 5
x[2] = 8
x[3] = [2,2,1,1]
print(x)
```
Kommer skriva ut: *{'key': 4, 'key2': 5, 2: 8, 3: [2, 2, 1, 1]}*

Fler exempel:
- Kolla om något finns i Dicitonary: `print('key' in x)` ger *True*.
- `print(x.values())` - hämtar värdena. Oftast vill man lägga de i en lista tex så här: `print(list(x.values()))`.
- `print(x.keys())` - hämtar nycklarna.
- Ta bort: `del x['key']` för att ta bort nyckeln och tillhörande värde.

**Loopa**

Vill man loopa igenom alla nycklar och värden använder man *.items*.
```python
for x = {'key': 4}

for key, value in x.items():
  print(key, value)
```
Vill man bara ha keys kan man göra:
```
for x = {'key': 4}

for key om x:
  print(key, x[key])
```

## Comprehensions
En comprehension initierar en lista på endast en rad. Tex:
```python
x = [x for x in range(5)]
print(x)
```
Visar: *[0, 1, 2, 3, 4]*

Det fungerar såhär: vi gör en *lista* genom []. Listan generas genom en *for loop*, `for x range(5)` vilket ger 0-4, stoppar först 0 i x-varibeln, sen 1, osv, upp till 4. Ger alltså en lista från 0-4.  Det vi har till vänster om det, i detta fallet *[x ...]* är det *x* är elementet vi stoppar in i listan.

Ett exempel:
```python
x = [x + 5 for x in range(5)]
print(x)
```
Då räknar den från 0-4 och adderar det med 5 innan det stoppas in i listan.

Ett annat exempel:
```python
x = [0 for x in range(5)]
print(x)
```
Då stoppar den in *0* vid varje *loop*.

Ett annat exempel:
```python
x = [[0 for x in range(100)] for x in range(5)]
print(x)
```
så om vi tittar på först den högra delen så kör den en loop 5 gånger, för varje loop så gör den en lista med 100 st *0*:or.

Ett annat exempel:
```python
x = [i for i in range(100) if i % 5 == 0]
print(x)
```
Visar: *[0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50, 55, 60, 65, 70, 75, 80, 85, 90, 95]*

Så om i är delbart med 5 kan vi lägga till det i listan

Det fungerar såhär: vi gör en *lista* genom []. Listan generas genom en *for loop*, `for i in range(100)` vilket ger 0-99, stoppar först 0 i i-varibeln, sen 1, osv, upp till 99. *if-satsen* säger sedan att om *i % 5* är likamed noll ska det stoppas in i *i*, i mod 5 betyder om det är delbart med 0. Kolla upp % för mer info.

## Functions
För att definera en funktion i python använder man *def* som keyword, sen väljer man namn på funktionen, tex `def jpxfunktion():` om man vil lämna den tom, går också att fylla i saker direkt om man vill.
Exempel:
```python
def func():
  print('Run')

func()
```
När man kör funktionen kommer allt i det indragna blocket att köra. Dena skriver ut strängen *Run*.

Annat exempel:
```python
def func(x, y):
  print('Run', x, y)

func(5, 6)
```
När man sätter i variabler i funktionen måste de ifyllas för att den ska kunna köras.

Exempel hur man returnerar:
```python
def func(x, y):
  print('Multiply', x, y)
  return x * y

print(func(5, 6))
```
För att skriva ut värdet av funktionen (det som returneras) behöver vi använda print(). Denna funktion multiplicerar nu de två int-talen den får i sig och returnerar dessa.

Hur man returnerar flera saker:
```python
def func(x, y):
  print('Multiply', x, y)
  return x * y, x / y

print(func(5, 6))
```
När man returnerar flera saker returneras det som en *Tuple*.

Hur man returnerar flera saker och returnerar en specifik del:
```python
def func(x, y):
  print('Multiply', x, y)
  return x * y, x / y

r1, r2 = func(5, 6)
print(r1, r2)
```
Man man köra index tex: `print(func(5, 6))[0]` eller `print(func(5, 6))[1]`, men ett snyggare och bättre sätt är att är plocka ut det i variabler som här ovan med *r1* och *r2*.

Hur man använder en *valfri parameter*:
```python
def func(x, y z=None):
  print('Run', x, y, z)
  return x * y, x / y

r1, r2 = func(5, 6, 7)
print(r1, r2)
```
Man kan sätta ett standardvärde, tex *None*. Man behöver inte använda *z* men man kan göra det och då ersätts standardvärdet, i det här fallet None.

**Avancerade funktioner**
Avancerat exempel på en funktion:
```python
def func(x):
  def func2():
    print(x)

  return func2

print(func(3))
```
Det som händer här är att en funktion defineras, den funktionen har en till funktion i sig, sen returneras func2. print skriver ut länken till func2, dvs den körs ej eftersom den är returnerad. Det som skrivs ut är: `<function func.<locals>.func2 at 0x7fc4f32fb7f0>`, detta beror på att funktioner är objekt.

*Personlig kommentar:* jag fattar inte riktigt dessa exempel och vad det kan användas till, så behöver nog kolla andra videos/guider på hur det här funkar om jag behöver använda det.

Annat exempel:
```python
def func(x):
  def func2():
    print(x)

  return func2

print(func(3)())
```
Lägger man till en () så ansluter man till func2. och får utskrivet *3* och *None*. Det blir None eftersom det inte är något att returnera från func2.

Annat sätt att göra det på:
```python
def func(x):
  def func2():
    print(x)

  return func2

x = func(3)
x()
```
Eftersom x är = med en funktion, här func2, så returnerar detta *3*.

## Unpack Operator

**Unpack operator**
är *\*-tecknet* före tex en variabel, vilket betyder *packa upp* objektet. Tex:
```python
x = [1,23,234525,2727]

print(*x)
```
Den tar ut alla elementen från listan, separerar dem som individuella element och skickar dem till *print* som *argument*. Dvs den gör samma sak som `print(1, 23, 234525, 2727)` skulle göra.

**Gör en for loop som ansluter till funktionen för att skriva ut par**

Naivt exempel:
```python
def func(x, y):
  print(x, y)

pairs = [(1,2), (3,4)]

for pair in pairs:
  func(pair[0], pair[1])
```
Skriver ut:
```
1 2
3 4
```
Men det är inte så man bör göra i Python utan istället såhär:
```python
def func(x, y):
  print(x, y)

pairs = [(1,2), (3,4)]

for pair in pairs:
  func(*pair)
```
Här använder man *unpack operator* (\*) som packar upp och separarera elementen och skickar de till funktionen som argument. Ger samma resultat.

Man kan även använda det på dictionaries, då är det två \*-tecken istället för ett, såhär:
```python
def func(x, y):
  print(x, y)

  func(**{'x': 2, 'y': 5})
```
De behöver inte vara i korrekt ordning utan tex y kan komma före x.

## \*args & \*\*kwargs

Används när man har en funktion och inte vet hur många argument man behöver använda. Är det keys så använder man *kwargs* (keyword arguments), är det positionella använder man *args*. Det går att använda båda samtidigt. Man kan sen stoppa i oändligt med argument.

Exempel:
```python
def func(*args, **kwargs):
  print(args, kwargs)

func(1,2,3,4,5,one=0, two=1)
```
Skriver ut en tuple med: `(1, 2, 3, 4, 5) {'one': 0, 'two': 1}`.

För att använda kan man sen packa upp dem, exempel:
```python
def func(*args, **kwargs):
  print(*args)

func(1,2,3,4,5,one=0, two=1)
```
Skriver ut `1 2 3 4 5`.

Annat exempel som *inte fungerar*:
```python
def func(*args, **kwargs):
  print(**kwargs)

func(1,2,3,4,5,one=0, two=1)
```
Det fungerar inte eftersom det är samma som att skriva `print(one=0, two=1)`. Ger felet: *'one' is an invalid keyword argument for print()*

## Scope & Globals

Exempel:
```python
x = 'tim'

def func(name):
  x = Name

print(x)
func('changed')
print(x)
```
Detta skriver ut två rader med *tim på båda*. Dvs den ändras inte som man kanske kan tro. Detta beror på att x-variabeln innut funktionen är lokal, det betyder att den inte kan användas, nås eller ändras utifrån. Första x-variabeln är dock global, det betyder att den inte kan ändras direkt från funktionen, däremot är den tillgänglig innifrån funktionen. Försöker man ändra den innuti funktionen kommer man skapa en ny x-variabel som är lokal innuti funktionen.

**global keyword (använd ej)**
Det man kan göra i Python som är intressant är att använda *global*, tex `global x`, tex:
```python
x = 'tim'

def func(name):
  global x
  x = Name

print(x)
func('changed')
print(x)
```
Här printar den `tim changed` därför att man har berättat att man vill använda *x* som en *global* variabel. Detta är dock inte rekommenderat att göra i Python så undvik det.

## Exceptions
Används för att upptäcka och ta upp fel/undtantag.

**Raise exceptions**
Får kolla på andra ställen för att se vad funktionen med detta är, var väldigt kort här, verkar vara för felmeddelanden?

- `raise Exception('Bad')` - skriver ut "Exception: Bad"
- `raise FileExistsError('Text som beskriver felet här')`

**Handle exceptions**

try, except, finally.

```python
try:
  x = 7 / 0
except Exception as e:
  print(e)
finally:
  print('finally')
```
Med *try* försöker man exekvera den kod som finns innut det bracket. *except* sätter ev fel som variabel, här *e*. *finally* kör alltid. Verkar kunna användas till tex om man ska läsa en fil, så istället för att programmet krashar kan man göra något annat om det inte fungerar.

## Lambda
En *lambda* är en anonym funktion som bara är en rad lång. Man definerar inte lambda med *def* utan se nedan:
```python
x = lambda x: x + 5
```
Denna lambda kommer ta ett argument, här x, och kommer returnera x + 5.

Exempel här med print:
```python
x = lambda x: x + 5

print(x(2))
```
Skriver ut *7*.

Exempel med två variabler:
```python
x = lambda x, y: x + y

print(x(2, 3))
```
Skriver ut *5*.

Exemplen ovan är dock **inte rekommenderade**, rekommenderat sätt att använda lambda följer i *Map and Filter*-avsnittet här nedan.

## Map and Filter
*Map* och *Filter* kan ofta nyttja *Lambda*-funktionen.

**Map**
Map tar alla element från en lista och använder en *funktion* för att mappa dem till en ny lista. Det görs genom  `map(<FunktionJagVillAnvända>)`, funktionen kan tex vara *lambda*.

Exempel:
```python
x = [1,2,4,5,3,3,52,2,32,4,5,124,1,17,142,4]

mp = map(lambda i: i + 2, x)
print(list(mp))
```
Vi gör en lista, här till x-variabeln. Vi kör map-funktionen som tar alla element från x-variabeln och gör en ny lista med hjälp av en funktion, här lambda. Lambda-funktionen här tar varje element i x och adderar 2. Sedan skriver vi ut det genom att göra om *mp*-variabeln med list()-kommandot (detta för att map returnerar ett map-objekt, kan användas men in andra sammanhang) som ger en lista. Det som skrivs ut blir: `[3, 4, 6, 7, 5, 5, 54, 4, 34, 6, 7, 126, 3, 19, 144, 6]`.

**Filter**
Filter filtrerar ut till en ny lista eller objekt. Den funktion man använder ihop med filter måste returnera *True* eller *False* för ett element i taget. Man kan tex använda lambda med kriterier för vad som ska filtreras, lambda ger *True* eller *False* på om det ska returneras och *filter* tar bara med de som får *True*.

Exempel:
```python
x = [1,2,4,5,3,3,52,2,32,4,5,124,1,17,142,4]

fi = filter(lambda i: i % 2 == 0, x)
print(list(fi))
```
Denna kommer bara printa ut de tal som är jämna. Print: `[2, 4, 52, 2, 32, 4, 124, 142, 4]`.

Annat exempel, med en mer komplicerad funktion, här definerad genom *def* istället för en enrads genom *lambda*.
```python
x = [1,2,4,5,3,3,52,2,32,4,5,124,1,17,142,4]

def func(i):
  i = i * 3
  return i % 2 == 0

fi = filter(func, x)
print(list(fi))
```

## F Strings
Nya från Python 3.6. De är ett nytt fränt sätt att skapa och manipulera strings. Man kan använda det för att lägga med variabler osv utan att använda tex `+ str() +` osv.

Exempel:
```python
tim = 89
x = f'hello {6 + 8} {tim} {42 + 8}'
print(x)
```
Ger: `hello 14 89 50`

Man kan även printa f-strings direkt såhär:
```python
tim = 89
print(f'hello {tim}')
```
ger `hello 89`


## Saknas i denna videon
- Objektorientard programmering
- Advanced language features
