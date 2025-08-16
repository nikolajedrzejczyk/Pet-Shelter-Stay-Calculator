# Pet-Shelter-Stay-Calculator
Prediction of shelter pet length of stay using animal data to improve shelter resource and financial management and increase adoption chances. (Przewidywanie długości pobytu zwierząt w schronisku na podstawie danych dotyczących zwierząt dla lepszego zarządzania finansami i zasobami schroniska w celu zwiększenia prawdopodobieństwa adopcji.)

Adres aplikacji: https://inzynieria-oprogramowania-kalkulator-dni.streamlit.app

Projekt stworzony we współpracy w ramach przedmiotu Inżynieria oprogramowania na Uniwersytecie Gdańskim. [Luty 2025]

---

## Wymagana dokumentacja:

### Charakterystyka oprogramowania:

**Nazwa skrócona:** *Kalkulator dni*  

**Nazwa pełna:** Kalkulator Przewidywania Długości Pobytu Zwierząt Domowych w Schronisku  

**Krótki opis ze wskazaniem celów:** Celem aplikacji *Kalkulator Przewidywania Długości Pobytu Zwierząt Domowych w Schronisku* jest wspieranie schronisk w lepszym zarządzaniu zasobami oraz poprawie opieki nad zwierzętami poprzez analizę kluczowych danych i przewidywanie czasu adopcji. Dzięki temu narzędziu schroniska mogą lepiej planować fundusze, skracać czas oczekiwania na nowe domy oraz zwiększać szanse zwierząt na adopcję.

---

## Prawa autorskie:

**Autorki:** Aleksandra Gomulak, Nikola Jędrzejczyk  
**Licencja:** GNU GENERAL PUBLIC LICENSE, Version 2  

---

## Specyfikacja wymagań:

| identyfikator | nazwa               | opis                                                                                      | priorytet  | kategoria       |
|---------------|---------------------|------------------------------------------------------------------------------------------|------------|-----------------|
| `WYM-001`       | Wprowadzenie danych | Użytkownik może wprowadzić parametry zwierzęcia, takie jak wiek, waga, płeć, typ rasy.   | Wymagane   | Funkcjonalne    |
| `WYM-002`       | Rozpoznawanie gatunku | Aplikacja rozpoznaje, czy przesłane zdjęcie przedstawia kota, czy psa, przy użyciu sieci neuronowej. | Wymagane | Funkcjonalne    |
| `WYM-003`       | Szacowanie czasu pobytu | Aplikacja, na podstawie wprowadzonych parametrów i rozpoznania gatunku, szacuje czas pobytu w schronisku. | Wymagane | Funkcjonalne    |
| `WYM-004`       | Wizualizacja wyników | Wynik szacowania jest przedstawiany użytkownikowi w formie przejrzystego komunikatu (np. liczba dni). | Przydatne | Funkcjonalne    |
| `WYM-005`       | Wydajność przetwarzania | Wynik szacowania czasu pobytu zwierzęcia powinien być dostępny w czasie krótszym niż 3 sekundy. | Wymagane | Pozafunkcjonalne |
| `WYM-006`       | Dokładność klasyfikatora | Klasyfikator czasu pobytu informuje o możliwym błędzie szacowania na podstawie testowych danych adoptowanych zwierząt. | Wymagane | Pozafunkcjonalne |
| `WYM-007`       | Instrukcja użytkowania | Aplikacja dostarcza instrukcje użytkowania.                                               | Przydatne  | Funkcjonalne    |
| `WYM-008`       | WebScraping          | Aplikacja automatycznie pobiera zdefiniowane dane ze strony internetowej.                 | Wymagane   | Funkcjonalne    |

---

## Architektura systemu/oprogamowania: 

### Architektura rozwoju:

| nazwa                          | przeznaczenie                                                                                       | wersja               |
|--------------------------------|-----------------------------------------------------------------------------------------------------|----------------------|
| `Python`                         | Główny język programowania                                                                          | 3.10.12              |
| `Streamlit`                      | Framework do tworzenia interfejsu aplikacji                                                        | 1.41.0               |
| `pandas`, `numpy`, `matplotlib`, `seaborn` | Analiza i przetwarzanie danych                                                                  | 2.2.2, 1.26.4, 3.10.0, 0.13.2 |
| `sklearn`, `tensorflow`, `keras`     | Model rozpoznający gatunek zwierzęcia ze zdjęcia oraz model przewidujący szacowaną liczbę dni pobytu w schronisku | 1.6.0, 2.17.1, 3.5.0 |
| `catboost`                      | Model przewidujący szacowaną liczbę dni pobytu w schronisku                   | 1.2.7                       |
| `time`                          | Wyświetlanie GIF-a oraz przewidywanie czasu pobytu                            | Wbudowana funkcja           |
| `base64`                        | Wyświetlanie GIF-a                                                            | Wbudowana funkcja           |
| `zipfile`                       | Rozpakowanie pliku .zip                                                       | Wbudowana funkcja           |
| `PIL`                           | Otwieranie zdjęć                                                              | 11.1.0                      |
| `os`                            | Otwieranie plików                                                             | Wbudowana funkcja           |
| `re`                            | Znajdowanie słów w opisie zwierzęcia w celu identyfikacji cech                | Wbudowana funkcja           |
| `requests`, `bs4`                | Pobieranie szczegółowych danych zwierzęcia ze strony internetowej              | 2.32.3, 4.12.3              |
| `shutil`                        | Pobieranie plików .zip                                                        | Wbudowana funkcja           |


