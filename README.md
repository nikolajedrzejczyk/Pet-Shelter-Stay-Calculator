# Pet-Shelter-Stay-Calculator
Prediction of shelter pet length of stay using animal data to improve shelter resource and financial management and increase adoption chances. (Przewidywanie długości pobytu zwierząt w schronisku na podstawie danych dotyczących zwierząt dla lepszego zarządzania finansami i zasobami schroniska w celu zwiększenia prawdopodobieństwa adopcji.)

Adres aplikacji: https://inzynieria-oprogramowania-kalkulator-dni.streamlit.app

Projekt stworzony we współpracy w ramach przedmiotu Inżynieria oprogramowania na Uniwersytecie Gdańskim.

---

## Wymagana dokumentacja

### Charakterystyka oprogramowania

**Nazwa skrócona:** *Kalkulator dni*  
**Nazwa pełna:** Kalkulator Przewidywania Długości Pobytu Zwierząt Domowych w Schronisku  
**Krótki opis ze wskazaniem celów:**  
Celem aplikacji *Kalkulator Przewidywania Długości Pobytu Zwierząt Domowych w Schronisku* jest wspieranie schronisk w lepszym zarządzaniu zasobami oraz poprawie opieki nad zwierzętami poprzez analizę kluczowych danych i przewidywanie czasu adopcji. Dzięki temu narzędziu schroniska mogą lepiej planować fundusze, skracać czas oczekiwania na nowe domy oraz zwiększać szanse zwierząt na adopcję.

---

## Prawa autorskie

Autorki: Aleksandra Gomulak, Nikola Jędrzejczyk  
Licencja: GNU GENERAL PUBLIC LICENSE, Version 2  

---

## Specyfikacja wymagań

| identyfikator | nazwa               | opis                                                                                      | priorytet  | kategoria       |
|---------------|---------------------|------------------------------------------------------------------------------------------|------------|-----------------|
| WYM-001       | Wprowadzenie danych | Użytkownik może wprowadzić parametry zwierzęcia, takie jak wiek, waga, płeć, typ rasy.   | Wymagane   | Funkcjonalne    |
| WYM-002       | Rozpoznawanie gatunku | Aplikacja rozpoznaje, czy przesłane zdjęcie przedstawia kota, czy psa, przy użyciu sieci neuronowej. | Wymagane | Funkcjonalne    |
| WYM-003       | Szacowanie czasu pobytu | Aplikacja, na podstawie wprowadzonych parametrów i rozpoznania gatunku, szacuje czas pobytu w schronisku. | Wymagane | Funkcjonalne    |
| WYM-004       | Wizualizacja wyników | Wynik szacowania jest przedstawiany użytkownikowi w formie przejrzystego komunikatu (np. liczba dni). | Przydatne | Funkcjonalne    |
| WYM-005       | Wydajność przetwarzania | Wynik szacowania czasu pobytu zwierzęcia powinien być dostępny w czasie krótszym niż 3 sekundy. | Wymagane | Pozafunkcjonalne |
| WYM-006       | Dokładność klasyfikatora | Klasyfikator czasu pobytu informuje o możliwym błędzie szacowania na podstawie testowych danych adoptowanych zwierząt. | Wymagane | Pozafunkcjonalne |
| WYM-007       | Instrukcja użytkowania | Aplikacja dostarcza instrukcje użytkowania.                                               | Przydatne  | Funkcjonalne    |
| WYM-008       | WebScraping          | Aplikacja automatycznie pobiera zdefiniowane dane ze strony internetowej.                 | Wymagane   | Funkcjonalne    |

---
