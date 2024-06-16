# Wprowadzenie do Grafiki Komputerowej

Grafika komputerowa to dziedzina zajmująca się tworzeniem i manipulacją obrazów za pomocą komputerów. Obejmuje zarówno aspekty techniczne (jak renderowanie obrazów), jak i artystyczne (jak tworzenie realistycznych scen).

## Definicje:

- **Modelowanie:** Opis matematyczny kształtu i wyglądu wirtualnych obiektów.
- **Renderowanie:** Proces tworzenia obrazu rastrowego z modelu 3D uwzględniając położenie kamery i perspektywę.
- **Animacja:** Tworzenie wrażenia ruchu przez sekwencyjne zmiany położenia i kształtu obiektów.

## Podstawowe Pojęcia

- **Model Geometryczny:** Opisuje obiekty (np. samochód, drzewo) za pomocą wierzchołków i krawędzi oraz parametrów takich jak odbicie światła.
- **Model Matematyczny:** Opisuje procesy fizyczne lub obliczeniowe (np. jak światło odbija się od powierzchni).

## Historia Grafiki Komputerowej

Rozwój grafiki komputerowej można podzielić na kilka etapów:

- **Lata 50. i 60.:** Powstanie podstawowych technik i algorytmów (np. algorytm rysowania linii Bresenhama).
- **Lata 70.:** Wprowadzenie wyświetlaczy rastrowych, algorytmów cieniowania (Gourauda, Phonga) i teksturowania.
- **Lata 80.:** Rozwój ray-tracingu i GUI (graficznych interfejsów użytkownika) w komputerach osobistych.
- **Lata 90.:** Wykorzystanie grafiki w filmach (Terminator, Jurassic Park) i gry 3D (Quake, Half-Life).
- **Po 2000:** Postęp w kierunku realizmu grafiki gier i rozwój algorytmów AI do tworzenia animacji.

## Podstawowe Metody Renderowania

- **Rasteryzacja:** Proces zamiany modelu 3D na obraz 2D za pomocą siatki pikseli. Jest szybki i idealny do aplikacji real-time (np. gry).
- **Ray Tracing:** Śledzenie promieni światła odbijających się od obiektów. Jest wolniejszy, ale oferuje większy realizm scen.

## Potok Graficzny (Graphics Pipeline)

Potok graficzny można porównać do taśmy produkcyjnej, gdzie różne etapy przetwarzania obrazu są realizowane przez różne jednostki. Składa się z:

1. **Etap aplikacji:** Wykonywany głównie na CPU, może obejmować detekcję kolizji.
2. **Etap przetwarzania geometrii:** Transformacja geometrii z 3D do 2D.
3. **Rasteryzacja:** Zamiana geometrii 2D na fragmenty (piksele).
4. **Etap przetwarzania pikseli:** Cieniowanie i łączenie pikseli.

## Zastosowania Współczesne

Grafika komputerowa znajduje zastosowanie w wielu dziedzinach, takich jak:

- Produkcja filmowa: Efekty specjalne, animacje 3D.
- Gry komputerowe: Real-time ray tracing, physically based rendering.
- Rzeczywistość wirtualna: Urządzenia takie jak Oculus.
- Wizualizacja w naukach: Medycyna, biologia, archeologia.
- Interfejsy człowiek-komputer: Symulatory i edukacja (np. symulatory lotnicze).

### Obraz jako funkcja matematyczna:

**Obraz analogowy:**

Jest to funkcja \( f: \mathbb{R} \times \mathbb{R} \to \mathbb{R} \), co oznacza, że przypisuje każdemu punktowi na płaszczyźnie wartość rzeczywistą. Wyobraź sobie, że każdy punkt w przestrzeni ma przypisaną pewną wartość, jak jasność czy intensywność koloru.

**Obraz cyfrowy:**

Jest to funkcja \( I: \{ (x, y) \in \mathbb{Z} \mid 0 \leq x < N_{cols}, 0 \leq y < N_{rows} \} \to \{ 0, 1, \ldots, 2^a - 1 \} \). Oznacza to, że mamy macierz pikseli, gdzie każdy piksel ma przypisaną wartość z pewnego zakresu, na przykład od 0 do 255 (jeśli głębia koloru wynosi 8 bitów). Każda wartość odpowiada poziomowi jasności lub koloru, które można reprezentować cyfrowo.

W obrazie cyfrowym, \( N_{cols} \) oznacza liczbę kolumn (szerokość obrazu) oraz \( N_{rows} \) liczbę wierszy (wysokość obrazu). Parametr \( a \) jest zazwyczaj liczbą bitów na kanał kolorów, co determinuje ilość możliwych wartości dla każdego piksela. Na przykład, dla 8-bitowej głębi kolorów, \( a = 8 \) i piksel może przyjąć wartości od 0 do 255.

W przypadku obrazu cyfrowego, funkcja \( I \) mapuje każdy punkt obrazu (o współrzędnych całkowitoliczbowych) na konkretną wartość numeryczną, która reprezentuje kolor danego piksela.
