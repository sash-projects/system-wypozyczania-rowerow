# Wymagania niefunkcjonalne systemu VELOCYCLE

## 1. Wielkość bazy danych

System powinien obsługiwać bazę danych zawierającą co najmniej:

* 10 000 kont użytkowników,
* 2 000 rowerów,
* 100 000 rezerwacji rocznie,
* 50 000 wpisów w historii wypożyczeń rocznie,
* 20 000 zgłoszeń usterek rocznie,
* 10 000 zleceń serwisowych rocznie.

Baza danych powinna umożliwiać dalsze zwiększanie liczby rekordów bez konieczności zmiany podstawowej struktury systemu.

## 2. Czasy odpowiedzi systemu

System powinien spełniać następujące wymagania dotyczące czasu odpowiedzi:

* logowanie użytkownika: maksymalnie 2 sekundy,
* wyświetlenie listy rowerów: maksymalnie 2 sekundy,
* filtrowanie i wyszukiwanie rowerów: maksymalnie 2 sekundy,
* utworzenie rezerwacji: maksymalnie 3 sekundy,
* autoryzacja płatności: maksymalnie 5 sekund,
* zgłoszenie usterki: maksymalnie 3 sekundy,
* zmiana statusu roweru przez pracownika: maksymalnie 2 sekundy,
* wyświetlenie historii wypożyczeń: maksymalnie 3 sekundy.

## 3. Dostępność systemu

System powinien być dostępny przez całą dobę, ponieważ wypożyczalnia rowerów może działać w trybie 24/7. Zakładana dostępność systemu powinna wynosić co najmniej 99% w skali miesiąca.

## 4. Bezpieczeństwo

System powinien zapewniać:

* logowanie użytkowników przy użyciu hasła,
* rozróżnienie ról użytkowników,
* dostęp do panelu pracownika tylko dla uprawnionych osób,
* dostęp do panelu serwisowego tylko dla mistrza serwisowego,
* przesyłanie danych przez bezpieczne połączenie HTTPS,
* ochronę danych osobowych klientów,
* bezpieczną komunikację z zewnętrznym systemem płatności.

## 5. Liczba i typy stanowisk pracy

System powinien obsługiwać następujące stanowiska i urządzenia:

* urządzenie klienta: smartfon, tablet lub komputer,
* stanowisko pracownika wypożyczalni: komputer z dostępem do panelu pracownika,
* stanowisko mistrza serwisowego: komputer lub tablet z dostępem do panelu serwisowego,
* serwer aplikacyjny obsługujący backend systemu,
* serwer bazy danych przechowujący dane systemowe.

## 6. Skalowalność

System powinien umożliwiać zwiększenie liczby użytkowników, rowerów oraz rezerwacji bez konieczności całkowitej przebudowy aplikacji. W przyszłości możliwe powinno być dodanie nowych lokalizacji wypożyczalni oraz nowych typów rowerów.

## 7. Użyteczność

Interfejs użytkownika powinien być prosty i czytelny. Klient powinien móc szybko znaleźć rower, sprawdzić jego dostępność i złożyć rezerwację. Panel pracownika powinien umożliwiać szybkie zarządzanie flotą, rezerwacjami i zgłoszeniami usterek.

## 8. Kopie zapasowe

Dane systemowe powinny być regularnie zabezpieczane przez wykonywanie kopii zapasowych. Kopia bazy danych powinna być wykonywana co najmniej raz dziennie, aby ograniczyć ryzyko utraty danych.
