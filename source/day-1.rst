Den 1
=====

[30min] Seznámení
-----------------

Kdo jsme a proč tu jsme
.......................

XXX

Proč Python?
............

XXX

[30min] Kontrola instalace
--------------------------

Python
......

``python --version``, případně ``python3 --version``,
musí ukázat ``Python 3.4`` nebo ``Python 3.5``.

Editor
......

Textový editor musí být nastavený tak, aby odsazoval o 4 mezery a ukazoval
čísla řádků.

Git
...

``git --version`` musí fungovat.

Účet na GitHubu
...............

Účet musí být založený.


[2h 30m] Základy programování v Pytohnu 1
-------------------------------------

Řetězce a ``print()``
.....................

XXX: Vede Nasťa, viz její notebook

Typy objektů
.....

XXX: Čísla, řetězce, ``bool``, seznamy, slovníky; převádění typů; operace

Proměnné
........

XXX: Vede Nasťa, viz její notebook

Řetězce
.......

XXX: Vede Nasťa, viz její notebook

Slovníky
........

XXX: Vede Nasťa

[1h] Oběd
---------

Ňam ňam!

[2h 30m] Základy programování v Pytohnu 2
-------------------------------------

Program v souboru
.................

::

    print('Ahoj, světe!')

::

    print('Ahoj, světe!')
    print(tady je chyba)


Podmínky: ``if``
................

::

    strana = float(input("Zadej stranu čtverce: "))
    if strana < 0:
        print("Záporné čtverce neexistují")
    elif strana == 0:
        print("Čtverec je prázdný")
    else:
        print("Takový čtverec má obsah:", strana * strana)

::

    cislo = int(input("Zadej číslo: "))
    if cislo % 2 == 0:
        print('Číslo je sudé.')
    else:
        print('Číslo je liché.')
    if cislo % 5 == 0:
        print('Číslo je dělitelné pěti.')
    else:
        print('Číslo není dělitelné pěti.')

::

    cislo = float(input("Zadej číslo: "))
    if cislo == int(cislo):
        if cislo % 2 == 0:
            print('Číslo je sudé.')
        else:
            print('Číslo je liché.')
    else:
        print('Číslo není celé!')

Zkus napsat program, který se zeptá na dvě otázky:
    * Jsi šťastná?
    * Jsi bohatá?

a podle odpovědí odvětí:
    * *šťastná i bohatá* – Gratuluji!
    * *jen bohatá* – Zkus se víc usmívat!
    * *jen šťastná* – Zkus míň utrácet!
    * *ani jedno* – To je mi líto...

Cykly: ``for`` a ``while``
..........................

::

    for jmeno in 'Jana', 'Anna', 'Petra':
        print('Přichází', jmeno + '!')
        print(jmeno, 'zase odchází.')

::

    for cislo in range(10):
        if cislo % 2 == 0:
            print('Číslo', cislo, 'je sudé.')
        else:
            print('Číslo', cislo, 'je liché.')

::

    odpoved = input('Řekni Ááá! ')
    while odpoved != 'Ááá':
        print('Špatně, zkus to znovu!')
        odpoved = input('Řekni Ááá! ')

    print('Hotovo, ani to nebolelo!')

::

    while True:
        print('počkej, než se počítač unaví...')

::

    soucet = 0

    for cislo in 2, 945, 24, 3:
        soucet = soucet + cislo

    print(soucet)

Zkus napsat program, který sčítá čísla, která zadá uživatel.
Když uživatel zadá nulu, program skončí.


Ramena obrů: ``import``
.......................

::

    from random import randrange

    print('Házím kostkou...')

    vysledek = randrange(6) + 1

    print('Výsledek je', vysledek)

Zkus napsat program, který náhodně vybere a vypíše "kámen", "nůžky",
nebo "papír".

Funkce: ``def``
...............

::

    def pozdrav():
        print('Ahoj!')

    pozdrav()

::

    def pozdrav(jmeno):
        print('Ahoj,', jmeno + '!')

    pozdrav('Lucko')
    pozdrav('Aničko')
    pozdrav('Terko')

::

    def obsah_ctverce(strana):
        return strana * strana

    vysledek = obsah_ctverce(4)
    print(vysledek)

::

    def ano_nebo_ne(otazka):
        while True:
            odpoved = input(otazka + ' (ano/ne) ')
            if odpoved == 'ano':
                return True
            elif odpoved == 'ne':
                return False
            else:
                print('Nerozumím, zkus to znovu.')

    stastna = ano_nebo_ne('Jsi šťastná?')
    bohata = ano_nebo_ne('Jsi bohatá?')

