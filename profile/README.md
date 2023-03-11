# SegmentONE git

## Naming scheme

Tato sekce popisuje pravidla pro pojmenování repozitářů, branchí a commitů, včetně konvence pro anglické a české názvy. Správné použití těchto pravidel pomáhá zvýšit přehlednost a usnadnit komunikaci v týmu, což v konečném důsledku vede k efektivnější práci na projektu.
- **Anglicky**: názvy, commity, a komentáře v kódu
- **Česky**: pull requesty, README a komentáře přímo v Githubu

|  | Příklad | Naming konvence 
|--|--|--|
| Repozitář | *test_repo, chytrey_app_wrapper* | Jednotlivá slova oddělena '_' (snake case) |
| Výchozí branch | *main, fix, production* | - |
| Vývojová branch | *feat/add_login_screen* | Prefix *feat*/ následován názvem feature |
| Commit | *feat: added login button*, *fix: correct font* | Prefix *feat/fix:*  následován názvem commitu |


## Branching scheme
Každý repozitář obsahuje výchozí branche, do kterých je možný push pouze po **schváleném pull requestu** team leaderem.

| Default branch | Účel |
|--|--|
| main | Nejvyšší branch pouze pro finální verze jednotlivých features |
| fix | Pomocný univerzální branch pro mále opravy dílčích problémů |
| production | Produkční branch pro archiv verzí projektu (implementace CI/CD) |

Pro vývoj jednotlivých features, je vždy vytvořena samostatná branch podle *Naming scheme*. Ve chvíli kdy je feature připravena pro přidání do *main*, je vytvořen pull request, který schválí team leader.

## Commit scheme
Pro tvorbu commitů platí následující pravidla, která jsou popsána v tabulce v sekci *Naming scheme*. Každý commit by měl mít popisek, který začíná prefixem, který specifikuje typ commitu. Prefixy pro commit typy jsou následující:

-   `feat/`: Nová funkcionalita nebo vlastnost
-   `fix/`: Oprava chyby nebo bugu
-   `refactor/`: Úprava kódu bez změny v chování aplikace 
-   `docs/`: Změna v dokumentaci

Následně následuje samotný popis změny v kódu, který by měl být stručný a jasně popisovat provedenou změnu.

## Pull requests (PRs)
### Vytváření PR
Pull Requesty slouží k tomu, aby autor feature mohl odeslat svou práci na review a umožnil tak kontrolu vývojových branchí a zajištění funkčnosti celého projektu. Každý Pull Request vytváří autor feature a v popisu uvádí stručné shrnutí změn, které feature obsahuje, a pokud je to relevantní, také jak se tyto změny projeví v celkové funkčnosti projektu. Na závěr autor přidává team leadera jako reviewera.
### Schvalování PR a merge
Každý Pull Request musí projít kontrolou team leadera, který zkontroluje jeho funkčnost i kvalitu kódu. Pokud je Pull Request funkční a kód odpovídá stanoveným standardům, team leader provede merge do žádaného branchi. Pokud není, napíše team leader poznámku k Pull Requestu, kterou autor musí před mergem opravit.

### Konflikty
Při pokusu o merge branchů, které obsahují konflikty, Git ukáže hlášku, která informuje, které soubory jsou konfliktní a ve kterých řádcích se konflikt vyskytuje. Konfliktní soubory budou mít v souboru označeny konflikty.

Konflikt v souboru vypadá následovně:

    <<<<<<< HEAD
    Změna provedená v aktuální branchi
    =======
    Změna provedená v druhé branchi
    >>>>>>> feat/add_login_screen 

V textu výše jsou vidět dvě verze stejné části kódu oddělené `<<<<<<< HEAD` a `>>>>>>> feat/add_login_screen`. Tyto značky, ukázují, které změny byly provedeny v které branchi.

Pro řešení konfliktů je nutné ručně upravit konfliktní soubory tak, aby obsahovaly správnou verzi kódu. Po úpravě je třeba změny commitovat a pushnout.

Nejlepší praxe pro řešení konfliktů je **průběžně synchronizovat** svůj kód se vzdáleným repozitářem, aby se minimalizovalo riziko vzniku konfliktů.

Konflikty vždy řeší ten, koho **určí team leader**. Nejlépe aby team leader sám řešil konflikty v kódu. Pokud se konflikty vyskytnou, team leader sdělí autorovi, aby je vyřešil, nebo je vyřeší sám. Je důležité, aby konflikty byly vyřešeny co nejdříve a zabránilo se ztrátě času.

## Základní pravidla pro psaní kódu

 - Kód by měl být napsán srozumitelně a jednoznačně tak, aby byl snadno čitelný pro ostatní členy týmu
 - Názvy proměnných, funkcí, tříd a dalších identifikátorů by měly být v angličtině a měly by být výstižné a v souladu s konvencemi daného jazyka
 - Kód by měl být dobře strukturovaný a organizovaný, aby byl snadno udržovatelný a rozšiřitelný
 - Používání komentářů by mělo být omezeno na minimum, pokud je to nezbytně nutné pro pochopení kódu
 - Velmi důležité funkce by měly obsahovat dokumentační komentáře pro IDE
 - Používání jednotného stylu psaní kódu v celém týmu
 -  Omezení používání globálních proměnných a funkcí
 - Zamezení zbytečné duplicity kódu a využívání správného refaktorování kódu
