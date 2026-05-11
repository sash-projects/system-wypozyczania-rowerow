 Opis przypadków użycia — System VELOCYCLE


Aktorzy systemu

Klient niezalogowany** — użytkownik bez konta. Może się zarejestrować, zalogować oraz przeglądać listę rowerów.

Klient zalogowany** — zarejestrowany użytkownik. Składa i anuluje rezerwacje, zgłasza usterki, przegląda swoje rezerwacje i edytuje profil.

Pracownik** — obsługa wypożyczalni. Zarządza flotą, przetwarza rezerwacje, obsługuje usterki i wzywa mistrza serwisowego.

Mistrz serwisowy** — technik. Przyjmuje zlecenia, naprawia rowery i zgłasza zakończenie naprawy.

System płatności** — zewnętrzny aktor automatyczny uczestniczący w procesie rezerwacji.


Przypadek użycia 1 — Składanie rezerwacji

Uczestniczący aktorzy: Klient zalogowany, System płatności

Podstawowy ciąg zdarzeń

1. Klient przegląda listę dostępnych rowerów (`<<include>>` Przeglądaj rowery).
2. Klient opcjonalnie zawęża wyniki (`<<extend>>` Filtruj i szukaj).
3. Klient wybiera rower i przechodzi do formularza rezerwacji.
4. Klient podaje datę odbioru, datę zwrotu i lokalizację.
5. Klient zatwierdza formularz.
6. System weryfikuje poprawność danych.
7. System płatności obsługuje transakcję.
8. System zapisuje rezerwację ze statusem `oczekuje`, rower otrzymuje status `wypożyczony`.
9. System wyświetla potwierdzenie z numerem rezerwacji.

### Alternatywne ciągi zdarzeń

**a) Błędne dane (krok 6)** — system zaznacza błędne pola; klient poprawia i ponownie zatwierdza.

**b) Płatność odrzucona (krok 7)** — rezerwacja nie zostaje zapisana; klient może ponowić próbę.

**c) Klient anuluje formularz** — brak zmian w systemie, powrót do listy rowerów.

### Wartości uzyskiwane przez aktorów

**Klient** — potwierdzenie z numerem rezerwacji; wpis w zakładce „Moje rezerwacje".
**System** — nowy wpis w rejestrze; zaktualizowany status roweru.

---

 Przypadek użycia 2 — Zarządzanie rezerwacjami (Pracownik)

*Uczestniczący aktorzy: Pracownik

Przypadek nadrzędny zawierający trzy operacje podrzędne (`<<include>>`): Zatwierdź rezerwację, Anuluj rezerwację (P), Zakończ wypożyczenie. Historia wypożyczeń jest rozszerzana (`<<extend>>`) przy każdym zakończeniu.

Podstawowy ciąg zdarzeń — zatwierdzenie

1. Pracownik otwiera panel rezerwacji i widzi listę ze statusami.
2. Pracownik wybiera rezerwację o statusie `oczekuje`.
3. Weryfikuje dane klienta i dostępność roweru.
4. Pracownik klika „Zatwierdź" (`<<include>>` Zatwierdź rezerwację).
5. System zmienia status rezerwacji na `aktywna`.

 Podstawowy ciąg zdarzeń — zakończenie wypożyczenia

1. Klient zwraca rower do wypożyczalni.
2. Pracownik klika „Zakończ wypożyczenie" (`<<include>>` Zakończ wypożyczenie).
3. System zmienia status rezerwacji na `zakończona`.
4. System zmienia status roweru na `dostępny`.
5. Wpis automatycznie trafia do historii (`<<extend>>` Historia wypożyczeń).

 Alternatywne ciągi zdarzeń

a) Pracownik anuluje rezerwację (krok 2)** — `<<include>>` Anuluj rezerwację (P) — system zwalnia rower niezależnie od woli klienta, np. przy awarii jednostki.

b) Brak rezerwacji do przetworzenia** — system wyświetla pustą listę z komunikatem.



### Wartości uzyskiwane przez aktorów

**Pracownik** — aktualny stan wszystkich rezerwacji; możliwość interwencji w każdym statusie.
**System** — spójny rejestr rezerwacji; zaktualizowana dostępność floty.

---

Przypadek użycia 3 — Obsługa usterki

**Uczestniczący aktorzy:** Pracownik, Mistrz serwisowy

Najbardziej rozbudowany przepływ w systemie — angażuje dwóch aktorów i cztery zagnieżdżone przypadki użycia: Przeglądaj usterki → `<<include>>` Przyjmij zgłoszenie → `<<include>>` Wezwij mistrza → `<<include>>` Przyjmij zlecenie → Napraw rower → `<<include>>` Zgłoś zakończenie → `<<include>>` Zamknij zgłoszenie.

Podstawowy ciąg zdarzeń

1. Pracownik otwiera listę usterek (`<<include>>` Przeglądaj usterki), posortowaną według priorytetu.
2. Pracownik wybiera otwarte zgłoszenie i przyjmuje je do realizacji (`<<include>>` Przyjmij zgłoszenie).
3. System zmienia status zgłoszenia na `w trakcie`.
4. Pracownik tworzy zlecenie serwisowe i przydziela je mistrzowi (`<<include>>` Wezwij mistrza).
5. Mistrz serwisowy widzi nowe zlecenie i przyjmuje je (`<<include>>` Przyjmij zlecenie).
6. Mistrz wykonuje naprawę roweru (`<<include>>` Napraw rower).
7. Mistrz zgłasza zakończenie naprawy (`<<include>>` Zgłoś zakończenie).
8. Pracownik weryfikuje naprawę i zamyka zgłoszenie (`<<include>>` Zamknij zgłoszenie).
9. System zmienia status zgłoszenia na `naprawione` i status roweru na `dostępny`.

Alternatywne ciągi zdarzeń

a) Mistrz nie może przyjąć zlecenia (krok 5)** — pracownik przydziela je innemu mistrzowi lub zmienia termin realizacji.

b) Naprawa niemożliwa (krok 6)** — mistrz zgłasza brak możliwości naprawy; pracownik zmienia status roweru na `niedostępny` i zamyka zgłoszenie z adnotacją.

c) Pracownik odrzuca zgłoszenie jako bezzasadne (krok 2)** — zmienia status na `zamknięte` bez angażowania mistrza.


 Wartości uzyskiwane przez aktorów

Pracownik— zamknięte zgłoszenie; rower przywrócony do floty z aktualnym statusem.
Mistrz serwisowy — potwierdzone wykonanie zlecenia; historia serwisowa jednostki.
System— zaktualizowany status roweru i zgłoszenia; pełny log zdarzeń serwisowych.