Zkus napsat funkci ``def napis_hlasku(nazev, skore)``, která
např. po zavolání ``napis_hlasku('Tvoje', 256)`` vypíše:

    ::

        Tvoje skóre je 256
        Skvělé!

ale po zavolání ``napis_hlasku('Protivníkovo', 5)`` vypíše:

    ::

        Protivníkovo skóre je 5
        Aspoň něco...

Hlášky můžou být třeba:

* 1000 a víc: Světový rekord!
* 100 a víc: Skvělé!
* 10 a víc: Ujde to.
* jinak: Aspoň něco...

Čtení souborů: ``with``
.......................

::

    with open('basnicka.txt') as soubor:
        obsah = soubor.read()

    print(obsah)

::

    with open('basnicka.txt') as soubor:
        for radek in soubor:
            print(radek.rstrip())

Zkus napsat program, který přečte nějaký soubor,
všechna písmenka převede na velká, a výsledek vypíše.

Procvičení
..........

Napiš hru Oko bere:

* Začínáš s 0 body.
* Počítač v každém kole vypíše kolik máš bodů,
  a zeptá se, jestli chceš pokračovat.

  * Pokud ne, hra končí.
  * Pokud ano, počítač „otočí kartu“
    (náhodně vybere číslo od 2 do 10),
    a přičte její hodnotu k bodům.
  * Pokud máš víc než 21 bodů, prohráváš.

* Cílem hry je získat co nejvíc bodů, ideálně 21.


[30min] Zadání projektu
------------

Zadání domácího úkolu
.....................

Vymyslete téma projektu!
Při vymýšlení komunikujte s koučem. Řekne vám co jde jednoduše,
a na co by byla potřeba víc času.

Varianta 1: Webová aplikace
...........................

Naučíme se *vytvářet webové stránky*, a ptát se jejich návštěvníků na různé
informace, které pak na stránkách můžeme zobrazit.

Příklady:

    * Plánování akce (kdy má nejvíc lidí zároveň čas?)
    * Blog nebo portfolio
    * Jednoduchá webová hra (pexeso, textovka)

Nedoporučujeme web, který by nutně od začátku potřeboval registraci uživatelů
(ta se případně dá dopsat po kurzu).

Taky nedoporučujeme stránky založené na animacích: aby se cokoliv změnilo,
uživatel bude muset zmáčknout odkaz nebo tlačítko, a načte se nová stránka.

Varianta 2: Hra
...............

Naučíme se *kreslit animované obrázky* a *reagovat na klávesnici a myš*,
což je ideální na interaktivní hry. 

Příklady:

    * Had
    * Pong
    * Šachy, dáma, atd.
    * Asteroids
    * Skákačka (Mario)

Nedoporučujeme hru založenou na 3D grafice, efektech, nebo zvuku.

Bude-li tvá hra potřebovat scénář nebo mapu, do příště je vymysli.
Budeš-li do hry potřebovat obrázky, do příště si nějaké sežeň.
(Pokud stahuješ z Internetu, zkontroluj jestli máš právo obrázky
použít ve své hře. Vhodné obrázky se dají najít na `OpenGameArt`_, příklady:
`1 <http://opengameart.org/content/space-shooter-redux>`_,
`2 <http://opengameart.org/content/jumper-pack>`_,
`3 <http://opengameart.org/content/boardgame-tiles>`_.)

.. _OpenGameArt: http://opengameart.org/

Varianta 3: Nástroj pro příkazovou řádku
........................................

Taky se naučíme jak psát programy pro příkazovou řádku – nejjednodušší způsob,
jak nechat počítač za nás něco udělat nebo vypočítat.

Tenhle typ projektu by se měl zaměřit buď na automatizaci nějaké nudné
činnosti, kterou na počítači často děláš, nebo na analýzu informací.

Příklady:

    * Hromadné přejmenování fotek, automatické zařazení do adresářů
    * Analýza textu – počet písmen/slov, seznam nejčastějších slov,
      srovnání počtu teček/čárek/vykřičníků/otazníků, vyhledávání...
    * Obdobná analýza tweetů z Twitteru
    * Zpracování informací z tabulky exportované z Excelu nebo Google Docs
    * Analýza obrázku – Je obrázek spíš modrý, nebo spíš červený?
      Který ze dvou obrázků je kontrastnější?

Tenhle druh projektu je hodně flexibilní, doporučujeme každý nápad
konzultovat s koučem :)


[30min] Poděkování a rozloučení
-------------------------------

XXX
