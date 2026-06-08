# Plan pracy nad projektem VELOCYCLE

## 1. Cel planu pracy

Celem planu pracy jest przedstawienie etapów realizacji projektu systemu VELOCYCLE, określenie czasu trwania poszczególnych etapów, zależności między nimi oraz przydziału zadań w zespole projektowym.

## 2. Etapy pracy

| Etap                          | Opis prac                                                                              | Czas trwania | Zależności                 | Odpowiedzialni        |
| ----------------------------- | -------------------------------------------------------------------------------------- | -----------: | -------------------------- | --------------------- |
| 1. Analiza wymagań            | Określenie celu systemu, zakresu, kontekstu, aktorów oraz głównych funkcji systemu     |        2 dni | Brak                       | Cały zespół           |
| 2. Słownik pojęć              | Przygotowanie definicji najważniejszych pojęć używanych w projekcie                    |      1 dzień | Etap 1                     | Analityk              |
| 3. Przypadki użycia           | Opracowanie diagramu przypadków użycia oraz opisów wybranych przypadków                |        3 dni | Etap 1                     | Analityk, projektant  |
| 4. Diagramy czynności         | Przygotowanie 3 diagramów czynności dla najważniejszych procesów                       |        2 dni | Etap 3                     | Projektant            |
| 5. Diagramy sekwencji         | Przygotowanie 3 diagramów sekwencji pokazujących komunikację między elementami systemu |        2 dni | Etap 3                     | Projektant            |
| 6. Diagram klas               | Opracowanie modelu klas systemu, atrybutów, metod oraz relacji                         |        3 dni | Etap 3                     | Projektant            |
| 7. Wykaz klas                 | Przygotowanie opisu klas, atrybutów i metod w porządku alfabetycznym                   |      1 dzień | Etap 6                     | Projektant            |
| 8. Diagramy stanów            | Przygotowanie 3 diagramów stanów dla wybranych klas                                    |        2 dni | Etap 6                     | Projektant            |
| 9. Projekt interfejsu         | Przygotowanie prototypu interfejsu użytkownika dla klienta, pracownika i serwisanta    |        3 dni | Etap 3                     | Projektant UI         |
| 10. Architektura i wdrożenie  | Przygotowanie opisu technologii, architektury oraz diagramu wdrożenia                  |        2 dni | Etap 6                     | Projektant techniczny |
| 11. Wymagania niefunkcjonalne | Określenie wymagań dotyczących wydajności, bezpieczeństwa, dostępności i bazy danych   |      1 dzień | Etap 1                     | Analityk              |
| 12. Analiza ryzyka            | Przygotowanie listy zagrożeń, skutków, metod zapobiegania i planów awaryjnych          |      1 dzień | Etap 1                     | Cały zespół           |
| 13. Kosztorys                 | Oszacowanie kosztów realizacji, wdrożenia, szkoleń i utrzymania systemu                |      1 dzień | Etap 10                    | Kierownik projektu    |
| 14. Kontrola i poprawki       | Sprawdzenie spójności dokumentacji, diagramów oraz repozytorium                        |        2 dni | Wszystkie poprzednie etapy | Cały zespół           |

## 3. Zależności między etapami

Analiza wymagań jest etapem początkowym i stanowi podstawę do przygotowania słownika pojęć, przypadków użycia, wymagań niefunkcjonalnych oraz analizy ryzyka. Diagram przypadków użycia jest podstawą do przygotowania diagramów czynności i diagramów sekwencji. Diagram klas jest powiązany z diagramami stanów oraz wykazem klas. Diagram wdrożenia i opis technologii powstają po ustaleniu głównych elementów systemu.

## 4. Alokacja zasobów ludzkich

W projekcie przewidziano następujące role:

* kierownik projektu — nadzoruje harmonogram, kosztorys i końcową dokumentację,
* analityk — odpowiada za wymagania, słownik pojęć, aktorów i przypadki użycia,
* projektant UML — odpowiada za diagramy klas, sekwencji, czynności i stanów,
* projektant UI — odpowiada za prototyp interfejsu użytkownika,
* projektant techniczny — odpowiada za technologie, architekturę i diagram wdrożenia,
* tester dokumentacji — sprawdza spójność dokumentów i diagramów.

## 5. Podsumowanie

Plan pracy zakłada realizację projektu w kilku etapach, od analizy wymagań po przygotowanie diagramów, dokumentacji technicznej, kosztorysu oraz końcową kontrolę projektu. Dzięki podziałowi pracy na etapy możliwe jest zachowanie porządku w projekcie oraz łatwiejsze sprawdzenie, czy wszystkie wymagania zostały spełnione.
