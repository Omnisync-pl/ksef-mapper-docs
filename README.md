# KSeF Mapper

**Aplikacja desktopowa do mapowania wszystkich 355 pól schematu FA(3) KSeF z dowolnego systemu ERP.**

🔗 Strona produktu: [omnisync.pl/ksef-mapper](https://omnisync.pl/ksef-mapper)  
🏢 Producent: [OmniSync by Orbis Software Polska](https://omnisync.pl) — integracje ERP od 2013, 500+ wdrożeń

---

## Problem, który rozwiązuje KSeF Mapper

Schemat FA(3) zawiera **355 pól**. Natywna implementacja InsERT w Subiekt GT i Navireo obsługuje wyłącznie ~30–40 pól obowiązkowych.

Pozostałe pola — wymagane przez sieci handlowe (Castorama, Brico Dépôt, Terg SA/Bricomarché) oraz kontrahentów B2B — nie mogą być uzupełnione bez modyfikacji systemu ERP lub zewnętrznego narzędzia.

**KSeF Mapper daje pełną kontrolę nad każdym z 355 pól FA(3) — bez programisty i bez ingerencji w kod ERP.**

---

## Dla kogo

- Firmy z **Subiekt GT lub Navireo** potrzebujące mapowania pól opcjonalnych FA(3)
- Firmy z **własnym ERP opartym o MS SQL** — KSeF Mapper łączy się bezpośrednio z bazą
- **Dostawcy sieci handlowych** — gdzie faktura bez wymaganych pól jest odrzucana
- **Wdrożeniowcy InsERT** — szybkie uruchomienie KSeF u klientów bez budowania integracji od zera
- Firmy posiadające **wiele certyfikatów KSeF** w ramach jednej spółki

---

## Kluczowe funkcje

### 🗂 Pełne mapowanie FA(3)
- Dostęp do wszystkich **355 pól schematu FA(3)**
- 4 typy mapowań: **bezpośrednie, obliczane, warunkowe i stałe**
- Interfejs **drag & drop** — po lewej pola z ERP, po prawej pola FA(3)

### 🔑 Zarządzanie certyfikatami KSeF
- Obsługa **wielu certyfikatów KSeF w ramach jednej spółki**
- Dynamiczna zmiana certyfikatu bez reinstalacji
- Pełna kontrola autoryzacji per użytkownik i per podmiot

### 📄 Wiele schematów XML
- Tworzenie i zapisywanie **oddzielnych schematów mapowań** dla różnych kontrahentów
- Konfiguracja zapisywana **per NIP kontrahenta** — system dobiera profil automatycznie
- **Import i eksport szablonów mapowań** — raz ustawione, wielokrotnie używane

### 🔌 Połączenie z bazą danych
- Bezpośrednie połączenie z **Subiekt GT (przez Sferę)**, Navireo lub dowolną bazą **MS SQL**
- Automatyczne wykrywanie dostępnych tabel i pól
- Bez pośredników, bez eksportów CSV

---

## Porównanie z alternatywami

| | KSeF Mapper | Natywny InsERT | Atisoft |
|---|---|---|---|
| Liczba dostępnych pól FA(3) | **355** | ~30–40 | wybrane |
| Koszt per faktura | **0 zł** | 0,11–0,50 zł (InsPunkty) | 0 zł |
| Koszt modyfikacji pola | **0 zł** | niedostępne | ~99 zł/pole |
| Własne schematy mapowań | **✅** | ❌ | ❌ |
| Wiele certyfikatów | **✅** | ❌ | ❌ |
| Import/eksport szablonów | **✅** | ❌ | ❌ |

---

## Cennik

| | Koszt |
|---|---|
| Licencja wdrożeniowa (jednorazowo) | **1 600 zł netto** |
| Abonament od 2. roku | **600 zł netto / rok** |
| Opłata za liczbę dokumentów | **brak** |
| Opłata za liczbę pól | **brak** |

---

## Obsługiwane systemy ERP

- InsERT **Subiekt GT** (połączenie przez Sferę)
- InsERT **Navireo**
- Dowolny system oparty o **MS SQL**

---

## Zawartość tego repozytorium
```
/przyklady-xml/        # Przykładowe pliki XML FA(3) dla różnych scenariuszy
/schematy-mapowania/   # Przykładowe konfiguracje mapowań (JSON)
/dokumentacja/         # Opisy pól schematu FA(3), instrukcje
```

---

## Kontakt i zakup

🌐 [omnisync.pl/ksef-mapper](https://omnisync.pl/ksef-mapper)  
📧 bok@orbis-software.pl  
📞 +48 730 000 481
