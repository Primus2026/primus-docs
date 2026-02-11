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

![Logowanie Admina](assets/user-manual/web-logowanie-admin.png)

### Dashboard (Panel Główny)

Jest to centrum dowodzenia. Widzisz tutaj skrócone informacje z innych modułów:

![Widok Dashboardu](assets/user-manual/web-widow-dashboardu.png)

- **Kafelki Szybkiego Dostępu:** Kliknięcie w kafelek (np. "Produkty") przenosi bezpośrednio do odpowiedniej sekcji.

### Zarządzanie Użytkownikami

W tej sekcji decydujesz, kto ma dostęp do systemu.

![Zarządzanie Użytkownikami](assets/user-manual/web-zarzadzanie-uzytkownikami.png)

- **Zatwierdzanie:** Nowi użytkownicy, którzy zarejestrowali się sami, trafiają na listę "Oczekujących". Kliknij zielony przycisk "Zatwierdź" , aby dać im dostęp.

- **Odrzucanie:** Kliknij "Odrzuć", aby usunąć wniosek o konto.

- **Usuwanie:** Możesz usunąć dowolnego użytkownika z listy aktywnych, klikając ikonę kosza.

### Definicja Magazynu (Zarządzanie Regałami)

Tutaj odwzorowujesz fizyczny układ magazynu w systemie.

![Definicja Magazynu](assets/user-manual/web-definicja-magazynu.png)

- **Dodawanie Regału:**
  1. Kliknij "Nowy Regał".

  2. Wypełnij formularz: Oznaczenie (np. R-01), Wymiary, Limity Wagi i Temperatury.

  ![Dodawanie Regału](assets/user-manual/web-dodawanie-regalu.png) 3. _Walidacja:_ System nie pozwoli stworzyć regału z ujemnymi wymiarami.

- **Import Masowy (CSV):**
- Jeśli masz setki regałów, przygotuj plik Excel/CSV i użyj opcji "Importuj".

![Import CSV 1](assets/user-manual/web-import-csv-1.png)
![Import CSV 2](assets/user-manual/web-import-csv-2.png)

![Import CSV 3](assets/user-manual/web-import-csv3.png)

- **Edycja i Usuwanie:**

- Możesz zmienić parametry istniejącego regału.

![Edycja Regału](assets/user-manual/web-edycja-regalu.png)
![Edycja Regału 1](assets/user-manual/web-edycja-regalu1.png)

- lub usunąć regał

![Usuwanie Regału](assets/user-manual/web-usuwanie-regalu1.png)

- _Ważne:_ **Nie można usunąć regału, na którym stoją towary.** Musisz najpierw przenieść produkty w inne miejsce.

![Błąd Usuwania](assets/user-manual/web-usuwanie-regalu-3-blad.png)
![Sukces Usuwania](assets/user-manual/web-usuwanie-regalu-5-sukcecs.png)

- **Wizualizacja:** Kliknij na regał, aby zobaczyć graficzny podgląd (mapę cieplną), gdzie dokładnie stoją produkty.

![Wizualizacja](assets/user-manual/web-wizualizacja-1.png)
![Wizualizacja 2](assets/user-manual/web-wizualizacja-2.png)

- **Wyszukiwanie:** Użyj paska szukania, aby szybko znaleźć odpowiedni regał na liście.

![Wyszukiwanie Regału](assets/user-manual/web-wyszukiwanie-regalow-1.png)

### Definicja Produktów

Baza asortymentu. Każdy towar w magazynie musi być tu zdefiniowany.

![Definicja Produktów](assets/user-manual/web-definicje-produktow.png)

- **Tworzenie Produktu:** Kliknij "Dodaj" i wypełnij nazwę, kod kreskowy, wymagania temperaturowe.

![Dodawanie Produktu 1](assets/user-manual/web-dodawanie-produktow-1.png)

- **Zdjęcia:**

- Każdy produkt musi mieć zdjęcie, aby działała sztuczna inteligencja.

- Możesz wgrać jedno zdjęcie ręcznie lub użyć **Prześlij Bulk Zdjęć** (Masowe Wgrywanie), wstaw tyle zdjęć ile chcesz, pamiętając o zgodności nazw zdjęć z wcześniejszym dodanym plikiem csv. Nazwa zdjęcia musi być taka sama jak nazwa zdjęcia produktu w pliku.

![Dodawanie Produktu 3](assets/user-manual/web-dodawanie-produktu3.png)

- **Import CSV:** Pozwala wgrać tysiące produktów z jednej tabeli.

![Import Produktów 1](assets/user-manual/web-import-produktow-1.png)
![Import Produktów 2](assets/user-manual/web-import-produktow-2.png)
![Import Produktów 3](assets/user-manual/web-import-produktow-3.png)

