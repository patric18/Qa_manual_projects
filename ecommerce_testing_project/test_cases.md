# Test Cases – E-commerce Store

## LOGOWANIE

### TC01 – Poprawne logowanie
Kroki:
1. Wejdź na stronę sklepu
2. Wpisz poprawny login i hasło
3. Kliknij "zaloguj"
Oczekiwany rezultat:
- użytkownik zostaje zalogowany
- widzi stronę główną z produktami

### TC02 – Błędne logowanie
Kroki:
1. Wejdź na stronę sklepu
2. Wpisz poprawny login
3. Wpisz błędne hasło
4. Kliknij "zaloguj"
Oczekiwany rezultat:
- komunikat "nieprawidłowe dane"
- brak logowania

---

## KOSZYK

### TC03 – Dodanie produktu do koszyka
Kroki:
1. Wejdź na stronę sklepu
2. Wpisz poprawny login i hasło
3. Zaloguj się
4. Wybierz produkt
5. Kliknij "dodaj do koszyka"
Oczekiwany rezultat:
- produkt pojawia się w koszyku
- cena wyświetla się poprawnie

### TC04 – Dodanie kilku produktów
Kroki:
1. Wejdź na stronę sklepu
2. Wpisz poprawny login i hasło
3. Zaloguj się
4. Dodaj 3 różne produkty do koszyka
Oczekiwany rezultat:
- wszystkie produkty w koszyku
- suma cen poprawna

### TC05 – Usunięcie produktu z koszyka
Kroki:
1. Wejdź na stronę sklepu
2. Wpisz poprawny login i hasło
3. Zaloguj się
4. Dodaj produkt
5. Usuń produkt z koszyka
Oczekiwany rezultat:
- koszyk pusty
- suma cen zaktualizowana

### TC06 – Edycja ilości produktu
Kroki:
1. Wejdź na stronę sklepu
2. Wpisz poprawny login i hasło
3. Zaloguj się
4. Dodaj produkt
5. Zmień ilość na 3
Oczekiwany rezultat:
- ilość zaktualizowana
- suma cen poprawna

### TC07 – Dodanie bardzo dużej liczby produktów
Kroki:
1. Wejdź na stronę sklepu
2. Wpisz poprawny login i hasło
3. Zaloguj się
4. Dodaj 1000 produktów tego samego typu
Oczekiwany rezultat:
- koszyk obsługuje dużą ilość produktów
- suma cen prawidłowa
- uwaga: strona lekko się zacina

---

## ZAMÓWIENIE

### TC08 – Prawidłowe zamówienie
Kroki:
1. Wejdź na stronę sklepu
2. Wpisz poprawny login i hasło
3. Zaloguj się
4. Dodaj produkty do koszyka
5. Kliknij "przejdź do kasy"
6. Wypełnij dane i kliknij "zapłać"
Oczekiwany rezultat:
- zamówienie zostało złożone
- numer zamówienia widoczny

### TC09 – Płatność błędna
Kroki:
1. Wejdź na stronę sklepu
2. Wpisz poprawny login i hasło
3. Zaloguj się
4. Dodaj produkty
5. Przejdź do kasy
6. Wpisz niepoprawne dane karty
7. Kliknij "zapłać"
Oczekiwany rezultat:
- komunikat o błędzie
- zamówienie nie zostało złożone

### TC10 – Kliknięcie "zapłać" wiele razy
Kroki:
1. Wejdź na stronę sklepu
2. Wpisz poprawny login i hasło
3. Zaloguj się
4. Dodaj produkty
5. Przejdź do kasy
6. Kliknij "zapłać" 5 razy szybko
Oczekiwany rezultat:
- tylko jedno zamówienie zostaje złożone
- notatka: "przycisk się blokuje po pierwszym kliknięciu"

---

## WYLOGOWANIE

### TC11 – Logout
Kroki:
1. Wejdź na stronę sklepu
2. Wpisz poprawny login i hasło
3. Zaloguj się
4. Kliknij "wyloguj"
Oczekiwany rezultat:
- powrót do strony logowania
- brak dostępu do konta po kliknięciu "wstecz"