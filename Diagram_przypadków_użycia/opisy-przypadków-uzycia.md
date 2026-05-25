# Opisy przypadków użycia

# 1. Zarezerwuj rower

## Aktorzy
- Klient zalogowany
- System płatności

## Opis
Klient wybiera dostępny rower i dokonuje jego rezerwacji.

## Scenariusz podstawowy
1. Klient loguje się do systemu.
2. System wyświetla listę dostępnych rowerów.
3. Klient wybiera rower.
4. System przekierowuje do płatności.
5. Klient dokonuje płatności.
6. System tworzy rezerwację.
7. Klient otrzymuje potwierdzenie.

## Scenariusz alternatywny
- Brak dostępnych rowerów.
- Nieudana płatność.
- Anulowanie operacji przez użytkownika.

## Częstotliwość
Codziennie.

## Czas realizacji
1–3 minuty.

## Korzyść dla aktora
Szybkie wypożyczenie roweru online.



# 2. Zgłoś usterkę

## Aktorzy
- Klient zalogowany
- Pracownik
- Mistrz serwisowy

## Opis
Klient zgłasza problem techniczny związany z rowerem.

## Scenariusz podstawowy
1. Klient wybiera opcję „Zgłoś usterkę”.
2. Klient wpisuje opis problemu.
3. System zapisuje zgłoszenie.
4. Pracownik przegląda zgłoszenie.
5. Pracownik przekazuje zgłoszenie mistrzowi serwisowemu.
6. Mistrz serwisowy przyjmuje zlecenie naprawy.

## Scenariusz alternatywny
- Niepełny opis zgłoszenia.
- Błąd zapisu zgłoszenia.
- Brak dostępnego serwisanta.

## Częstotliwość
Kilka razy dziennie.

## Czas realizacji
2–5 minut.

## Korzyść dla aktora
Możliwość szybkiego zgłoszenia problemu z rowerem.



# 3. Zakończ wypożyczenie

## Aktorzy
- Klient zalogowany
- Pracownik

## Opis
Proces zakończenia aktywnego wypożyczenia roweru.

## Scenariusz podstawowy
1. Klient oddaje rower.
2. Pracownik sprawdza stan roweru.
3. System oblicza koszt wypożyczenia.
4. System kończy rezerwację.
5. Status roweru zostaje zmieniony na dostępny.

## Scenariusz alternatywny
- Rower jest uszkodzony.
- Nie udało się zakończyć płatności.
- Błąd systemu.

## Częstotliwość
Codziennie.

## Czas realizacji
1–2 minuty.

## Korzyść dla aktora
Poprawne zakończenie wypożyczenia i zwrot roweru.