- **Import Zdjęć:**

![Import Zdjęć 2](assets/user-manual/web-import-zdjec-2.png)

- **Walidacja:** System sprawdzi, czy parametry produktu nie są ujemne oraz czy kody kreskowe są unikalne.

- **Szukanie:** Pasek wyszukiwania pozwala filtrować listę po nazwie lub kodzie.
  ![Import Zdjęć 3](assets/user-manual/web-import-zdjec-3.png)
  ![Import Zdjęć 4](assets/user-manual/web-import-zdjec-4.png)
- **Kompatebilność nazw** Nazwy zdjęć muszą być takie same jak w pliku .csv.

### Raporty

Generowanie raportów dla magazynu.

![Raporty](assets/user-manual/web-raporty.png)

- **Generowanie Ręczne:** Wybierz typ (Temperatury, Ważność, Inwentaryzacja) i kliknij "Generuj".

![Generowanie Raportu 1](assets/user-manual/web-generowanie-raportu-1.png)
![Generowanie Raportu 2](assets/user-manual/web-generowanie-raportu-2.png)

- **Filtrowanie:** Możesz wygenerować raport tylko dla konkretnego regału.

- **Pobieranie:** Po wygenerowaniu, raport pojawi się na liście. Kliknij ikonę chmurki, aby pobrać go jako PDF/CSV.

![Generowanie Raportu 3](assets/user-manual/web-generowanie-raportu-3.png)

### Alerty (Powiadomienia)

![Alerty](assets/user-manual/web-alerty-1.png)

- **Nowe (Nieodczytane):** Nowe zdarzenia (np. "Zbyt wysoka temperatura"). Dzwonek w menu pokazuje ich liczbę.

![Odczytanie Alertu](assets/user-manual/web-odczytanie-alertu.png)
![Odczytane Alerty](assets/user-manual/web-odczytane-alerty.png)

- **Aktywne (Odczytane):** Zdarzenia, które już widziałeś, ale problem nie został rozwiązany.

- **Rozwiązane (Archiwum):** Historia naprawionych usterek.

![Rozwiązywanie Alertu](assets/user-manual/web-rowziawanie-alertu.png)
![Rozwiązane Alerty](assets/user-manual/web-rozwiazane-alerty.png)

### Kopie Zapasowe (Backups)

Bezpieczeństwo danych to priorytet.

![Kopie Zapasowe](assets/user-manual/web-backupy.png)

- **Tworzenie:** Kliknij "Utwórz Kopię". System zapisze całą bazę danych w bezpiecznym miejscu.

![Tworzenie Backupu 1](assets/user-manual/web-tworzenie-backupu-1.png)
![Tworzenie Backupu 2](assets/user-manual/web-tworzenie-backupu-2.png)

- **Przywracanie:** W razie awarii, wybierz plik z listy i kliknij "Przywróć".

![Przywracanie Backupu 1](assets/user-manual/web-przywracanie-backupu-1.png)
![Przywracanie Backupu 2](assets/user-manual/web-przywracanie-backupu-2.png)

### Zarządzanie AI (Sztuczna Inteligencja)

![Zarządzanie AI](assets/user-manual/web-zarzadzanie-ai.png)

- **Trening:** Wgraj zdjęcia produktów, aby nauczyć system ich rozpoznawania. Kliknij "Rozpocznij Trening".

![Trenowanie 1](assets/user-manual/trenowanie-1.png)
![Trenowanie Zdjęcie](assets/user-manual/trenowanie-zdjecie.png)
![Trenowanie 3](assets/user-manual/trenowanie-3.png)

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

![Profil](assets/user-manual/web-profil.png)

- **Zmiana Hasła:** Tutaj możesz zaktualizować swoje hasło do logowania.

- **Weryfikacja Dwuetapowa (2FA):**
  1. Kliknij "Włącz 2FA".

  ![2FA 1](assets/user-manual/web-2fa-1.png)

2. Zeskanuj kod QR aplikacją w telefonie (Google Authenticator) i kniknij przycisk "dalej".

![2FA 2](assets/user-manual/web-2fa-2.png)

3. Wpisz 6-cyfrowy kod z Google Authenticator i zakończ proces.

![2FA 3](assets/user-manual/web-2fa-3.png)

4.  Od teraz logowanie będzie wymagało podania jednorazowego kodu dla bezpieczeństwa.

![2FA 4](assets/user-manual/web-2fa-4.png)

---

## 4. Aplikacja Mobilna (Dla Wszystkich) <a  id="mobile-app"></a>

