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

# Hipotezy badawcze

W projekcie analizujemy zależności między ceną samochodu a jego cechami technicznymi i dodatkowymi. Zdefiniowano następujące hipotezy badawcze:

H1: Samochody z większym przebiegiem mają istotnie niższą cenę niż samochody z niższym przebiegiem.
H2: Nowsze samochody (z wyższym rokiem produkcji) są istotnie droższe niż starsze samochody.
H3: Cena samochodu zależy od typu nadwozia; SUV-y i crossovery są średnio droższe niż hatchbacki i sedany.
H4: Samochody z automatyczną skrzynią biegów są średnio droższe niż samochody z manualną skrzynią biegów.
H5: Samochody od pierwszego właściciela (First_owner = tak) osiągają istotnie wyższą cenę (Price) niż samochody, które miały więcej niż jednego właściciela.
H6: Samochody z napędem na cztery koła (4x4) są średnio droższe niż samochody z napędem na jedną oś, przy porównywalnych pozostałych parametrach.
H7: Wyższa moc silnika wiąże się z wyższą ceną samochodu, nawet po uwzględnieniu przebiegu i roku produkcji.
H8: Samochody hybrydowe i elektryczne są istotnie droższe niż samochody benzynowe i z silnikiem Diesla, przy porównywalnym przebiegu i roczniku
H9: Samochody w popularnych kolorach siągają istotnie wyższe ceny niż samochody w kolorach mniej typowych.
H10: Dla samochodów starszych niż 10 lat wskaźnik „cena na km” różni się istotnie między analizowanymi grupami aut w tej kategorii wieku.
H11: W regionach (województwach) o wyższej średniej cenie ofert średnia moc silnika jest istotnie wyższa niż w regionach o niższej średniej cenie.


#Etapy projektu
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
6. Doors_number (liczba  drzwi) - musi być liczbą całkowitą z przedziału (1-6)