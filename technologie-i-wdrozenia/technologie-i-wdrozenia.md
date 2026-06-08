# Technologie informatyczne i wdrożenie systemu VELOCYCLE

## 1. Propozycja technologii informatycznych

System VELOCYCLE może zostać zrealizowany jako aplikacja webowa z podziałem na część kliencką, część serwerową oraz bazę danych. System powinien umożliwiać korzystanie z aplikacji przez klienta, pracownika wypożyczalni oraz mistrza serwisowego.

## 2. Frontend

Do wykonania interfejsu użytkownika można wykorzystać:

* HTML,
* CSS,
* JavaScript,
* opcjonalnie framework React.

Frontend odpowiada za prezentację danych użytkownikowi, obsługę formularzy, wyświetlanie dostępnych rowerów, rezerwacji, historii wypożyczeń, panelu pracownika oraz panelu serwisowego.
## 3. Backend

Część serwerowa systemu może zostać wykonana z użyciem jednej z następujących technologii:

* Java Spring Boot,
* Node.js z Express,
* Python Django lub Flask.

Backend odpowiada za logikę działania systemu, autoryzację użytkowników, obsługę rezerwacji, zarządzanie flotą rowerów, obsługę zgłoszeń usterek, zleceń serwisowych oraz komunikację z bazą danych i systemem płatności.

## 4. Baza danych

Do przechowywania danych można wykorzystać relacyjną bazę danych:

* PostgreSQL,
* MySQL,
* MariaDB.

W bazie danych przechowywane są informacje o użytkownikach, rowerach, rezerwacjach, zgłoszeniach usterek, zleceniach serwisowych, historii wypożyczeń oraz płatnościach.

## 5. System płatności

System VELOCYCLE powinien współpracować z zewnętrznym systemem płatności. System płatności odpowiada za:

* autoryzację płatności,
* obsługę kaucji,
* potwierdzanie transakcji,
* realizację zwrotów.

Komunikacja z systemem płatności odbywa się przez bezpieczne API z wykorzystaniem protokołu HTTPS.

## 6. Komunikacja z rowerami IoT

Rowery mogą być wyposażone w moduł IoT, który umożliwia:

* przesyłanie lokalizacji GPS,
* przesyłanie statusu roweru,
* obsługę elektronicznej blokady,
* informowanie systemu o zakończeniu wypożyczenia lub awarii.

Komunikacja roweru z serwerem może odbywać się przez Internet, LTE lub inne API przeznaczone dla urządzeń IoT.

## 7. Repozytorium i dokumentacja

Do zarządzania projektem i wersjonowania plików wykorzystywany jest GitHub. Dokumentacja projektu może być przechowywana w plikach Markdown, natomiast diagramy mogą być przygotowane w PlantUML, Mermaid lub draw.io.

## 8. Diagram wdrożenia

Diagram wdrożenia przedstawia fizyczne rozmieszczenie elementów systemu VELOCYCLE. Klient korzysta z aplikacji klienta na smartfonie lub komputerze. Pracownik wypożyczalni korzysta z panelu pracownika, a mistrz serwisowy z panelu serwisowego. Wszystkie te elementy komunikują się z serwerem aplikacyjnym przez protokół HTTPS.

Na serwerze aplikacyjnym działa backend systemu VELOCYCLE. Backend komunikuje się z bazą danych, zewnętrznym systemem płatności oraz rowerami IoT. Baza danych przechowuje dane systemowe, system płatności obsługuje transakcje, a rowery IoT przekazują informacje o lokalizacji, statusie i stanie blokady.