Aplikacja to Twoje główne narzędzie pracy na hali magazynowej.

### Logowanie

1. Uruchom aplikację.

![Logowanie Mobile 1](assets/user-manual/mobile-logowanie1.png)

2. Wpisz Login i Hasło.

![Logowanie Mobile 2](assets/user-manual/mobile-logowanie-21.png)

3. **2FA:** Jeśli włączyłeś weryfikację dwuetapową, system poprosi o 6-cyfrowy kod z aplikacji Authenticator. Bez niego nie wejdziesz do systemu.

![Logowanie Mobile 3](assets/user-manual/mobile-logowanie-3.png)

### Dashboard - Panel Główny

Po poprawnym zalogowaniu zobaczysz ekran główny aplikacji (Dashboard), który umożliwia szybki dostęp do najważniejszych funkcji.

![Panel Główny](assets/user-manual/mobile-dashboard.jpg)

### Proces Przyjęcia (Inbound)

Jak położyć towar na półkę?

1. Kliknij **Zieloną Kartę "Przyjmij produkt"**.

2. **Skanowanie:** Zeskanuj kod kreskowy produktu lub wpisz go ręcznie, jeśli kod jest nieczytelny.

   ![Ręczne wpisywanie kodu](assets/user-manual/mobile-przyjmowanie-manualne-wpisanie-kodu.jpg)

3. **Co jeśli kod jest zniszczony? (AI):**
   - Kliknij "Użyj AI". Zrób zdjęcie produktu.

   ![Robienie zdjęcia](assets/user-manual/mobile-przyjmowanie-robienie-zdjecia.jpg)
   - System przeanalizuje zdjęcie i spróbuje rozpoznać towar.

   ![Analiza AI](assets/user-manual/mobile-przyjmowanie-ai-zdjecie.jpg)
   - **Co jeśli AI się pomyli? (Pick from List):** Jeśli system nie jest pewny, wyświetli okienko z pytaniem "Czy to ten produkt?". Kliknij "To nie to", aby ręcznie wybrać właściwy produkt z listy rozwijanej.

   ![Wybór produktu z listy](assets/user-manual/mobile-przyjmowanie-ai-nie-rozpoznalo-wybierz-produkt.jpg)

4. **Alokacja:** Aplikacja wskaże sugerowane miejsce w magazynie (np. "Regał w sali głównej, Półka 1").

   ![Znaleziono miejsce](assets/user-manual/mobile-przyjmowanie-znaleziono-miejsce-w-magazynie.jpg)

5. Połóż towar we wskazanym miejscu i kliknij **"Zatwierdź"**.

   ![Potwierdzenie przyjęcia](assets/user-manual/mobile-przyjmowanie-sukces-przyjmowania-produktu.jpg)

### Proces Wydania (Outbound)

Proces wydania towaru z magazynu przebiega analogicznie do procesu przyjęcia (Inbound), z tą różnicą, że zamiast odkładać towar na półkę, pobierasz go zgodnie ze wskazówkami aplikacji. Aplikacja poprowadzi Cię do odpowiedniej lokalizacji, skąd należy pobrać towar (zgodnie z zasadą FIFO - First In, First Out).

### Generowanie Raportów (Z Telefonu)

Możesz zlecić raport stojąc bezpośrednio przy regale.

1. Wejdź w **"Raporty"**.

2. Kliknij **"Generuj"** w prawym górnym rogu.

3. Wybierz typ: Ważność, Temperatury lub Audyt.

4. (Opcjonalnie) Zeskanuj kod regału, aby raport dotyczył tylko tego miejsca.

5. Kliknij "Wyślij". Raport zostanie wygenerowany w tle.

### Asystent Głosowy (Voice Assistant)

Najbardziej zaawansowana funkcja systemu. Pozwala sterować aplikacją bez użycia rąk.

![Asystent Głosowy](assets/user-manual/mobile-asystent-glosowy.jpg)

1. Kliknij ikonę mikrofonu na dole ekranu głównego.

2. Powiedz komendę. Przykłady:
   - **Przyjęcie:** _"Przyjmij mleko"_ -> System automatycznie wypełni formularz przyjęcia.

   - **Wydanie:** _"Wydaj paracetamol"_ -> System znajdzie najstarszą partię leku i pokaże Ci, gdzie iść.

   - **Raport:** _"Wygeneruj raport temperatur [dla regału numer 5]"_ -> System zleci raport.

Asystent rozumie język naturalny. Możesz mówić pełnymi zdaniami, choć najlepiej działają krótkie komendy. System "słyszy", przetwarza Twoją mowę na tekst, a następnie inteligenta analiza (LLM) decyduje, jaką akcję wykonać w aplikacji.
