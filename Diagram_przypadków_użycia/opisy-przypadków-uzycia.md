# Opisy przypadków użycia systemu VELOCYCLE

## 1. Zarezerwuj rower

### Aktor główny
- Klient zalogowany

### Aktorzy pomocniczy
- System płatności

### Opis
Klient rezerwuje dostępny rower poprzez system VELOCYCLE. Rezerwacja zostaje zapisana po poprawnym wykonaniu płatności.

### Scenariusz podstawowy
1. Klient loguje się do systemu.
2. System wyświetla listę dostępnych rowerów.
3. Klient filtruje lub wyszukuje rower.
4. Klient wybiera rower.
5. System sprawdza dostępność roweru.
6. Klient rozpoczyna proces rezerwacji.
7. System płatności autoryzuje płatność.
8. System zapisuje rezerwację.
9. Klient otrzymuje potwierdzenie rezerwacji.

### Scenariusze alternatywne
- Wybrany rower jest już zarezerwowany.
- Płatność została odrzucona.
- Klient anuluje operację przed zakończeniem rezerwacji.

### Częstotliwość
Bardzo często, codziennie.

### Czas realizacji
Typowo 1–3 minuty.

### Wartość dla aktora
Możliwość szybkiego wypożyczenia roweru online bez kontaktu z obsługą.



## 2. Zgłoś usterkę

### Aktor główny
- Klient zalogowany

### Aktorzy pomocniczy
- Pracownik
- Mistrz serwisowy

### Opis
Klient zgłasza problem techniczny dotyczący roweru. Zgłoszenie trafia do pracownika oraz mistrza serwisowego odpowiedzialnego za naprawę.

### Scenariusz podstawowy
1. Klient loguje się do systemu.
2. Klient wybiera opcję „Zgłoś usterkę”.
3. System wyświetla formularz zgłoszenia.
4. Klient wybiera rower, którego dotyczy problem.
5. Klient wpisuje opis usterki.
6. System zapisuje zgłoszenie ze statusem „otwarte”.
7. Pracownik przegląda zgłoszenie.
8. Pracownik przekazuje zgłoszenie mistrzowi serwisowemu.
9. Mistrz serwisowy przyjmuje zlecenie naprawy.

### Scenariusze alternatywne
- Klient nie podał opisu problemu.
- Wybrany rower nie istnieje w systemie.
- Zgłoszenie zostało odrzucone przez pracownika.

### Częstotliwość
Kilka razy w tygodniu lub częściej w sezonie.

### Czas realizacji
2–5 minut.

### Wartość dla aktora
Możliwość szybkiego zgłoszenia problemu i poprawa bezpieczeństwa użytkowników.



## 3. Zarządzaj flotą

### Aktor główny
- Pracownik

### Opis
Pracownik zarządza flotą rowerów znajdujących się w systemie. Może dodawać nowe rowery, usuwać je, zmieniać ich status oraz edytować dane.

### Scenariusz podstawowy
1. Pracownik loguje się do systemu.
2. Pracownik otwiera moduł zarządzania flotą.
3. System wyświetla listę rowerów.
4. Pracownik wybiera operację:
   - dodanie roweru,
   - edycję danych,
   - zmianę statusu,
   - usunięcie roweru.
5. Pracownik wprowadza wymagane dane.
6. System sprawdza poprawność danych.
7. System zapisuje zmiany.
8. System wyświetla komunikat o poprawnym wykonaniu operacji.

### Scenariusze alternatywne
- Dane roweru są niepoprawne lub niepełne.
- Rower posiada aktywną rezerwację i nie może zostać usunięty.
- Status roweru został zmieniony na „w serwisie”.

### Częstotliwość
Regularnie, kilka razy w tygodniu.

### Czas realizacji
1–4 minuty.

### Wartość dla aktora
Możliwość utrzymywania aktualnej i poprawnej bazy rowerów.



## 4. Zarządzaj rezerwacjami

### Aktor główny
- Pracownik

### Opis
Pracownik zarządza aktywnymi rezerwacjami klientów. Może zatwierdzać, anulować lub kończyć wypożyczenia oraz przeglądać historię operacji.

### Scenariusz podstawowy
1. Pracownik loguje się do systemu.
2. System wyświetla listę aktualnych rezerwacji.
3. Pracownik wybiera konkretną rezerwację.
4. Pracownik wykonuje wybraną operację.
5. System aktualizuje status rezerwacji.
6. System zapisuje zmiany w historii wypożyczeń.
7. System wyświetla potwierdzenie wykonania operacji.

### Scenariusze alternatywne
- Rezerwacja została wcześniej anulowana.
- Rower nie został oddany na czas.
- Podczas zakończenia wypożyczenia wykryto uszkodzenie roweru.

### Częstotliwość
Codziennie.

### Czas realizacji
1–3 minuty.

### Wartość dla aktora
Możliwość kontrolowania przebiegu wypożyczeń i utrzymywania poprawności danych systemowych.