### Architektura uruchomieniowa:

| nazwa             | przeznaczenie                                | wersja  |
|-------------------|-----------------------------------------------|---------|
| `Python`            | Wymagany język do uruchamiania aplikacji      | 3.9+    |
| `Streamlit Cloud`   | Hosting i uruchamianie aplikacji              | 1.41.0  |
| `Przeglądarka`      | Dostęp do interfejsu użytkownika              | Dowolna |

---

## Testy:

### Scenariusze testów:

| identyfikator testu | opis testu                                           | dane testowe                                                                 | oczekiwany rezultat                                                                                                      |
|---------------------|------------------------------------------------------|-------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| `TEST-001`            | Sprawdzenie kalkulacji długości pobytu               | Użytkownik może wprowadzić parametry zwierzęcia, takie jak wiek, waga, płeć, typ rasy. | Gatunek: pies, Rasa: Kundelek/nie mam pewności, Płeć: samiec, Wiek: 0 lat 5 miesięcy, Waga: 5kg, Cechy: przyjazny, aktywny |
| `TEST-002`            | Wybór rasy w menu                                    | Gatunek: kot.                                                                 | Na następnej stronie zostają wyświetlone rasy kotów                                                                       |
| `TEST-003`            | Sprawdzenie poprawności zmian stron (Cofnij/Dalej)   | Kliknięcie przycisku `Cofnij/Dalej`.                                          | Zmiana strony na poprzednią/następną                                                                                      |
| `TEST-004`            | Sprawdzenie poprawności interfejsu (Rozpocznij)      | Kliknięcie przycisku `Rozpocznij`.                                            | Przekierowanie do strony z pierwszym pytaniem                                                                             |
| `TEST-005`            | Sprawdzenie poprawności interfejsu (Oblicz ponownie) | Kliknięcie przycisku `Oblicz ponownie`.                                       | Przekierowanie do strony z pierwszym pytaniem                                                                             |
| `TEST-006`            | Sprawdzenie poprawności interfejsu (Nie wiem)        | Kliknięcie przycisku `Nie wiem`.                                              | Ustawienie cech zwierzęcia jako „niezidentyfikowany”                                                                      |
| `TEST-007`            | Sprawdzenie poprawności slider'a                      | Przesunięcie punktora po sliderze.                                            | Ustawienie liczby jako np. 5                                                                                              |
| `TEST-008`            | Sprawdzenie poprawności interfejsu (Brak rasy)       | Kliknięcie przycisku `Kundelek/dachowiec/nie mam pewności`.                   | Zapisanie rasy jako „Mieszaniec”/„Europejska”                                                                             |
| `TEST-009`            | Obsługa danych                                       | Gatunek: pies, Rasa: Kundelek/nie mam pewności, Płeć: samiec, Wiek: 0 lat 5 miesięcy, Waga: 5kg, Cechy: przyjazny, aktywny. | Aplikacja zwraca stosowny wynik w rozsądnym czasie                                                                        |

---

### Sprawozdanie z wykonania scenariuszy testów:

| identyfikator testu | status | rzeczywisty rezultat                                                                 | komentarz                                                                                                               |
|---------------------|--------|---------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| `TEST-001`          | PASS   | Wynik: „58 dni”                                                                        | Test zakończony sukcesem                                                                                                |
| `TEST-002`         | PASS   | Na następnej stronie zostają wyświetlone jedynie rasy kotów                            | Test zakończony sukcesem                                                                                                |
| `TEST-003`          | PASS   | Zmiana strony na poprzednią/następną                                                   | Test zakończony sukcesem                                                                                                |
| `TEST-004`        | PASS   | Przekierowanie do strony z pierwszym pytaniem                                           | Test zakończony sukcesem                                                                                                |
| `TEST-005`            | PASS   | Przekierowanie do strony z pierwszym pytaniem                                           | Test zakończony sukcesem                                                                                                |
| `TEST-006`            | PASS   | Ustawiono cechy zwierzęcia jako „niezidentyfikowany”                                   | Test zakończony sukcesem                                                                                                |
| `TEST-007`           | PASS   | Ustawiono liczbę jako 5                                                                 | Test zakończony sukcesem                                                                                                |
| `TEST-008`            | PASS   | Zapisano rasę jako „Mieszaniec”/„Europejska”                                           | Test zakończony sukcesem                                                                                                |
| `TEST-009`            | FAIL   | Szacowany czas pobytu zwierzęcia podany z możliwym błędem wynoszącym 65 dni             | Model wymaga optymalizacji (natura danych nie pozwoliła na osiągnięcie lepszego wyniku bez względu na użyty model)      |
