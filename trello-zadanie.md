1. Zadanie 1 (Utworzenie nowej tablicy):
   - [Create Board](https://developer.atlassian.com/cloud/trello/rest/api-group-boards/#api-boards-post)

2. Zadanie 2 (Dodanie list do tablicy):
   - [Create List](https://developer.atlassian.com/cloud/trello/rest/api-group-lists/#api-lists-post)

3. Zadanie 3 (Utworzenie karty):
   - [Create Card](https://developer.atlassian.com/cloud/trello/rest/api-group-cards/#api-cards-post)

4. Zadanie 4 (Przeniesienie karty do innej listy):
   - [Update Card: Move to List](https://developer.atlassian.com/cloud/trello/rest/api-group-cards/#api-cards-id-put)

5. Zadanie 5 (Dodanie komentarza do karty):
   - [Add Comment to Card](https://developer.atlassian.com/cloud/trello/rest/api-group-cards/#api-cards-id-actions-comments-post)

6. Zadanie 6 (Utworzenie etykiety):
   - [Create Label](https://developer.atlassian.com/cloud/trello/rest/api-group-labels/#api-labels-post)

7. Zadanie 7 (Przypisanie etykiety do karty):
   - [Add Label to Card](https://developer.atlassian.com/cloud/trello/rest/api-group-cards/#api-cards-id-idlabels-post)

8. Zadanie 8 (Zmiana nazwy tablicy):
   - [Update Board](https://developer.atlassian.com/cloud/trello/rest/api-group-boards/#api-boards-id-put)

9. Zadanie 9 (Usunięcie karty):
   - [Delete Card](https://developer.atlassian.com/cloud/trello/rest/api-group-cards/#api-cards-id-delete)




## Zadanie 1: Stworzenie Kolekcji Trello

Utwórz kolekcję w Postmanie na podstawie poniższych specyfikacji:

1. Otwórz aplikację Postman.
2. W lewym panelu wybierz `Collections`.
3. Kliknij `New Collection`.
4. Wpisz nazwę kolekcji: `Trello`.
5. Kliknij `Create` aby stworzyć nową kolekcję.

<details>
<summary>Instrukcje</summary>

- Kolekcja powinna zawierać żądania takie jak te, które są zdefiniowane w Twoim pliku JSON. Przykłady to `GET`, `POST`, `PUT`, `DELETE` żądania do różnych endpointów API Trello.
- Możesz ręcznie dodawać żądania klikając prawym przyciskiem myszy na kolekcję i wybierając `Add Request`.
- Pamiętaj, aby każde żądanie miało odpowiednio ustawione metody HTTP oraz endpointy.

</details>

## Zadanie 2: Stworzenie Środowiska Trello

Utwórz środowisko w Postmanie zgodnie z poniższymi specyfikacjami:

1. W Postmanie, wybierz ikonę `Environments` w lewym dolnym rogu.
2. Kliknij `Add` aby stworzyć nowe środowisko.
3. Wpisz nazwę środowiska: `Trello Environment`.
4. Dodaj następujące zmienne środowiskowe:
   - `baseUrl` z wartością `https://api.trello.com/1`
   - `key` z wartością `2f1d6341233fb95a746fbdaba8a563e0`
   - `token` z wartością `ATTAbef53bab37f477ac436a6fccdcbb6894d7b78acf832a35f4eadab9569b511985A1433556`
5. Po dodaniu zmiennych, kliknij `Add` aby zapisać środowisko.

<details>
<summary>Instrukcje</summary>

- Zmienne środowiskowe pozwalają przechowywać wartości, które mogą być często używane w różnych żądaniach, takie jak URL bazy czy klucze uwierzytelniające.
- Pamiętaj, żeby każda zmienna miała ustawione odpowiednie wartości, które odpowiadają tym z Twojego JSON-a środowiska.
- Kiedy skończysz, nie zapomnij zapisać środowiska klikając `Add` lub `Save` jeśli edytujesz istniejące środowisko.

</details>









# Instrukcje Testowania API Trello

## Ćwiczenie 1: Inicjalizacja Pustej Tablicy Trello

Zadanie:
Utwórz nową, pustą tablicę w Trello.

<details>
  <summary>Instrukcje:</summary>

  1. Utwórz zapytanie typu `POST` do endpointu `/boards/`.
  2. Ustaw parametry zapytania na:
     - `name` - użyj zmiennej `{{$randomWord}}`, aby wygenerować losową nazwę tablicy.
     - `defaultLists` - ustaw na `false`, aby stworzyć tablicę bez domyślnych list.
  3. W sekcji `Tests` skryptu dodaj test sprawdzający, czy kod odpowiedzi to `200`.
  4. Zapisz `id` nowo utworzonej tablicy w zmiennych kolekcji jako `boardId`.

</details>

## Ćwiczenie 2: Utworzenie Listy 'DONE' na Tablicy

Zadanie:
Na utworzonej tablicy dodaj listę o nazwie "DONE".

<details>
  <summary>Instrukcje:</summary>

  1. Stwórz zapytanie typu `POST` do `/lists`.
  2. Dodaj do zapytania parametry:
     - `name` - ustaw na `DONE`.
     - `idBoard` - użyj zmiennej `{{boardId}}`, aby wskazać, gdzie lista ma być utworzona.
  3. W sekcji `Tests` dodaj test sprawdzający status odpowiedzi `200`.
  4. Zapisz `id` nowo utworzonej listy jako `doneListId` w zmiennych kolekcji.

</details>

## Ćwiczenie 3: Utworzenie Karty

Zadanie:
Stwórz kartę na liście "DONE".

<details>
  <summary>Instrukcje:</summary>

  1. Wykonaj zapytanie typu `POST` do `/cards`.
  2. Dodaj do zapytania parametry:
     - `name` - użyj zmiennej `{{$randomWord}}`, aby nadać karcie losową nazwę.
     - `idList` - użyj zmiennej `{{doneListId}}`.
  3. Dodaj test w sekcji `Tests`, aby sprawdzić, czy status odpowiedzi to `200`.
  4. Zapisz `id` utworzonej karty w zmiennych kolekcji jako `cardId`.

</details>

## Ćwiczenie 4: Przeniesienie Karty

Zadanie:
Przenieś kartę do innej listy na tej samej tablicy.

<details>
  <summary>Instrukcje:</summary>

  1. Użyj zapytania `PUT` do `/cards/{{cardId}}/idList`.
  2. Jako parametr zapytania podaj `value`, które powinno być równoważne `id` docelowej listy.
  3. Upewnij się, że status odpowiedzi to `200`.

</details>

## Ćwiczenie 5: Archiwizacja Karty

Zadanie:
Zarchiwizuj określoną kartę.

<details>
  <summary>Instrukcje:</summary>

  1. Utwórz zapytanie typu `PUT` do `/cards/{{cardId}}/closed`.
  2. W parametrach zapytania ustaw `value` na `true`, aby zarchiwizować kartę.
  3. Sprawdź w `Tests`, czy status odpowiedzi to `200`.

</details>

## Ćwiczenie 6: Dodanie Komentarza do Karty

Zadanie:
Dodaj komentarz do karty.

<details>
  <summary>Instrukcje:</summary>

  1. Stwórz zapytanie `POST` do `/cards/{{cardId}}/actions/comments`.
  2. W treści zapytania (`body`) umieść:
     - `text` - treść komentarza.
  3. Upewnij się, że w `Tests` sprawdzasz, czy odpowiedź ma status `200`.

</details>

## Ćwiczenie 7: Utworzenie Etykiety

Zadanie:
Utwórz etykietę i dodaj ją do karty.

<details>
  <summary>Instrukcje:</summary>

  1. Wykonaj zapytanie `POST` do `/labels`.
  2. W parametrach zapytania określ:
     - `name` - nazwa etykiety.
     - `color` - kolor etykiety.
     - `idBoard` - identyfikator tablicy.
  3. Dodaj test w `Tests`, aby sprawdzić, czy odpowiedź ma status `200`.
  4. Zapisz `id` utworzonej etykiety w zmiennych kolekcji jako `labelId`.

</details>

## Ćwiczenie 8: Przypisanie Etykiety do Karty

Zadanie:
Przypisz wcześniej utworzoną etykietę do karty.

<details>
  <summary>Instrukcje:</summary>

  1. Użyj zapytania `POST` do `/cards/{{cardId}}/idLabels`.
  2. W treści zapytania prześlij `id` etykiety.
  3. Sprawdź, czy w `Tests` odpowiedź ma status `200`.

</details>

## Ćwiczenie 9: Zmiana Nazwy Karty

Zadanie:
Zmień nazwę istniejącej karty.

<details>
  <summary>Instrukcje:</summary>

  1. Wyślij zapytanie `PUT` do `/cards/{{cardId}}/name`.
  2. Jako parametr (`query`) zapytania dodaj nową nazwę karty.
  3. Upewnij się, że test w sekcji `Tests` weryfikuje status odpowiedzi `200`.

</details>
