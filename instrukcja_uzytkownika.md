# Podręcznik Użytkownika Systemu Racket

## Wstęp

System Racket to zaawansowane narzędzie klasy WMS (Warehouse Management System), które łączy tradycyjne zarządzanie magazynem z nowoczesną sztuczną inteligencją. Niniejszy podręcznik został przygotowany tak, aby poprowadzić Cię krok po kroku przez każdą funkcję systemu, niezależnie od Twojego doświadczenia technicznego.

Dokumentacja podzielona jest na cztery główne sekcje:

### Spis Treści

1.  [Menu i Nawigacja (Panel WWW)](#menu-nav)

2.  [Instrukcja dla Administratora](#admin-guide)
    - [Logowanie](#logowanie)

    - [Dashboard](#dashboard-panel-główny)

    - [Zarządzanie Użytkownikami](#zarządzanie-użytkownikami)

    - [Magazyn i Regały](#definicja-magazynu-zarządzanie-regałami)

    - [Produkty](#definicja-produktów)

    - [Raporty](#raporty)

    - [Alerty](#alerty-powiadomienia)

    - [Kopie Zapasowe](#kopie-zapasowe-backups)

    - [Zarządzanie AI](#zarządzanie-ai-sztuczna-inteligencja)

3.  [Instrukcja dla Magazyniera (WWW)](#worker-guide)
    - [Funkcje Wspólne](#funkcje-wspólne)

    - [Profil Użytkownika](#profil-użytkownika)

4.  [Aplikacja Mobilna](#mobile-app)
    - [Logowanie Mobile](#logowanie-1)

    - [Proces Przyjęcia (Inbound)](#proces-przyjęcia-inbound)

    - [Proces Wydania (Outbound)](#proces-wydania-outbound)

    - [Generowanie Raportów](#generowanie-raportów-z-telefonu)

    - [Asystent Głosowy](#asystent-głosowy-voice-assistant)

---

## 1. Menu i Nawigacja (Panel WWW) <a  id="menu-nav"></a>

Po zalogowaniu do systemu w przeglądarce internetowej, po lewej stronie ekranu zobaczysz pasek nawigacyjny (Sidebar). Umożliwia on szybki dostęp do wszystkich modułów.

- **Panel (Dashboard):** Główny ekran z podsumowaniem stanu magazynu.

- **Użytkownicy:** Zarządzanie kontami pracowników (tylko Administrator).

- **Magazyn:** Konfiguracja regałów i wizualizacja rozmieszczenia (tylko Administrator).

- **Produkty:** Baza towarów, zdjęcia i kody kreskowe.

- **Raporty:** Statystyki temperatur, ważności produktów i inwentaryzacja.

- **Alerty:** Centrum powiadomień o awariach i nieprawidłowościach.

- _Ikona Dzwonka:_ Jeśli masz nieprzeczytane alerty, zobaczysz czerwoną plakietkę z ich liczbą.

- **Kopie Zapasowe:** Narzędzie do zabezpieczania danych systemu.

- **Model AI:** Centrum treningowe sztucznej inteligencji (tylko Administrator).

- **Profil:** Twoje ustawienia (hasło, weryfikacja dwuetapowa).

---

## 2. Instrukcja dla Administratora <a  id="admin-guide"></a>

Jako Administrator posiadasz pełną kontrolę nad systemem. Twoim zadaniem jest dbanie o poprawność danych i ciągłość pracy magazynu.

### Logowanie

Administrator jest tworzony domyślnie podczas instalacji systemu.

1. Wejdź na stronę logowania.

2. Wpisz login: `SUPER_ADMIN` oraz hasło `Asdf#1234`.

3. Kliknij **"Zaloguj się"**.

### Dashboard (Panel Główny)

Jest to centrum dowodzenia. Widzisz tutaj skrócone informacje z innych modułów:

- **Kafelki Szybkiego Dostępu:** Kliknięcie w kafelek (np. "Produkty") przenosi bezpośrednio do odpowiedniej sekcji.

### Zarządzanie Użytkownikami

W tej sekcji decydujesz, kto ma dostęp do systemu.

- **Zatwierdzanie:** Nowi użytkownicy, którzy zarejestrowali się sami, trafiają na listę "Oczekujących". Kliknij zielony przycisk "Zatwierdź" , aby dać im dostęp.

- **Odrzucanie:** Kliknij "Odrzuć", aby usunąć wniosek o konto.

- **Usuwanie:** Możesz usunąć dowolnego użytkownika z listy aktywnych, klikając ikonę kosza.

### Definicja Magazynu (Zarządzanie Regałami)

Tutaj odwzorowujesz fizyczny układ magazynu w systemie.

- **Dodawanie Regału:**

    1. Kliknij "Dodaj Regał".

    2. Wypełnij formularz: Oznaczenie (np. R-01), Wymiary, Limity Wagi i Temperatury.

    3. _Walidacja:_ System nie pozwoli stworzyć regału z ujemnymi wymiarami.

- **Import Masowy (CSV):**

- Jeśli masz setki regałów, przygotuj plik Excel/CSV i użyj opcji "Importuj".

- **Edycja i Usuwanie:**

- Możesz zmienić parametry istniejącego regału.

- _Ważne:_ **Nie można usunąć regału, na którym stoją towary.** Musisz najpierw przenieść produkty w inne miejsce.

- **Wizualizacja:** Kliknij na regał, aby zobaczyć graficzny podgląd (mapę cieplną), gdzie dokładnie stoją produkty.

- **Wyszukiwanie:** Użyj paska szukania, aby szybko znaleźć odpowiedni produkt na regale.

### Definicja Produktów

Baza asortymentu. Każdy towar w magazynie musi być tu zdefiniowany.

- **Tworzenie Produktu:** Kliknij "Dodaj" i wypełnij nazwę, kod kreskowy, wymagania temperaturowe.

- **Zdjęcia:**

- Każdy produkt musi mieć zdjęcie, aby działała sztuczna inteligencja.

- Możesz wgrać jedno zdjęcie ręcznie lub użyć **Prześlij Bulk Zdjęć** (Masowe Wgrywanie), wstaw tyle zdjęć ile chcesz, pamiętając o zgodności nazw zdjęć z wcześniejszym dodanym plikiem csv. Nazwa zdjęcia musi być taka sama jak nazwa zdjęcia produktu w pliku.

- **Import CSV:** Pozwala wgrać tysiące produktów z jednej tabeli.

- **Walidacja:** System sprawdzi, czy parametry produktu nie są ujemne oraz czy kody kreskowe są unikalne.

- **Szukanie:** Pasek wyszukiwania pozwala filtrować listę po nazwie lub kodzie.

### Raporty

Generowanie raportów dla magazynu.

- **Generowanie Ręczne:** Wybierz typ (Temperatury, Ważność, Inwentaryzacja) i kliknij "Generuj".

- **Filtrowanie:** Możesz wygenerować raport tylko dla konkretnego regału.

- **Pobieranie:** Po wygenerowaniu, raport pojawi się na liście. Kliknij ikonę chmurki, aby pobrać go jako PDF/CSV.

### Alerty (Powiadomienia)

- **Nowe (Nieodczytane):** Nowe zdarzenia (np. "Zbyt wysoka temperatura"). Dzwonek w menu pokazuje ich liczbę.

- **Aktywne (Odczytane):** Zdarzenia, które już widziałeś, ale problem nie został rozwiązany.

- **Rozwiązane (Archiwum):** Historia naprawionych usterek.

### Kopie Zapasowe (Backups)

Bezpieczeństwo danych to priorytet.

- **Tworzenie:** Kliknij "Utwórz Kopię". System zapisze całą bazę danych w bezpiecznym miejscu.

- **Przywracanie:** W razie awarii, wybierz plik z listy i kliknij "Przywróć".

### Zarządzanie AI (Sztuczna Inteligencja)

- **Trening:** Wgraj zdjęcia produktów, aby nauczyć system ich rozpoznawania. Kliknij "Rozpocznij Trening".

- **Reset:** Jeśli model działa źle, możesz go zresetować do ustawień fabrycznych.

- **Testowanie:** Wgraj dowolne zdjęcie, aby sprawdzić, czy system poprawnie rozpozna produkt.

- **Dane Treningowe:** Wgraj pojedyncze zdjęcie i wprowadź id produktu lepiej rozpoznawał konkretny asortyment.

---

## 3. Instrukcja dla Magazyniera (Panel WWW) <a  id="worker-guide"></a>

Pracownicy magazynu również mają dostęp do panelu WWW, choć z ograniczonymi uprawnieniami.

### Funkcje Wspólne

Następujące moduły działają identycznie jak u Administratora (patrz rozdział wyżej):

- **Dashboard:** Podgląd zadań.

- **Produkty:** Przeglądanie bazy towarów (tylko odczyt).

- **Raporty:** Przeglądanie i pobieranie gotowych raportów.

- **Alerty:** Odczytywanie powiadomień skierowanych do magazynierów.

- **Kopie Zapasowe:** (Zależnie od uprawnień nadanych przez firmę).

### Profil Użytkownika

- **Zmiana Hasła:** Tutaj możesz zaktualizować swoje hasło do logowania.

- **Weryfikacja Dwuetapowa (2FA):**

    1. Kliknij "Włącz 2FA".

    2. Zeskanuj kod QR aplikacją w telefonie (Google Authenticator) i kniknij przycisk "dalej".

    3. Wpisz 6-cyfrowy kod z Google Authenticator i zakończ proces.

    4. Od teraz logowanie będzie wymagało podania jednorazowego kodu dla bezpieczeństwa.

---

## 4. Aplikacja Mobilna (Dla Wszystkich) <a  id="mobile-app"></a>

Aplikacja to Twoje główne narzędzie pracy na hali magazynowej.

### Logowanie

1. Uruchom aplikację.

2. Wpisz Login i Hasło.

3. **2FA:** Jeśli włączyłeś weryfikację dwuetapową, system poprosi o 6-cyfrowy kod z aplikacji Authenticator. Bez niego nie wejdziesz do systemu.

### Proces Przyjęcia (Inbound)

Jak położyć towar na półkę?

1. Kliknij **Zieloną Kartę "Przyjmij produkt"**.

2. **Skanowanie:** Zeskanuj kod kreskowy.

3. **Co jeśli kod jest zniszczony? (AI):**

    - Kliknij "Użyj AI". Zrób zdjęcie produktu.

    - System rozpozna towar.

    - **Co jeśli AI się pomyli? (Pick from List):** Jeśli system nie jest pewny, wyświetli okienko z pytaniem "Czy to ten produkt?". Kliknij "To nie to", aby ręcznie wybrać właściwy produkt z listy rozwijanej.

4.  **Alokacja:** Aplikacja wskaże, gdzie masz iść (np. "Regał R-01, kolumna 5, rząd 3").

5.  Połóż towar i kliknij **"Potwierdź lokację"**.

### Proces Wydania (Outbound)

Jak pobrać towar do wysyłki?

1. Kliknij **Niebieską Kartę "Zdejmij produkt"**.

2. **Wybór Produktu:** Zeskanuj kod, użyj AI (tak samo jak przy przyjęciu) lub wybierz ręcznie z listy.

3. **Lokalizacja (FIFO):**

    - System wskaże _konkretną_ sztukę, którą musisz wziąć (tę, która leży najdłużej).

    - Nie bierz towaru z innej półki – system to wykryje (niezgodność wagi).

4. Zdejmij towar i kliknij **"Potwierdź pobranie"**.

### Generowanie Raportów (Z Telefonu)

Możesz zlecić raport stojąc bezpośrednio przy regale.

1. Wejdź w **"Raporty"**.

2. Kliknij **"Generuj"** w prawym górnym rogu.

3. Wybierz typ: Ważność, Temperatury lub Audyt.

4. (Opcjonalnie) Zeskanuj kod regału, aby raport dotyczył tylko tego miejsca.

5. Kliknij "Wyślij". Raport zostanie wygenerowany w tle.

### Asystent Głosowy (Voice Assistant)

Najbardziej zaawansowana funkcja systemu. Pozwala sterować aplikacją bez użycia rąk.

1. Kliknij ikonę mikrofonu na dole ekranu głównego.

2. Powiedz komendę. Przykłady:

    - **Przyjęcie:** _"Przyjmij mleko"_ -> System automatycznie wypełni formularz przyjęcia.

    - **Wydanie:** _"Wydaj paracetamol"_ -> System znajdzie najstarszą partię leku i pokaże Ci, gdzie iść.

    - **Raport:** _"Wygeneruj raport temperatur [dla regału numer 5]"_ -> System zleci raport.

Asystent rozumie język naturalny. Możesz mówić pełnymi zdaniami, choć najlepiej działają krótkie komendy. System "słyszy", przetwarza Twoją mowę na tekst, a następnie inteligenta analiza (LLM) decyduje, jaką akcję wykonać w aplikacji.
