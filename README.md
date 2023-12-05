# Dokumentacja Aplikacji Kalendarza Zmianowego

 1. Wstęp
1.1 Cel Aplikacji
Aplikacja Kalendarza Zmianowego została stworzona w celu umożliwienia strażakom lepszego planowania czasu poprzez dostęp do interaktywnego kalendarza, umożliwiającego zarządzanie zmianami, urlopami i chorobowymi.

1.2 Zakres Aplikacji
Aplikacja pozwala na:
- Tworzenie, przeglądanie i aktualizację grafiku zmianowego.
- Ustawianie danego dnia na urlop, pracę i chorobowe.
- Zmianę liczby godzin w danym dniu pracującym.
- Aktualizację wprowadzonych zmian.
- Usuwanie wprowadzonych zmian.

2. Instalacja i Uruchamianie
2.1 Wymagania Systemowe
Język programowania back-end: Python (Flask)
Język programowania front-end: JavaScript (React)
Baza danych: NoSQL (MongoDb).




Przeglądarka internetowa z obsługą JavaScript.
Aplikacja Docker Desktop
Aplikacja do obsługi bazy danych w mongodb np. MongoDbCompass
Zalecany system operacyjny: Windows 10



2.2 Instalacja
1. Pobrać folder zip z repozytorium
2. Utworzyć obrazy za pomocą komendy docker build (np. w wierszu poleceń) w katalogach poszczególnych (reactapp-frontend i flaskapp-backend)
3. Otworzyć folder główny projektu i komendy docker-compose up (np. w wierszu poleceń)

Po wykonaniu powyższych kroków można otworzyć przeglądarkę gdzie można uzyskać dostęp do aplikacji za pomocą linków:

http://localhost:3000/ - interfejs aplikacji (frontend)

http://localhost:5000/apidocs/ - dokumentacja swagger (backend)

aby uzyskać dostęp do bazy danych można skorzystać z narzędzia MongoDbCompass gdzie należy wkleić w okno URI:

mongodb+srv://ProjectAdmin:Parano55@calendarprojectcluster.usy8q0s.mongodb.net/?retryWrites=true&w=majority

Następnie klikamy connect, w ten sposób dostaniemy się do zawartości bazy danych







3. Użytkowanie Aplikacji
3.1 Tworzenie Grafiku Zmianowego
Zaloguj się do systemu.
Zaznacz dany dzień.
Wprowadź zmiany na panelu bocznym.
Zatwierdź zmiany.
3.2 Zarządzanie Godzinami Pracy
Kliknij na konkretny dzień z przypisem praca.
Dodaj lub odejmij godziny pracy dla danego dnia.
3.3 Aktualizacja Danych Dni
Wybierz dany dzień.
Dokonaj zmian.
Zatwierdź.
3.4 Usuwanie Danych
Wybierz dany dzień
Kliknij usuń.
Potwierdź operację.

4. Bezpieczeństwo
4.1 Zasady Bezpieczeństwa
Dostęp do aplikacji jest chroniony za pomocą tokenów.
Każdy zalogowany użytkownik posiada własny unikatowy token pozwalający na korzystanie z aplikacji.

