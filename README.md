# KSeF Mapper

**Aplikacja desktopowa do mapowania wszystkich 355 pól schematu FA(3) KSeF z dowolnego systemu ERP opartego o Microsoft SQL Server.**

🔗 **Strona produktu:** [omnisync.pl/ksef-mapper](https://omnisync.pl/ksef-mapper)  
📖 **Baza wiedzy FA(3):** [omnisync.pl/baza-wiedzy](https://omnisync.pl/baza-wiedzy)  
🏢 **Producent:** [OmniSync by Orbis Software Polska](https://omnisync.pl) — integracje ERP od 2013, 500+ wdrożeń  
🤝 **Program partnerski:** [omnisync.pl/partnerzy](https://omnisync.pl/partnerzy)

---

## Problem który rozwiązuje KSeF Mapper

Schemat FA(3) Krajowego Systemu e-Faktur zawiera **355 pól**. Natywna implementacja KSeF w InsERT (Subiekt GT, Navireo) obsługuje wyłącznie **~30–40 pól obowiązkowych**.

Sieci handlowe, factorzy i instytucje publiczne wymagają pól fakultatywnych, których ERP nie wypełnia:

| Wymagane pole FA(3) | Kto wymaga | Problem bez KSeF Mapper |
|---------------------|------------|------------------------|
| `Podmiot3` z kodem GLN | Sieci handlowe, factorzy | Faktura odrzucana przez system sieci / EDI |
| Numer zamówienia PO w `DodatkowyOpis` | Kaufland, OBI, Castorama, PSB... | Brak dopasowania faktury do zamówienia |
| Kod GLN miejsca dostawy | Systemy EDI sieci | Ręczna weryfikacja, opóźnienie płatności |
| Dane factora w `Podmiot3` (rola 3) | Firmy faktoringowe | Blokada automatycznej identyfikacji cesji |
| Numer umowy / MPK | Instytucje publiczne, JST, PGE | Faktura trafia do ręcznej weryfikacji |
| Indeksy towarów sieci (GTIN) | Kaufland, OBI, Castorama | Brak automatycznego dopasowania pozycji |

Szczegółowy opis problemu: [omnisync.pl/integracja-ksef-erp](https://omnisync.pl/integracja-ksef-erp)

---

## Funkcje

### Mapowanie pól FA(3)
- **Wizualny edytor drag & drop** — pole z bazy ERP → pole XML FA(3)
- **355 pól schematu FA(3)** — pełna kontrola nad każdym polem
- **4 typy mapowań:**
  - Bezpośrednie (pole ERP → pole XML)
  - Obliczane (dowolna formuła SQL)
  - Warunkowe (IF/CASE na danych ERP)
  - Stałe (wartość wpisana ręcznie)

### Profile i szablony
- **Profile mapowania per NIP kontrahenta** — system automatycznie dobiera właściwy profil przy każdej wysyłce
- **Gotowe szablony dla sieci handlowych** — importujesz szablon, konfigurujesz pod swoje dane:
  - Kaufland
  - OBI (Superhobby Market Budowlany)
  - Castorama
  - Brico Dépôt
  - Leroy Merlin
  - Terg SA (Media Expert)
  - Merkury Market
  - Grupa PSB (PSB Mrówka, Składy PSB, PSB Profi)
  - PGE (Polska Grupa Energetyczna)

### Pełny cykl KSeF
1. Pobranie danych z bazy ERP (Subiekt GT / Navireo / dowolny MS SQL)
2. Mapowanie pól na schemat FA(3) według profilu kontrahenta
3. Generowanie pliku XML FA(3)
4. **Walidacja offline** — XSD + reguły biznesowe przed wysyłką
5. Podpis certyfikatem KSeF (lokalnie, certyfikat nie opuszcza infrastruktury)
6. Wysyłka do KSeF przez API
7. Pobranie UPO (Urzędowego Poświadczenia Odbioru)

### Certyfikaty KSeF
- Obsługa **wielu certyfikatów** — per użytkownik i per podmiot (NIP)
- Dynamiczna zmiana certyfikatu bez restartu aplikacji
- Certyfikat przechowywany **lokalnie** — nie przechodzi przez serwery zewnętrzne
- Obsługa trybu offline24 z kodem QR na wizualizacji faktury

---

## Obsługiwane systemy ERP

| System | Status |
|--------|--------|
| InsERT Subiekt GT | ✅ Aktywny |
| InsERT Navireo | ✅ Aktywny |
| Dowolna baza MS SQL | ✅ Aktywny |

KSeF Mapper łączy się z bazą danych bezpośrednio przez MSSQL — nie wymaga modyfikacji systemu ERP ani licencji Sfera.

---

## Porównanie z natywną obsługą KSeF w InsERT

| Cecha | Natywny InsERT | KSeF Mapper |
|-------|:---:|:---:|
| Pola obowiązkowe FA(3) | ✅ ~30–40 | ✅ ~30–40 |
| Pola opcjonalne FA(3) — wszystkie 355 | ❌ | ✅ |
| `Podmiot3` z GLN (factor, sieć handlowa) | ❌ | ✅ |
| Szablony per sieć handlowa | ❌ | ✅ 9 sieci |
| Profile mapowania per NIP kontrahenta | ❌ | ✅ |
| Wizualny edytor mapowania (drag & drop) | ❌ | ✅ |
| Walidacja offline XSD + reguły biznesowe | ❌ podstawowa | ✅ pełna |
| Wiele certyfikatów KSeF per podmiot | ❌ | ✅ |
| Obsługa dowolnej bazy MS SQL | ❌ | ✅ |
| Opłata za wysłany dokument | ❌ 0,11–0,50 zł (InsPunkty) | ✅ 0 zł |

---

## Cennik

| | Kwota |
|--|--|
| Licencja roczna (pierwszy rok) | **1 600 PLN netto** |
| Odnowienie od drugiego roku | **600 PLN netto / rok** |
| Opłata za dokument KSeF | **0 PLN** — bez limitu |

Instalacja i konfiguracja: kilka godzin.

---

## Baza wiedzy FA(3)

Artykuły techniczne o schemacie FA(3), polach opcjonalnych i wymaganiach sieci handlowych:

| Artykuł | Link |
|---------|------|
| Co to jest element Podmiot3 w FA(3) i kiedy jest wymagany? | [→](https://omnisync.pl/baza-wiedzy/podmiot3-fa3) |
| Pola obowiązkowe vs opcjonalne vs fakultatywne w FA(3) — pełna lista | [→](https://omnisync.pl/baza-wiedzy/pola-fa3-obowiazkowe-opcjonalne) |
| Jak wypełnić numer zamówienia zakupowego (PO) w e-Fakturze KSeF? | [→](https://omnisync.pl/baza-wiedzy/numer-zamowienia-po-ksef) |
| Kod GLN w KSeF — co to jest, skąd go wziąć i jak wpisać do FA(3)? | [→](https://omnisync.pl/baza-wiedzy/gln-ksef-fa3) |
| KSeF a EDI — jak działa fakturowanie gdy sieć rozlicza się przez EDI? | [→](https://omnisync.pl/baza-wiedzy/ksef-edi-fakturowanie) |
| Jak wskazać factora w e-Fakturze KSeF? Podmiot3 rola i kod GLN | [→](https://omnisync.pl/baza-wiedzy/factor-podmiot3-ksef) |
| KSeF Subiekt GT — co natywna obsługa InsERT pokrywa, a czego nie? | [→](https://omnisync.pl/baza-wiedzy/ksef-subiekt-gt-co-pokrywa) |
| Certyfikat KSeF — rodzaje, jak pobrać, jak skonfigurować w ERP | [→](https://omnisync.pl/baza-wiedzy/certyfikat-ksef-rodzaje) |
| Walidacja offline FA(3) — jak sprawdzić e-Fakturę przed wysyłką? | [→](https://omnisync.pl/baza-wiedzy/walidacja-offline-fa3) |
| KSeF tryb offline24 — kiedy używać i jak działa? | [→](https://omnisync.pl/baza-wiedzy/ksef-tryb-offline24) |
| Mechanizm podzielonej płatności (MPP) w KSeF — które pola FA(3)? | [→](https://omnisync.pl/baza-wiedzy/mpp-ksef-fa3) |
| KSeF dla dostawców Kaufland — wymagania pól FA(3) | [→](https://omnisync.pl/baza-wiedzy/ksef-kaufland-pola-fa3) |
| KSeF dla dostawców OBI — wymagania pól FA(3) | [→](https://omnisync.pl/baza-wiedzy/ksef-obi-pola-fa3) |
| KSeF dla dostawców PSB (Mrówka, PSB Profi) — wymagania pól FA(3) | [→](https://omnisync.pl/baza-wiedzy/ksef-psb-pola-fa3) |
| Faktury KSeF dla jednostek samorządu terytorialnego (JST) | [→](https://omnisync.pl/baza-wiedzy/ksef-jst-faktury-publiczne) |
| InsPunkty InsERT a KSeF — ile kosztuje wysyłka faktur? | [→](https://omnisync.pl/baza-wiedzy/inspunkty-ksef-koszty) |
| Mapowanie SQL w KSeF Mapper — formuły obliczane i warunkowe | [→](https://omnisync.pl/baza-wiedzy/mapowanie-sql-ksef-mapper) |
| KSeF a faktury korygujące — jak wystawić korektę w FA(3)? | [→](https://omnisync.pl/baza-wiedzy/ksef-faktura-korygujaca) |
| KSeF dla firm z wieloma certyfikatami — zarządzanie autoryzacją | [→](https://omnisync.pl/baza-wiedzy/ksef-wiele-certyfikatow) |

---

## Dla kogo?

- **Dostawcy sieci handlowych** — Kaufland, OBI, Castorama, Leroy Merlin, Brico Dépôt, Terg SA (Media Expert), Merkury Market, Grupa PSB, PGE i inne sieci wymagające pól opcjonalnych FA(3)
- **Firmy korzystające z faktoringu** — factor musi być wskazany w `Podmiot3` z kodem GLN
- **Partnerzy InsERT** — wdrożenie KSeF Mapper u klientów Subiekt GT i Navireo obsługujących sieci EDI
- **Firmy z własnym ERP opartym o MS SQL** — mapowanie FA(3) bez budowania integracji od zera

---

## Program partnerski

Firma IT, biuro rachunkowe lub agencja e-commerce? Sprzedawaj KSeF Mapper swoim klientom i zarabiaj prowizję od każdej licencji i odnowienia.

👉 [omnisync.pl/partnerzy](https://omnisync.pl/partnerzy)

---

## Kontakt

- 🌐 [omnisync.pl](https://omnisync.pl)
- 📧 bok@omnisync.pl
- 📞 +48 730 000 481
- 🕐 Pon–Pt 9:00–17:00

**Producent:** Orbis Software Polska Sp. z o.o.  
ul. Rynek 60/2, 50-116 Wrocław  
NIP: 894-304-66-69 | KRS: 0000466567  
Oficjalny partner InsERT i BaseLinker. 500+ wdrożeń integracyjnych od 2013.
