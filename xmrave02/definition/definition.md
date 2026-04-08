# Specifikace požadavků na software (DSP)

## Podle IEEE standardu 830-1984

---

## 1. Úvod

### 1.1 Účel systému

Popisuje, proč má být daná aplikace vytvořena a vymezuje zamýšlený okruh čtenářů dokumentu.

### 1.2 Rozsah systému

Udvádí seznam softwarových systémů, které mají být vytvořeny, co se od nich má (případně nemá) očekávat a jak budou používány (včetně přínosů).

### 1.3 Definice, zkratky a akronymy

Poskytuje definice termínů používaných v DSP, aby jej mohl číst i neodborník.

### 1.4 Reference

Obsahuje úplný seznam všech dokumentů, na něž se daný DSP odkazuje (z nichž vychází) a odkud mohou být získány.

### 1.5 Přehled dokumentu

Popisuje, jak je zbytek DSP zorganizován a co obsahuje.

---

## 2. Všeobecný popis

### 2.1 Kontext produktu

Udvádí vztahy produktu k ostatním produktům, s nimiž má spolupracovat v rámci většího systému. Popisuje jednotlivé systémové komponenty a jejich rozhraní, jakož i postavení v organizačním kontextu uživatele.

### 2.2 Základní přehled funkcí

Uvádí shrnutí funkcí poskytovaných softwarem bez uvedení detailů. Je zaměřen především na vrcholový management zákazníka a příležitostné čtenáře.

### 2.3 Profil uživatele

Uvádí všeobecné charakteristiky budoucích uživatelů softwaru (obyčejných i administrátorů) a jaký vliv to má na specifikaci požadavků.

### 2.4 Přehled omezujících podmínek

Popisuje okolnosti omezující volby vývojářů při návrhu softwaru:
- Dostupný hardware pro vývoj a provoz
- Časové či jiné limity
- Nutnost dodržet rozhraní ke stávajícímu softwaru
- Použité protokoly
- Bezpečnostní požadavky
- Další omezení

### 2.5 Předpoklady a závislosti

Uvdádí všechny faktory, od nichž jsou odvozeny nebo na nichž závisí požadavky specifikované v dokumentu, kromě již uvedených omezení. Např. co musí být organizačně a technicky připraveno na místě zákazníka, než bude možné systém nainstalovat a provozovat.

---

## 3. Specifikace požadavků

Obsahuje detailní informace potřebné pro vytvoření návrhu produktu. Detaily by měly být specifikované po jednotlivých funkcích systému, splňovat vlastnosti uvedené v kvalitativních charakteristikách DSP a být doplněné křížovými referencemi k příslušným částem Úvodu a Všeobecného popisu.

### 3.1 Klasifikace požadavků

Požadavky je možné klasifikovat do kategorií:

| Kategorie | Popis |
|-----------|-------|
| **Požadavky na funkce** | Funkcionalita systému |
| **Požadavky na výkonnost** | Výkonnostní charakteristiky |
| **Požadavky na vlastnosti (atributy)** | Atributy kvality |
| **Vnější rozhraní** | Rozhraní systému |

### 3.2 Struktura informací (dat)

Popis dat, které systém udržuje/zpřístupňuje, ve formě:
- Výčtu položek
- Odkazu do datového slovníku
- ERD diagramů

### 3.3 Detailní specifikace funkcionality

Pro každou funkci systému:
- Identifikátor funkce
- Název funkce
- Popis funkce
- Vstupy
- Výstupy
- Závislosti
- Omezení

---

## 4. Ověřovací kritéria

Z jistého pohledu nejdůležitější část DSP. Definuje, jak bude možné poznat dobrou implementaci systému.

### 4.1 Rozsah výkonnostních charakteristik

- Doby odezvy
- Velikosti dat
- Další metriky

### 4.2 Druhy testů

Jaké druhy testů bude třeba vykonat pro ověření funkcionality a výkonnosti.

### 4.3 Platné odezvy

Specifikace reakcí, které má software poskytnout.

### 4.4 Specifické případy

Specifikace chování systému pro specifické případy a chybové stavy.

---

## Přílohy

- Obsah
- Rejstřík
- ERD a DFD diagramy
- Podrobné popisy vstupně/výstupních formátů
- Vysvětlení terminologie a grafických notací

---

## Vlastnosti dobrého DSP

### Jednoznačnost
Jeden každý požadavek má právě jednu interpretaci. Pozor na to, že přirozený jazyk je od principu nejednoznačný.

### Úplnost
Obsahuje všechny důležité požadavky (na funkce, vlastnosti, omezení), definuje odezvy na všechny realizovatelné kombinace vstupních dat (platných i neplatných), splňuje případné příslušné normy.

### Verifikovatelnost
Jeden každý požadavek je verifikovatelný - existuje cenově efektivní proces, pomocí něhož je možno ověřit, že software odpovídá tomuto požadavku. Důraz na kvantifikovatelnost a měřitelnost požadavků.

### Konzistence
Neobsahuje navzájem konfliktní množinu požadavků (rozdílné termíny pro stejný objekt, konfliktní požadavky na objekt, časově nebo logicky konfliktní specifikace).

### Modifikovatelnost
Struktura a styl dovolují snadné, úplné a konzistentní doplňování případných změn. Dokument by měl být psaný konzistentním stylem bez redundancí a obsahovat seznamy pro křížové reference.

### Trasovatelnost
Je zřejmé, odkud vzešly jednotlivé požadavky a na každý požadavek je možné se explicitně odkazovat v další dokumentaci.

---

## Čeho se vyvarovat při psaní DSP

### Vágní formulace
Všechny požadavky musí být popsány jednoznačně a přesně. Formulace typu "program by mohl být použit pro..." jsou nepřípustné.

**Správně:** Program *bude použit* pro...

### Design zakomponovaný do požadavků
DSP specifikuje *co* má software dělat, nikoli *jak* toho dosáhnout. Netýká se rozdělení systému na moduly, specifikace datových struktur, toku řízení apod.

### Požadavky na proces
DSP by se měl týkat softwarového produktu, nikoli procesu jeho vytváření. Požadavky na termíny dodání, zajištění kvality a procedury pro verifikaci mají být specifikovány v jiných dokumentech kontraktu.

---

## Formální náležitosti dokumentu

1. **Titulní stránka** - Název týmu, projektu, dokumentu, autoři, datum
2. **Obsah** - Pro dokumenty delší než 2 strany
3. **Úvod** - Účel a přehled zbytku dokumentu, tabulka zkratek
4. **Text dokumentu** - Členěný na číslované oddíly
5. **Rejstřík** - Pro rozsáhlé dokumenty

---

## Rozsah dokumentu

cca 5-10 stran textu (dle šablony předmětu MPR)

---

*Zdroj: [Pressman], Standard ANSI/IEEE číslo 830-1984 [IEEE Guide to Software Requirements Specifications, IEEE 1984]*
