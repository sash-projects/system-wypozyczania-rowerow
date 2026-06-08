# Analiza ryzyka systemu VELOCYCLE

## 1. Cel analizy ryzyka

Celem analizy ryzyka jest wskazanie potencjalnych zagrożeń związanych z realizacją i działaniem systemu VELOCYCLE oraz określenie ich prawdopodobieństwa, skutków, metod zapobiegania i planów awaryjnych.

## 2. Tabela ryzyka

| Zagrożenie                                   | Prawdopodobieństwo | Skutek                                                                      | Metoda zapobiegania                                                          | Plan awaryjny                                                                    |
| -------------------------------------------- | ------------------ | --------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Awaria systemu płatności                     | Średnie            | Brak możliwości autoryzacji płatności i rozpoczęcia wypożyczenia            | Integracja ze sprawdzonym operatorem płatności, obsługa błędów transakcji    | Czasowe zapisanie rezerwacji jako oczekującej i ponowienie płatności później     |
| Brak dostępu do Internetu po stronie klienta | Średnie            | Klient nie może zarezerwować lub zakończyć wypożyczenia                     | Aplikacja powinna jasno informować o braku połączenia                        | Klient może skontaktować się z pracownikiem wypożyczalni                         |
| Nieaktualny status roweru                    | Średnie            | Klient może próbować zarezerwować rower, który nie jest faktycznie dostępny | Automatyczna aktualizacja statusów i blokada podwójnych rezerwacji           | Pracownik ręcznie zmienia status roweru i proponuje klientowi inny rower         |
| Uszkodzenie roweru podczas wypożyczenia      | Duże               | Rower staje się niedostępny, klient może nie zakończyć jazdy poprawnie      | Możliwość szybkiego zgłoszenia usterki i zmiana statusu roweru na W_SERWISIE | Utworzenie zgłoszenia serwisowego i przypisanie roweru do naprawy                |
| Kradzież roweru                              | Średnie            | Strata sprzętu i konieczność obsługi reklamacji                             | Kaucja, GPS, elektroniczna blokada, historia wypożyczeń                      | Zablokowanie roweru, kontakt z klientem i przekazanie danych odpowiednim służbom |
| Awaria elektronicznej blokady                | Średnie            | Klient nie może rozpocząć lub zakończyć wypożyczenia                        | Regularne przeglądy techniczne i monitorowanie statusu blokady               | Ręczne odblokowanie lub zablokowanie roweru przez pracownika                     |
| Błąd w danych rezerwacji                     | Średnie            | Niepoprawny termin, rower lub dane klienta                                  | Walidacja formularzy i potwierdzenie danych przed zapisaniem                 | Edycja lub anulowanie rezerwacji przez pracownika                                |
| Przeciążenie systemu                         | Niskie/Średnie     | Wolniejsze działanie aplikacji lub chwilowy brak dostępności                | Skalowalna architektura, optymalizacja zapytań do bazy danych                | Tymczasowe ograniczenie ruchu i zwiększenie zasobów serwera                      |
| Utrata danych                                | Niskie             | Utrata informacji o użytkownikach, rezerwacjach i historii wypożyczeń       | Regularne kopie zapasowe bazy danych                                         | Odtworzenie systemu z najnowszej kopii zapasowej                                 |
| Nieuprawniony dostęp do panelu pracownika    | Średnie            | Ryzyko zmiany danych systemowych przez nieuprawnioną osobę                  | Logowanie, role użytkowników, hasła, HTTPS                                   | Zablokowanie konta i analiza historii działań                                    |
| Błąd pracownika przy zmianie statusu roweru  | Średnie            | Rower może zostać błędnie oznaczony jako dostępny lub niedostępny           | Potwierdzenia przy ważnych operacjach i historia zmian                       | Ręczna korekta statusu oraz analiza zdarzenia                                    |
| Brak aktualizacji lokalizacji GPS            | Średnie            | System pokazuje nieprawidłowe położenie roweru                              | Regularne odświeżanie danych GPS i wykrywanie braku sygnału                  | Oznaczenie roweru jako wymagającego weryfikacji przez pracownika                 |

## 3. Najważniejsze ryzyka

Najważniejsze ryzyka dla systemu VELOCYCLE to awaria systemu płatności, kradzież roweru, uszkodzenie roweru podczas jazdy, awaria elektronicznej blokady oraz nieaktualny status roweru. Ryzyka te są bezpośrednio związane z podstawowym działaniem systemu i mogą wpływać na możliwość wypożyczenia roweru przez klienta.

## 4. Podsumowanie

Analiza ryzyka pozwala określić zagrożenia, które mogą wystąpić podczas działania systemu. Dla każdego zagrożenia wskazano sposób zapobiegania oraz plan awaryjny. Dzięki temu system VELOCYCLE może być bardziej odporny na problemy techniczne, organizacyjne i bezpieczeństwa.
