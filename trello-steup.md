## Zadanie 1: Uzyskanie klucza API dla trello
0. Stwórz sobie tymczasowego maila na https://temp-mail.org/pl/ (jeżeli chcesz możesz też korzystać z własnego adresu email)
1. Trello rejestracja:
https://trello.com/pl

2. Aktywacja maila, nadanie hasła


3. Zaloguj się na swoje konto i utwórz nową tablicę (trello zaproponuje 30-dniowy plan premium ale wybierz opcję darmową)

4. Po stworzeniu nowej tablicy wejdź na:
https://trello.com/power-ups/admin
+ akceptacja regulaminu

4. Stwórz nowy power-up
https://trello.com/power-ups/admin/new

uzupełnij wymagane pola

5. Po stworzeniu power-up zostaniesz przeniesiony do okna z tworzeniem nowego API key - wygeneruj nowy klucz



## Zadanie 2: Stworzenie Kolekcji Trello

Utwórz kolekcję w Postmanie na podstawie poniższych specyfikacji:

1. Otwórz aplikację Postman.
2. W lewym panelu wybierz `Collections`.
3. Kliknij `New Collection`.
4. Wpisz nazwę kolekcji: `Trello`.
5. Kliknij `Create` aby stworzyć nową kolekcję.

Instrukcje

- Kolekcja powinna zawierać żądania takie jak te, które są zdefiniowane w Twoim pliku JSON. Przykłady to `GET`, `POST`, `PUT`, `DELETE` żądania do różnych endpointów API Trello.
- Możesz ręcznie dodawać żądania klikając prawym przyciskiem myszy na kolekcję i wybierając `Add Request`.
- Pamiętaj, aby każde żądanie miało odpowiednio ustawione metody HTTP oraz endpointy.



## Zadanie 3: Stworzenie Środowiska Trello

Utwórz środowisko w Postmanie zgodnie z poniższymi specyfikacjami:

1. W Postmanie, wybierz ikonę `Environments` w lewym dolnym rogu.
2. Kliknij `Add` aby stworzyć nowe środowisko.
3. Wpisz nazwę środowiska: `Trello Environment`.
4. Dodaj następujące zmienne środowiskowe:
   - `baseUrl` z wartością `https://api.trello.com/1`
   - `key` z wartością `2f1d6341233fb95a746fbdaba8a563e0`
   - `token` z wartością `ATTAbef53bab37f477ac436a6fccdcbb6894d7b78acf832a35f4eadab9569b511985A1433556`
5. Po dodaniu zmiennych, kliknij `Add` aby zapisać środowisko.

Instrukcje

- Zmienne środowiskowe pozwalają przechowywać wartości, które mogą być często używane w różnych żądaniach, takie jak URL bazy czy klucze uwierzytelniające.
- Pamiętaj, żeby każda zmienna miała ustawione odpowiednie wartości, które odpowiadają tym z Twojego JSON-a środowiska.
- Kiedy skończysz, nie zapomnij zapisać środowiska klikając `Add` lub `Save` jeśli edytujesz istniejące środowisko.


