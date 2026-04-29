---
marp: true
theme: default
paginate: true
footer: "404 TNNF · FIT VUT 2026"
style: |
    section {
      font-family: 'Segoe UI', sans-serif;
      font-size: 26px;
      padding: 40px 55px;
      justify-content: flex-start;
      background: #0f1923;
      color: #dce8f0;
      border-left: 5px solid #29abe2;
    }
    h1 { color: #ffffff; font-size: 1.7em; margin-bottom: 12px; }
    h2 {
      color: #29abe2;
      font-size: 1.15em;
      padding-bottom: 6px;
      margin-bottom: 16px;
      border-bottom: 2px solid transparent;
      border-image: linear-gradient(90deg, #29abe2, transparent) 1;
    }
    h3 { color: #8baab8; font-size: 0.95em; margin-bottom: 8px; }
    ul li::marker { color: #29abe2; }
    table { font-size: 0.8em; width: 100%; border-collapse: collapse; }
    th { background: #29abe2; color: #1e3448; padding: 7px 10px; }
    td { padding: 5px 10px; color: #1e3448; border-bottom: 1px solid #1e3448; }
    tr:nth-child(even) { background: #1a2a3a; }
    img { max-width: 100%; border: 1px solid #29abe230; border-radius: 4px; padding: 5px; max-height: 460px; margin: 0 auto; display: block; }
    code { background: #1a2a3a; color: #7dd3fc; border: 1px solid #29abe250; padding: 2px 6px; border-radius: 4px; font-size: 0.85em; }
    pre { background: #1a2a3a; border: 1px solid #29abe240; border-radius: 6px; padding: 12px; }
    pre code { border: none; background: transparent; }
    blockquote { border-left: 4px solid #29abe2; background: #1a2a3a; margin: 8px 0; padding: 10px 20px; border-radius: 0 6px 6px 0; color: #8baab8; }
    footer { font-size: 14px; color: #8baab8; }
    section.title {
      text-align: center;
      justify-content: center;
      background: linear-gradient(135deg, #0a0f1a 0%, #1a2a3a 100%);
      color: white;
      border-left: none;
    }
    section.title h1 { color: #29abe2; font-size: 4.5em; font-family: 'Courier New', monospace; letter-spacing: 0.08em; margin-bottom: 0; }
    section.title h2 { color: #ffffff; border: none; font-size: 1.0em; letter-spacing: 0.15em; text-transform: uppercase; margin-top: 0; margin-bottom: 24px; }
    section.title h3 { color: #8baab8; font-size: 0.85em; font-weight: 400; }
    section.title footer { color: rgba(255,255,255,0.25); }
    section.phase footer { color: rgba(255,255,255,0.3); }
    section.phase {
      background: linear-gradient(135deg, #29abe2 0%, #1a5f8a 100%);
      justify-content: center;
      text-align: center;
      border-left: none;
    }
    section.phase h2 { color: rgba(255,255,255,0.75); font-size: 0.9em; border: none; margin-bottom: 8px; font-weight: 400; }
    section.phase h1 { color: #ffffff; font-size: 1.8em; }
---

<!-- _class: title -->

# 404

## Team Name Not Found

### Systém pro podporu řízení rizik v projektech

**FIT VUT · jaro 2026**

---

## Agenda

1. Tým a organizace
2. Definice problému + Úvodní studie _(Igor Mikula)_
3. Specifikace požadavků _(Marcel Mravec)_
4. Plán projektu _(Michael Babušík)_
5. Návrh systému _(Tomáš Hlásenský)_
6. Plán etapy implementace + LRM _(Filip Polomski)_
7. Konfigurační řízení + Sledování _(Vojtěch Kuchař)_
8. Seznam rizik + Oponentura _(Jan Lindovský)_
9. Testování + Metriky _(Michal Kaňkovský)_
10. Uživatelská příručka _(Pavel Marek)_
11. Záznamy + Uzavření projektu _(Adam Krška, Michael Babušík)_
12. Demo + Q&A

---

## Tým 404 Team Name Not Found

| Člen             | Role      | Dokument                             |
| ---------------- | --------- | ------------------------------------ |
| Michael Babušík  | MNG, ADM  | Plán projektu, Uzavření projektu     |
| Tomáš Hlásenský  | DEV, DSGN | Návrh systému, Odhad ceny (EVM)      |
| Michal Kaňkovský | QA        | Testování, Metriky                   |
| Adam Krška       | MNG, ADM  | Záznamy schůzek, Protokoly etap      |
| Vojtěch Kuchař   | REQ       | Konfigurační řízení, Sledování prací |
| Jan Lindovský    | MNG       | Výsledky oponentury, Seznam rizik    |
| Pavel Marek      | QA, ADM   | Referenční a uživatelská příručka    |
| Igor Mikula      | REQ       | Definice problému, Úvodní studie     |
| Marcel Mravec    | DEV, REQ  | Specifikace požadavků, Analýza       |
| Filip Polomski   | DEV, MNG  | Plán etapy implementace, LRM         |

---

## Organizace práce

**Komunikace:** Discord / osobní schůzky

**Schůzky:** 1x měsíčně (plánování, kontrola, retrospektiva)

| Oblast         | Nástroj    |
| -------------- | ---------- |
| Verzování kódu | GitHub     |
| Plán projektu  | MS Project |
| Diagramy       | PlantUML   |
| Dokumentace    | OverLeaf   |

---

<!-- _class: phase -->

## Igor Mikula

# Definice problému + Úvodní studie

---

## Definice problému + Úvodní studie

_TODO: Igor doplní obsah_

---

<!-- _class: phase -->

## Marcel Mravec

# Specifikace požadavků

---

## Specifikace požadavků

**Systém umožňuje:**

- Správu projektů, manažerů a rizik
- Kvalitativní analýzu rizik (matice)
- Filtrování a přehledy rizik

**Mimo rozsah:** Helpdesk, AI doplňování rizik

**Role:** `admin (super_manager)` · `project_manager` · `unverified`

---

<!-- _class: phase -->

## Michael Babušík

# Plán projektu

---

## Plán projektu

_TODO: Miki doplní obsah (harmonogram, milníky, zdroje)_

---

<!-- _class: phase -->

## Tomáš Hlásenský

# Návrh systému

---

## Architektura

```
┌─────────────────────────────────────────┐
│              Browser (Livewire)         │
└─────────────┬───────────────────────────┘
              │ HTTP / WebSocket
┌─────────────▼───────────────────────────┐
│          Laravel 12 (MVC)               │
│  Controllers │ Livewire Components      │
│  Models (Eloquent ORM)                  │
└─────────────┬───────────────────────────┘
              │
┌─────────────▼───────────────────────────┐
│            SQLite                       │
│  managers · projects · risks            │
└─────────────────────────────────────────┘
```

**Stack:** Laravel 12 · Livewire v3 · SQLite · PHP 8.3

---

## Datový model

![ER Diagram](../out/xhlase01/diagrams/DB-Schema/DB-Schema.png)

Cascade delete: projekt → rizika, manažer → projekty → rizika

---

## Návrh GUI

| Obrazovka        | Popis                                          |
| ---------------- | ---------------------------------------------- |
| Login / Register | Formulář, přesměrování na dashboard            |
| Dashboard        | Kartičky projektů — název, termín, počet rizik |
| Detail projektu  | Tabulka rizik                                  |
| Matice rizik     | Heat-mapa 5×5 (X = pravděpodobnost, Y = dopad) |
| Správa manažerů  | CRUD nad uživateli (jen admin)                 |

---

<!-- _class: phase -->

## Filip Polomski

# Plán etapy implementace + LRM

---

## Plán etapy implementace + LRM

_TODO: Filip doplní obsah_

---

<!-- _class: phase -->

## Vojtěch Kuchař

# Konfigurační řízení + Sledování prací

---

## Konfigurační řízení + Sledování prací

_TODO: Vojta doplní obsah_

---

<!-- _class: phase -->

## Jan Lindovský

# Seznam rizik + Výsledky oponentury

---

## Seznam rizik + Výsledky oponentury

_TODO: Lindak doplní obsah_

---

<!-- _class: phase -->

## Michal Kaňkovský

# Zpráva o testování + Metriky

---

## Uživatelské testy

| ID    | Scénář                   | Kritérium                      |
| ----- | ------------------------ | ------------------------------ |
| UT-01 | Registrace + přihlášení  | < 500 ms                       |
| UT-02 | Vytvoření projektu       | viditelný ihned (Livewire)     |
| UT-03 | Přidání rizika + matice  | matice do 300 ms               |
| UT-04 | Ověření manažera (admin) | změna role OK, 403 pro ostatní |
| UT-05 | Validace formulářů       | chyba do 200 ms bez POST       |

_TODO: Michal doplní metriky produktu_

---

<!-- _class: phase -->

## Pavel Marek

# Referenční a uživatelská příručka

---

## Referenční a uživatelská příručka

_TODO: Pavel doplní obsah_

---

<!-- _class: phase -->

## Adam Krška + Michael Babušík

# Záznamy schůzek + Uzavření projektu

---

## Záznamy schůzek + Uzavření projektu

_TODO: Adam + Miki doplní obsah_

---

## Demo

**Průchod aplikací:**

1. Registrace → dashboard
2. Nový projekt → přidání rizik
3. Přepnutí na matici rizik (heat-mapa)
4. Admin: ověření nového manažera

---

## Shrnutí

_TODO: Shrnutí klíčových bodů a přínosů projektu_

---

<!-- _class: title -->

# Dotazy?

**Tým 404 TNNF**
