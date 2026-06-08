# Opisy przypadków użycia systemu VELOCYCLE

## 1. Aktorzy systemu

## Klient niezalogowany

Klient niezalogowany to użytkownik, który nie posiada aktywnej sesji w systemie. Może przeglądać dostępne rowery, filtrować i wyszukiwać rowery oraz przejść do rejestracji lub logowania.

## Klient zalogowany

Klient zalogowany to użytkownik posiadający konto w systemie. Może rezerwować rowery, anulować swoje rezerwacje, przeglądać historię, edytować profil oraz zgłaszać usterki.

## Pracownik

Pracownik to osoba obsługująca wypożyczalnię. Zarządza flotą rowerów, rezerwacjami, historią wypożyczeń oraz zgłoszeniami usterek.

## Mistrz serwisowy

Mistrz serwisowy to osoba odpowiedzialna za naprawę rowerów. Przyjmuje zlecenia serwisowe, wykonuje naprawy oraz zgłasza zakończenie prac.

## System płatności

System płatności to zewnętrzny aktor odpowiedzialny za autoryzację płatności, obsługę kaucji, potwierdzanie transakcji oraz realizację zwrotów.

# 2. Dokładne opisy wybranych przypadków użycia

## Przypadek użycia: Zarezerwuj rower

### Aktor główny

Klient zalogowany.

### Aktorzy pomocniczy

System płatności.

### Warunki wstępne

* Klient posiada konto w systemie.
* Klient jest zalogowany.
* W systemie istnieje co najmniej jeden dostępny rower.
* System płatności jest dostępny.

### Przebieg podstawowy

1. Klient przechodzi do listy dostępnych rowerów.
2. System wyświetla rowery dostępne w wybranej lokalizacji.
3. Klient wybiera rower.
4. Klient wybiera datę odbioru, datę zwrotu oraz lokalizację.
5. System sprawdza dostępność wybranego roweru.
6. System wyświetla podsumowanie rezerwacji oraz informację o wymaganej kaucji.
7. Klient potwierdza rezerwację.
8. System przekazuje dane płatności do systemu płatności.
9. System płatności autoryzuje płatność lub kaucję.
10. System tworzy rezerwację.
11. System zmienia status roweru na wypożyczony lub zarezerwowany.
12. System wyświetla klientowi potwierdzenie rezerwacji.

### Przebieg alternatywny

* Jeśli rower nie jest dostępny, system informuje klienta i proponuje wybór innego roweru.
* Jeśli płatność nie zostanie autoryzowana, rezerwacja nie zostaje utworzona.
* Jeśli klient poda niepoprawne dane, system wyświetla komunikat o błędzie i prosi o poprawienie formularza.

### Rezultat

Rezerwacja zostaje zapisana w systemie, klient otrzymuje potwierdzenie, a rower zmienia status zgodnie z przebiegiem rezerwacji.

## Przypadek użycia: Zakończ wypożyczenie

### Aktor główny

Klient zalogowany.

### Aktorzy pomocniczy

System płatności, rower IoT.

### Warunki wstępne

* Klient ma aktywne wypożyczenie.
* Rower jest oznaczony jako wypożyczony.
* System ma dostęp do danych rezerwacji.
* Rower może przesłać informację o blokadzie lub lokalizacji.

### Przebieg podstawowy

1. Klient wybiera opcję zakończenia wypożyczenia w aplikacji.
2. System wysyła polecenie zablokowania roweru.
3. Rower potwierdza zablokowanie elektronicznej blokady.
4. System pobiera lokalizację GPS roweru.
5. System zapisuje czas zakończenia wypożyczenia.
6. System oblicza końcową kwotę wypożyczenia.
7. System przekazuje informację do systemu płatności.
8. System płatności potwierdza transakcję.
9. System zmienia status roweru na dostępny.
10. System zapisuje wypożyczenie w historii.
11. System wyświetla klientowi podsumowanie oraz paragon.

### Przebieg alternatywny

* Jeśli rower nie potwierdzi zablokowania, system informuje klienta o problemie i oznacza wypożyczenie jako wymagające weryfikacji.
* Jeśli płatność nie zostanie potwierdzona, system zapisuje informację o problemie i przekazuje ją pracownikowi.
* Jeśli lokalizacja GPS nie jest dostępna, system kończy wypożyczenie, ale oznacza je do ręcznej kontroli.

### Rezultat

Wypożyczenie zostaje zakończone, transakcja zostaje potwierdzona, rower zmienia status, a dane trafiają do historii wypożyczeń.

## Przypadek użycia: Zgłoś usterkę

### Aktor główny

Klient zalogowany.

### Aktorzy pomocniczy

Pracownik, mistrz serwisowy.

### Warunki wstępne

* Klient jest zalogowany.
* Rower istnieje w systemie.
* Klient może wskazać rower, którego dotyczy usterka.

### Przebieg podstawowy

1. Klient wybiera opcję zgłoszenia usterki.
2. System wyświetla formularz zgłoszenia.
3. Klient wybiera rower, typ awarii oraz wpisuje opis problemu.
4. Klient może dodać zdjęcie usterki.
5. Klient wysyła formularz.
6. System tworzy zgłoszenie usterki.
7. System nadaje zgłoszeniu priorytet.
8. System zmienia status roweru na w serwisie lub niedostępny.
9. System blokuje możliwość dalszego wypożyczania roweru.
10. System tworzy zlecenie serwisowe.
11. System przekazuje informację do panelu serwisowego.
12. Klient otrzymuje komunikat o przyjęciu zgłoszenia.

### Przebieg alternatywny

* Jeśli formularz jest niekompletny, system prosi o uzupełnienie brakujących danych.
* Jeśli rower jest już w serwisie, system dopisuje zgłoszenie do istniejącego problemu.
* Jeśli zgłoszenie nie może zostać zapisane, system informuje klienta o błędzie.

### Rezultat

Zgłoszenie usterki zostaje zapisane w systemie, rower zostaje zabezpieczony, a zlecenie serwisowe trafia do obsługi przez pracownika lub mistrza serwisowego.
