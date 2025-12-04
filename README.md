# Projekt_Analiza_danych_z_R

Projekt zespołowy - Analiza Danych z R 2025/2026

# Wstęp
Niniejszy dokument opisuje projekt zespołowy dotyczący analizy danych przy użycia języka R.
Celem tego projektu jest przeprowadzenie kompleksowej analizy danych przy użyciu języka R. Projekt obejmuje zbieranie, przetwarzanie, analizę oraz wizualizację danych.
Dane do analizy pozyskano ze strony:https://www.kaggle.com/datasets/bartoszpieniak/poland-cars-for-sale-dataset.

Struktura zespołu
- Paweł Cyrocki (leader)
- Patryk Siuda
- Damian Skinder

Etapy projektu
1. Zbieranie danych
2. Porządkowanie danych
3. Analiza danych
4. Wizualizacja danych
5. Prezentacja wyników

# 1. Opis zmiennych
Zbiór danych zawiera 208 304 obserwacje oraz 25 zmiennych.
Opis zmiennych:
1.	ID - unikalny identyfikator oferty
2.	Cena - wartość ceny
3.	Waluta - waluta, w której podawana jest cena (najczęściej polski złoty, ale także niektóre euro)
4.	Stan - nowy lub używany
5.	Vehicle_brand - marka pojazdu w ofercie
6.	Vehicle_model - model pojazdu w ofercie
7.	Vehicle_generation - generacja pojazdu w ofercie
8.	Vehicle_version - wersja pojazdu w ofercie
9.	Production_year - rok produkcji samochodu
10.	Mileage_km - całkowity dystans, jaki samochód przebył w kilometrach
11.	Power_HP - moc silnika samochodu w koni mechanicznych
12.	Displacement_cm3 - pojemność silnika samochodu w centymetrach sześciennych
13.	Fuel_type - rodzaj paliwa samochodowego
14.	CO2_emissions - emisja CO2 z samochodów w g/km
15.	Drive - rodzaj napędu samochodu
16.	Skrzynia biegów - rodzaj skrzyni biegów samochodowych
17.	Typ - styl nadwozia samochodu
18.	Doors_number - ilość drzwi samochodowych
19.	Kolor - kolor karoserii
20.	Origin_country - kraj pochodzenia samochodu
21.	First_owner - czy właściciel jest pierwszym właścicielem
22.	First_registration_date - data pierwszej rejestracji
23.	Offer_publication_date - data publikacji oferty
24.	Offer_location - adres podany przez wystawcę
25.	Cechy - wymienione cechy samochodu (ABS, poduszka powietrzna, czujniki parkowania itp.)

# 2. Porządkowanie danych

W tym etapie dokanano sprawdzenia braków w danych oraz ich walidacji.

## 2.1. Braki danych

Etap ten objął sprawdzenie braków w danych. Na tej podstawie usunięto zmienną CO2_emissions ze względu na zbyt dużą liczbę braków danych.
Po usunięciu braków danych wyznaczono korelację między zmiennymi. Następnie dokonano wypełnienia braków w zmiennych numerycznych, po czym zaimputowano dane za pomocą metody MICE.

## 2.2. Walidacja danych

Dane zostały poddane procesowi walidacji w celu zapewnienia ich jakości i spójności.

Reguły walidacji danych brzmią następująco:

1. Price (cena) - musi być liczbą dodatnią.
2. Mileage_km (przebieg) - musi być liczbą nieujemną.
3. Production_year (rok produkcji) - musi być liczbą całkowitą mieszczącą się w rozsądnym zakresie (np. 1900-2025).
4. Power_HP (moc silnika) - musi być liczbą nieujemną.
5. Displacement_cm3 (pojemność silnika) - musi być liczbą nieujemną.
6. Doors_number (liczba  drzwi) - musi być liczbą całkowitą z przedziału (3-7)