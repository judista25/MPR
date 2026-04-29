---
marp: true
theme: default
paginate: true
style: |
  section {
    font-family: 'Segoe UI', sans-serif;
    font-size: 26px;
    padding: 40px 60px;
  }
  h1 { color: #2c3e50; font-size: 1.8em; }
  h2 { color: #2980b9; border-bottom: 2px solid #2980b9; padding-bottom: 6px; margin-bottom: 16px; }
  h3 { color: #34495e; font-size: 0.95em; margin-bottom: 8px; }
  table { font-size: 0.8em; width: 100%; }
  th { background: #2980b9; color: white; padding: 6px 10px; }
  td { padding: 5px 10px; }
  tr:nth-child(even) { background: #f0f4f8; }
  code { background: #f0f0f0; padding: 2px 6px; border-radius: 4px; font-size: 0.85em; }
  footer { font-size: 14px; color: #aaa; }
  section.title { text-align: center; justify-content: center; background: linear-gradient(135deg, #1a252f 0%, #2c3e50 100%); color: white; }
  section.title h1 { color: white; font-size: 2em; border: none; }
  section.title h2 { color: #3498db; border: none; font-size: 1.1em; }
  section.phase { background: #f8f9fa; }
  section.phase h2 { color: #7f8c8d; font-size: 0.85em; border: none; margin-bottom: 4px; }
  section.phase h1 { color: #2c3e50; font-size: 1.5em; }
---

<!-- _class: title -->

# Systém pro podporu řízení rizik v projektech

## 404 TNNF - Management projektů
**FIT VUT - jaro 2026**

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

| Člen | Role | Dokument |
|------|------|----------|
| Michael Babušík | MNG, ADM | Plán projektu, Uzavření projektu |
| Tomáš Hlásenský | DEV, DSGN | Návrh systému, Odhad ceny (EVM) |
| Michal Kaňkovský | QA | Testování, Metriky |
| Adam Krška | MNG, ADM | Záznamy schůzek, Protokoly etap |
| Vojtěch Kuchař | REQ | Konfigurační řízení, Sledování prací |
| Jan Lindovský | MNG | Výsledky oponentury, Seznam rizik |
| Pavel Marek | QA, ADM | Referenční a uživatelská příručka |
| Igor Mikula | REQ | Definice problému, Úvodní studie |
| Marcel Mravec | DEV, REQ | Specifikace požadavků, Analýza |
| Filip Polomski | DEV, MNG | Plán etapy implementace, LRM |

---

## Organizace práce

**Komunikace:** Discord / osobní schůzky

**Schůzky:** 1x měsíčně (plánování, kontrola, retrospektiva)

| Oblast | Nástroj |
|--------|---------|
| Verzování kódu | GitHub |
| Plán projektu | MS Project |
| Diagramy | PlantUML |
| Dokumentace | OverLeaf |

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

**Role:** `super_manager` · `project_manager` · `unverified`

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
│              Browser (Livewire)          │
└─────────────┬───────────────────────────┘
              │ HTTP / WebSocket
┌─────────────▼───────────────────────────┐
│          Laravel 12 (MVC)               │
│  Controllers │ Livewire Components      │
│  Models (Eloquent ORM)                  │
└─────────────┬───────────────────────────┘
              │
┌─────────────▼───────────────────────────┐
│            SQLite                        │
│  managers · projects · risks            │
└─────────────────────────────────────────┘
```

**Stack:** Laravel 12 · Livewire v3 · SQLite · PHP 8.3

---

## Datový model

```
managers          projects              risks
─────────         ────────              ─────
id                id                    id
name              name (unique/user)    name
email             description           impact      1–10
password (bcrypt) deadline              probability 1–10
role              manager_id ──────┐    score = i × p
                                   │    project_id ───┐
                  ◄────────────────┘                  │
                  ◄──────────────────────────────────┘
```

Cascade delete: projekt → rizika, manažer → projekty → rizika

---

## Návrh GUI

| Obrazovka | Popis |
|-----------|-------|
| Login / Register | Formulář, přesměrování na dashboard |
| Dashboard | Kartičky projektů — název, termín, počet rizik |
| Detail projektu | Tabulka rizik, filtry, záložky |
| Matice rizik | Heat-mapa 5×5 (X = pravděpodobnost, Y = dopad) |
| Správa manažerů | CRUD nad uživateli (jen admin) |

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

| ID | Scénář | Kritérium |
|----|--------|-----------|
| UT-01 | Registrace + přihlášení | < 500 ms |
| UT-02 | Vytvoření projektu | viditelný ihned (Livewire) |
| UT-03 | Přidání rizika + matice | matice do 300 ms |
| UT-04 | Ověření manažera (admin) | změna role OK, 403 pro ostatní |
| UT-05 | Validace formulářů | chyba do 200 ms bez POST |

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
