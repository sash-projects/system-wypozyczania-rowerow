# Wykaz klas systemu VELOCYCLE

## 1. Cel dokumentu

Celem dokumentu jest przedstawienie uporządkowanego wykazu klas występujących w systemie VELOCYCLE. Dla każdej klasy podano krótki opis, przykładowe atrybuty oraz metody. Wykaz jest zgodny z diagramem klas systemu wypożyczania rowerów.

## 2. Wykaz klas

## HistoriaWypozyczen

### Opis

Klasa przechowuje informacje o zakończonych i anulowanych wypożyczeniach rowerów. Umożliwia zapisywanie danych o kliencie, rowerze, czasie wypożyczenia oraz koszcie.

### Atrybuty

* id: int
* idKlienta: int
* idRoweru: int
* dataStartu: Date
* dataZakonczenia: Date
* koszt: double
* status: String

### Metody

* zapiszWypozyczenie(idKlienta: int, idRoweru: int, czas: int, kwota: double): void
* pobierzHistorieKlienta(idKlienta: int): List
* pobierzHistorieRoweru(idRoweru: int): List

## Klient

### Opis

Klasa reprezentuje użytkownika korzystającego z systemu jako klient wypożyczalni. Klient może rezerwować rowery, anulować rezerwacje, edytować profil oraz zgłaszać usterki.

### Atrybuty

* id: int
* imie: String
* nazwisko: String
* email: String
* telefon: String
* haslo: String

### Metody

* zarejestruj(): void
* zaloguj(): boolean
* edytujProfil(): void
* zarezerwujRower(): Rezerwacja
* anulujRezerwacje(idRezerwacji: int): void
* zglosUsterke(): ZgloszenieUsterki

## MistrzSerwisowy

### Opis

Klasa reprezentuje osobę odpowiedzialną za naprawę rowerów. Mistrz serwisowy obsługuje zlecenia serwisowe i oznacza zakończenie naprawy.

### Atrybuty

* id: int
* imie: String
* nazwisko: String
* email: String
* specjalizacja: String

### Metody

* przyjmijZlecenie(idZlecenia: int): void
* naprawRower(idRoweru: int): void
* zglosZakonczenieNaprawy(idZlecenia: int): void

## Pracownik

### Opis

Klasa reprezentuje pracownika wypożyczalni. Pracownik zarządza flotą rowerów, rezerwacjami, zgłoszeniami usterek oraz historią wypożyczeń.

### Atrybuty

* id: int
* imie: String
* nazwisko: String
* email: String
* stanowisko: String

### Metody

* zatwierdzRezerwacje(idRezerwacji: int): void
* anulujRezerwacje(idRezerwacji: int): void
* zakonczWypozyczenie(idRezerwacji: int): void
* zmienStatusRoweru(idRoweru: int, status: StatusRoweru): void
* przegladajUsterki(): List

## Rezerwacja

### Opis

Klasa reprezentuje rezerwację roweru przez klienta. Przechowuje informacje o terminie, lokalizacji, kwocie, kaucji oraz statusie rezerwacji.

### Atrybuty

* id: int
* dataOd: Date
* dataDo: Date
* lokalizacja: String
* kwota: double
* kaucja: double
* czasStartu: Date
* czasZakonczenia: Date
* status: StatusRezerwacji

### Metody

* utworzRezerwacje(idKlienta: int, idRoweru: int): Rezerwacja
* anuluj(): void
* zakoncz(): void
* obliczKwote(): double
* setCzasStartu(czas: Date): void

## Rower

### Opis

Klasa reprezentuje rower znajdujący się we flocie wypożyczalni. Rower posiada status, lokalizację, cenę za godzinę oraz może być wyposażony w funkcje IoT, takie jak GPS i elektroniczna blokada.

### Atrybuty

* id: int
* model: String
* typ: String
* cenaZaGodzine: double
* status: StatusRoweru
* lokalizacja: String
* pozycjaGPS: String
* stanBlokady: String

### Metody

* getStatus(): StatusRoweru
* setStatus(status: StatusRoweru): void
* zablokuj(): void
* odblokuj(): void
* pobierzPozycjeGPS(): String

## SystemPlatnosci

### Opis

Klasa reprezentuje zewnętrzny system lub moduł odpowiedzialny za płatności. Obsługuje autoryzację środków, kaucję, potwierdzanie transakcji oraz zwroty.

### Atrybuty

* idTransakcji: int
* kwota: double
* statusTransakcji: String

### Metody

* autoryzujPlatnosc(kwota: double): boolean
* potwierdzTransakcje(): String
* realizujZwrot(kwota: double): boolean

## ZgloszenieUsterki

### Opis

Klasa reprezentuje zgłoszenie problemu technicznego dotyczącego roweru. Zgłoszenie może być utworzone przez klienta lub pracownika i może prowadzić do utworzenia zlecenia serwisowego.

### Atrybuty

* id: int
* idRoweru: int
* idKlienta: int
* opis: String
* dataZgloszenia: Date
* priorytet: Priorytet
* status: String

### Metody

* utworz(idKlienta: int, idRoweru: int, opis: String): ZgloszenieUsterki
* przyjmij(): void
* zamknij(): void
* zmienPriorytet(priorytet: Priorytet): void

## ZlecenieSerwisowe

### Opis

Klasa reprezentuje zlecenie naprawy roweru utworzone na podstawie zgłoszenia usterki. Zlecenie jest obsługiwane przez mistrza serwisowego.

### Atrybuty

* id: int
* idZgloszenia: int
* idRoweru: int
* idSerwisanta: int
* dataUtworzenia: Date
* dataZakonczenia: Date
* status: String

### Metody

* utworzNaPodstawieZgloszenia(idZgloszenia: int): ZlecenieSerwisowe
* przydzielSerwisanta(idSerwisanta: int): void
* oznaczJakoZakonczone(): void
