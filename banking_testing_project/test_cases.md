# Test Cases – Banking Application

## LOGOWANIE

### TC01 – Poprawne logowanie
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Wpisz poprawny login i hasło
3. Kliknij "zaloguj"
Oczekiwany rezultat:
- użytkownik zostaje zalogowany

### TC02 – Błędne hasło
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Wpisz poprawny login
3. Wpisz błędne hasło
4. Kliknij "zaloguj"
Oczekiwany rezultat:
- komunikat: "nieprawidłowe dane"

### TC03 – Puste pola
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Nie wpisuj danych
3. Kliknij "zaloguj"
Oczekiwany rezultat:
- walidacja pól
- brak logowania

### TC04 – SQL Injection
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Wpisz w login: `' OR 1=1 --`
3. Kliknij "zaloguj"
Oczekiwany rezultat:
- brak logowania
- system odporny na atak

### TC05 – Zbyt długie dane
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Wpisz w login 500 znaków
3. Kliknij "zaloguj"
Oczekiwany rezultat:
- błąd walidacji
- brak crasha aplikacji

---

## PRZELEWY

### TC06 – Poprawny przelew
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Zaloguj się poprawnym loginem i hasłem
3. Przejdź do sekcji "przelewy"
4. Wpisz poprawny numer konta i kwotę
5. Kliknij "wyślij"
Oczekiwany rezultat:
- przelew wykonany
- saldo zmniejsza się

### TC07 – Kwota = 0
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Zaloguj się poprawnym loginem i hasłem
3. Przejdź do sekcji "przelewy"
4. Wpisz kwotę 0
5. Kliknij "wyślij"
Oczekiwany rezultat:
- komunikat: "Nie można wykonać przelewu o kwocie 0"
- przelew nie wykonany

### TC08 – Kwota ujemna
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Zaloguj się poprawnym loginem i hasłem
3. Przejdź do sekcji "przelewy"
4. Wpisz kwotę -100
5. Kliknij "wyślij"
Oczekiwany rezultat:
- walidacja błedu
- przelew nie wykonany
- notatka: system poprawnie odrzuca, ale komunikat mało czytelny

### TC09 – Przelew większy niż saldo
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Zaloguj się poprawnym loginem i hasłem
3. Przejdź do sekcji "Przelewy"
4. Wpisz kwotę większą niż saldo
5. Kliknij "Wyślij"
Oczekiwany rezultat:
- komunikat "brak środków"

### TC10 – Niepoprawny numer konta
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Zaloguj się poprawnym loginem i hasłem
3. Przejdź do sekcji "Przelewy"
4. Wpisz niepoprawny numer konta
5. Kliknij "Wyślij"
Oczekiwany rezultat:
- walidacja numeru konta
- brak wykonania przelewu
- komunikat: "niepoprawny numer konta"


### TC11 – Bardzo duża kwota
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Zaloguj się poprawnym loginem i hasłem
3. Przejdź do sekcji "Przelewy"
4. Wpisz bardzo dużą kwotę (np. 999999999)
5. Kliknij "Wyślij"
Oczekiwany rezultat:
- system obsługuje poprawnie lub odrzuca

### TC12 – Kliknięcie „Wyślij” wiele razy
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Zaloguj się poprawnym loginem i hasłem
3. Przejdź do sekcji "Przelewy"
4. Kliknij „Wyślij” kilka razy szybko
Oczekiwany rezultat:
- tylko jeden przelew zostaje wykonany
- uwaga: UI blokuje przycisk chwilowo

---

## SALDO I HISTORIA

### TC13 – Aktualizacja salda po przelewie
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Zaloguj się poprawnym loginem i hasłem
3. Wykonaj przelew
Oczekiwany rezultat:
- saldo konta jest poprawnie zaktualizowane

### TC14 – Historia transakcji
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Zaloguj się poprawnym loginem i hasłem
3. Wykonaj przelew
4. Przejdź do historii transakcji
Oczekiwany rezultat:
- przelew widoczny w historii

### TC15 – Odświeżenie strony
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Zaloguj się poprawnym loginem i hasłem
3. Wykonaj przelew
4. Odśwież stronę
Oczekiwany rezultat:
- saldo i historia pozostają poprawne

---

## WYLOGOWANIE

### TC16 – Wylogowanie
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Zaloguj się poprawnym loginem i hasłem
3. Kliknij przycisk wyloguj
Oczekiwany rezultat:
- powrót do logowania
- brak dostępu do konta

### TC17 – Back po logout
Kroki:
1. Wejdź na stronę aplikacji bankowej
2. Zaloguj się poprawnym loginem i hasłem
3. Wyloguj się
4. Kliknij "wstecz" w przeglądarce
Oczekiwany rezultat:
- brak dostępu do konta