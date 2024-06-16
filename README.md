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

### Charakterystyka obrazu cyfrowego:

- **Tablica pikseli:** Obraz cyfrowy jest reprezentowany jako zbiór pikseli ułożonych w formie dwuwymiarowej macierzy.

- **Wygodne przechowywanie:** Taka forma reprezentacji umożliwia łatwe przechowywanie, przetwarzanie i wyświetlanie obrazu przy użyciu komputerów i innych urządzeń elektronicznych.

- **Skończona rozdzielczość:** Obraz cyfrowy ma ograniczoną liczbę pikseli, co oznacza, że jego rozdzielczość jest skończona i jest określona przez liczbę kolumn (szerokość) i wierszy (wysokość) w macierzy pikseli.


### Zasada działania wyświetlaczy LCD i LED:

**LCD (Liquid Crystal Display):**
- Używa ciekłych kryształów (c) do modulacji światła.
- Światło przechodzi przez filtr polaryzacyjny (b i f) i jest modulowane przez ciekłe kryształy.

**LED (Light Emitting Diode):**
- Diody LED (2) emitują światło, które jest modulowane przez filtry polaryzacyjne (b i f).

### Układ subpikseli:

Wyświetlacze składają się z pikseli, a każdy piksel może zawierać subpiksele w różnych kolorach (czerwony, zielony, niebieski).

#### Rysunek 2: Sposoby układania subpikseli

1. **Stripe:** Subpiksele ułożone w pionowe paski.
2. **Mosaic:** Subpiksele ułożone w układ mozaikowy.
3. **Delta:** Subpiksele ułożone w układzie delta, przypominającym trójkąty.

Każdy z tych układów subpikseli ma wpływ na jakość i dokładność wyświetlanego obrazu oraz efektywność energetyczną wyświetlacza.


### Bufor Ramki (Frame Buffer)

Bufor ramki to specjalne miejsce w pamięci komputera, używane do przechowywania obrazu przeznaczonego do wyświetlenia na ekranie. Gdy obraz jest gotowy, bufor ramki przesyła go do urządzenia wyjściowego, takiego jak monitor.

### Podwójne Buforowanie (Double Buffering)

**Dlaczego podwójne buforowanie jest potrzebne?**

Bez podwójnego buforowania moglibyśmy doświadczać "migotania" lub "przeskoków" na ekranie. Dzieje się tak, gdy obraz jest aktualizowany bezpośrednio podczas jego wyświetlania, co może prowadzić do widocznych zmian i artefaktów.

**Jak działa podwójne buforowanie?**

1. **Dwa Bufory:**
   - **Bufor Przedni (Front Buffer):** Jest to obraz aktualnie wyświetlany na ekranie.
   - **Bufor Tylny (Back Buffer):** Jest to bufor, w którym aktualnie odbywa się rysowanie nowego obrazu.

2. **Rysowanie obrazu:**
   - Nowy obraz jest rysowany w buforze tylnym, który nie jest jeszcze widoczny na ekranie.

3. **Przełączanie buforów:**
   - Po zakończeniu rysowania, bufory tylny i przedni zamieniają się miejscami.
   - Obraz, który był w buforze tylnym, staje się teraz buforem przednim i jest wyświetlany na ekranie.
   - Poprzedni bufor przedni staje się buforem tylnym, gotowym do kolejnego rysowania nowego obrazu.

**Kroki podwójnego buforowania:**
1. Komputer rysuje obraz w buforze tylnym.
2. Po zakończeniu rysowania, bufory tylny i przedni zamieniają się miejscami.
3. Nowo narysowany obraz jest teraz wyświetlany na ekranie z bufora przedniego.

**Zalety Podwójnego Buforowania:**
- **Brak migotania:** Aktualizacje obrazu są płynne, ponieważ rysowanie odbywa się poza widokiem użytkownika.
- **Płynne animacje:** Dzięki podwójnemu buforowaniu animacje i ruchome obrazy wyglądają płynnie bez widocznych zakłóceń.

### Przykład z Życia Codziennego

Wyobraź sobie, że malujesz obraz na płótnie, a ludzie ciągle patrzą. Trudno jest malować bez pokazywania połowicznych, niedokończonych fragmentów obrazu. Teraz wyobraź sobie, że masz dwa płótna:
- Malujesz na jednym (bufor tylny), podczas gdy drugi (bufor przedni) jest pokazywany ludziom.
- Kiedy skończysz malować, szybko zamieniasz płótna, pokazując gotowy obraz, a ty zaczynasz malować nowy na drugim płótnie.


### Algorytm rysowania linii

#### Cel:
Rysowanie linii między dwoma punktami \( (x0, y0) \) i \( (x1, y1) \) na ekranie, aby linia była jak najbardziej realistyczna.

#### Algorytm Zmiennoprzecinkowy

##### Równanie prostej:
Prosta może być opisana równaniem:
\[ y = m \cdot x + c \]
gdzie:
- \( m \) to nachylenie (slope) linii, obliczane jako:
\[ m = \frac{y1 - y0}{x1 - x0} \]
- \( c \) to punkt przecięcia z osią y.

##### Rysowanie linii:
1. Oblicz nachylenie \( m \).
2. Dla każdego \( x \) od \( x0 \) do \( x1 \):
   - Oblicz odpowiadające \( y \) jako:
     \[ y = m \cdot (x - x0) + y0 \]
   - Zaokrągl \( y \) do najbliższej liczby całkowitej.
   - Narysuj piksel na współrzędnych \( (x, y) \).

##### Przykładowa funkcja w języku Java:

```java
public void drawLine(float x0, float y0, float x1, float y1) {
    // Calculate the slope (nachylenie) of the line
    float m = (y1 - y0) / (x1 - x0);

    // Loop through each x from x0 to x1
    for (float x = x0; x <= x1; x++) {
        // Calculate corresponding y
        float y = m * (x - x0) + y0;

        // Round y to the nearest integer
        int roundedY = Math.round(y);

        // Draw pixel at (x, roundedY)
        drawPixel(Math.round(x), roundedY);
    }
}

// Dummy method to represent drawing a pixel at (x, y)
// In a real implementation, this would interface with a graphics library
public void drawPixel(int x, int y) {
    // Code to draw a pixel at (x, y)
    System.out.println("Drawing pixel at (" + x + ", " + y + ")");
}

### Wyjaśnienie kodu

#### Obliczanie nachylenia:
Nachylenie \( m \) prostej między punktami \( (x0, y0) \) i \( (x1, y1) \) jest obliczane za pomocą wzoru:
\[ m = \frac{y1 - y0}{x1 - x0} \]
Nachylenie \( m \) określa, jak stroma jest linia.

#### Pętla od \( x0 \) do \( x1 \):
Pętla iteruje po każdej wartości \( x \) od \( x0 \) do \( x1 \), aby wyznaczyć odpowiadające wartości \( y \).

#### Obliczanie wartości \( y \):
Każde \( y \) jest obliczane używając równania prostej:
\[ y = m \cdot (x - x0) + y0 \]
gdzie \( x \) jest aktualną wartością w pętli.

#### Zaokrąglanie \( y \) do najbliższej liczby całkowitej:
Ponieważ współrzędne pikseli muszą być liczbami całkowitymi, wartość \( y \) jest zaokrąglana do najbliższej liczby całkowitej za pomocą funkcji:
\[ \text{int roundedY} = \text{Math.round}(y); \]

#### Rysowanie piksela:
Funkcja `drawPixel` reprezentuje rysowanie piksela na współrzędnych \( (x, y) \):
```java
drawPixel(Math.round(x), roundedY);
