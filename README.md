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

Jest to funkcja <img src="https://latex.codecogs.com/svg.image?\bg{white}f:\mathbb{R}\times\mathbb{R}\to\mathbb{R}" title="f:\mathbb{R}\times\mathbb{R}\to\mathbb{R}" />, co oznacza, że przypisuje każdemu punktowi na płaszczyźnie wartość rzeczywistą. Wyobraź sobie, że każdy punkt w przestrzeni ma przypisaną pewną wartość, jak jasność czy intensywność koloru.

**Obraz cyfrowy:**

Jest to funkcja <img src="https://latex.codecogs.com/svg.image?\bg{white}I:{(x,y)\in\mathbb{Z}\mid&space;0\leq&space;x<N_{cols},0\leq&space;y<N_{rows}}\to{0,1,\ldots,2^a-1}" title="I:{(x,y)\in\mathbb{Z}\mid 0\leq x<N_{cols},0\leq y<N_{rows}}\to{0,1,\ldots,2^a-1}" />. Oznacza to, że mamy macierz pikseli, gdzie każdy piksel ma przypisaną wartość z pewnego zakresu, na przykład od 0 do 255 (jeśli głębia koloru wynosi 8 bitów). Każda wartość odpowiada poziomowi jasności lub koloru, które można reprezentować cyfrowo.

W obrazie cyfrowym, <img src="https://latex.codecogs.com/svg.image?\bg{white}N_{cols}" title="N_{cols}" /> oznacza liczbę kolumn (szerokość obrazu) oraz <img src="https://latex.codecogs.com/svg.image?\bg{white}N_{rows}" title="N_{rows}" /> liczbę wierszy (wysokość obrazu). Parametr <img src="https://latex.codecogs.com/svg.image?\bg{white}a&space;" title="a " /> jest zazwyczaj liczbą bitów na kanał kolorów, co determinuje ilość możliwych wartości dla każdego piksela. Na przykład, dla 8-bitowej głębi kolorów, <img src="https://latex.codecogs.com/svg.image?\bg{white}a=8&space;" title="a=8 " /> i piksel może przyjąć wartości od 0 do 255.

W przypadku obrazu cyfrowego, funkcja <img src="https://latex.codecogs.com/svg.image?\bg{white}I{\color{Green}}" title="I{\color{Green}}" /> mapuje każdy punkt obrazu (o współrzędnych całkowitoliczbowych) na konkretną wartość numeryczną, która reprezentuje kolor danego piksela.

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

```

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
```

### Algorytm Bresenhama do rysowania linii

Algorytm Bresenhama jest efektywnym sposobem rysowania linii za pomocą liczb całkowitych. Oto jak działa ten algorytm:

#### Założenia

Rysujemy linię między punktami \( (x0, y0) \) i \( (x1, y1) \).

#### Zmienne sterujące

- \( \Delta x \) i \( \Delta y \): Różnice w współrzędnych x i y między punktami:
  \[ \Delta x = x1 - x0 \]
  \[ \Delta y = y1 - y0 \]

- \( D \): Zmienna decyzyjna, inicjalizowana jako:
  \[ D = 2 \cdot \Delta y - \Delta x \]

#### Główne kroki

1. **Inicjalizacja:**
   - Ustawiamy \( x = x0 \) i \( y = y0 \).

2. **Pętla rysująca:**
   - Iterujemy po każdym \( x \) od \( x0 \) do \( x1 \).
   - Rysujemy piksel na współrzędnych \( (x, y) \).
   - Aktualizujemy \( D \):
     - Jeśli \( D > 0 \), inkrementujemy \( y \) o 1 i aktualizujemy \( D \) o \( 2 \cdot ( \Delta y - \Delta x ) \).
     - W przeciwnym razie, aktualizujemy \( D \) o \( 2 \cdot \Delta y \).

#### Przykładowy kod w języku Java

```java
public void drawLineBresenham(int x0, int y0, int x1, int y1) {
    int dx = x1 - x0;
    int dy = y1 - y0;
    
    int D = 2 * dy - dx;
    int y = y0;

    for (int x = x0; x <= x1; x++) {
        drawPixel(x, y);
        
        if (D > 0) {
            y++;
            D = D - 2 * dx;
        }
        
        D = D + 2 * dy;
    }
}

// Dummy method to represent drawing a pixel at (x, y)
// In a real implementation, this would interface with a graphics library
public void drawPixel(int x, int y) {
    // Code to draw a pixel at (x, y)
    System.out.println("Drawing pixel at (" + x + ", " + y + ")");
}

```

### Inicjalizacja zmiennych:

- `dx` i `dy` reprezentują różnice współrzędnych między punktami końcowymi.
- `D` jest inicjalizowane jako `2 * Δy - Δx`.
- `y` jest początkowo ustawione na `y0`.

### Pętla rysująca:

Pętla iteruje od `x0` do `x1`.
W każdej iteracji jest rysowany piksel na współrzędnych `(x, y)`.
Wartość `D` jest aktualizowana w zależności od warunku sprawdzającego, czy przekroczono pewną wartość.


## Wypełnianie Trójkątów

Wypełnianie trójkątów to proces rysowania wszystkich pikseli wewnątrz trójkąta na ekranie. Jest to kluczowy problem w grafice komputerowej, szczególnie w renderowaniu grafiki 3D.

### Współrzędne Barycentryczne

Współrzędne barycentryczne pozwalają opisać położenie punktu względem wierzchołków trójkąta. Można je zapisać jako kombinację wierzchołków trójkąta:

\[ p = \alpha \cdot a + \beta \cdot b + \gamma \cdot c \]

gdzie \( \alpha + \beta + \gamma = 1 \).

### Definicja

Punkt \( p \) w współrzędnych barycentrycznych można również zapisać jako:

\[ p(\alpha, \beta, \gamma) = \alpha \cdot a + \beta \cdot b + \gamma \cdot c \]

gdzie \( \alpha = 1 - \beta - \gamma \).

### Cechy Współrzędnych Barycentrycznych

- **Punkt wewnątrz trójkąta**: Jeżeli wszystkie współrzędne barycentryczne \( (\alpha, \beta, \gamma) \) należą do przedziału (0, 1), to punkt leży wewnątrz trójkąta.
- **Punkt na boku trójkąta**: Jeżeli jedna współrzędna jest równa zero, a pozostałe należą do przedziału (0, 1), to punkt leży na boku trójkąta.
- **Punkt w wierzchołku trójkąta**: Jeżeli dwie współrzędne są równe zero, a jedna równa 1, to punkt leży w wierzchołku trójkąta.

### Algorytm Wypełniania Trójkątów

1. **Obliczenie współrzędnych barycentrycznych dla każdego piksela**: Dla każdego piksela w obszarze zawierającym trójkąt, obliczamy współrzędne barycentryczne \( (\alpha, \beta, \gamma) \).
2. **Sprawdzenie czy punkt leży wewnątrz trójkąta**: Sprawdzamy, czy obliczone współrzędne barycentryczne należą do odpowiednich przedziałów, aby określić, czy piksel leży wewnątrz trójkąta.
3. **Rysowanie pikseli wewnątrz trójkąta**: Jeżeli współrzędne barycentryczne wskazują, że piksel leży wewnątrz trójkąta, to zamalowujemy ten piksel.

### Przykładowy Kod w Java

Oto przykład funkcji wypełniającej trójkąt za pomocą współrzędnych barycentrycznych w języku Java:

```java

public class TriangleFilling {

    public static void main(String[] args) {
        // Przykładowe wierzchołki trójkąta
        Point a = new Point(0, 0);
        Point b = new Point(10, 0);
        Point c = new Point(5, 10);
        
        // Przykładowe wypełnianie trójkąta
        fillTriangle(a, b, c);
    }
    
    public static void fillTriangle(Point a, Point b, Point c) {
        // Wyznacz granice trójkąta
        int minX = Math.min(a.x, Math.min(b.x, c.x));
        int maxX = Math.max(a.x, Math.max(b.x, c.x));
        int minY = Math.min(a.y, Math.min(b.y, c.y));
        int maxY = Math.max(a.y, Math.max(b.y, c.y));
        
        // Iteracja przez wszystkie piksele w obszarze otaczającym trójkąt
        for (int y = minY; y <= maxY; y++) {
            for (int x = minX; x <= maxX; x++) {
                Point p = new Point(x, y);
                double[] barycentric = computeBarycentric(p, a, b, c);
                
                // Sprawdzanie czy punkt leży wewnątrz trójkąta
                if (barycentric[0] >= 0 && barycentric[0] <= 1 && 
                    barycentric[1] >= 0 && barycentric[1] <= 1 && 
                    barycentric[2] >= 0 && barycentric[2] <= 1) {
                    drawPixel(x, y);
                }
            }
        }
    }
    
    // Obliczanie współrzędnych barycentrycznych
    public static double[] computeBarycentric(Point p, Point a, Point b, Point c) {
        double detT = (b.y - c.y) * (a.x - c.x) + (c.x - b.x) * (a.y - c.y);
        double alpha = ((b.y - c.y) * (p.x - c.x) + (c.x - b.x) * (p.y - c.y)) / detT;
        double beta = ((c.y - a.y) * (p.x - c.x) + (a.x - c.x) * (p.y - c.y)) / detT;
        double gamma = 1.0 - alpha - beta;
        return new double[]{alpha, beta, gamma};
    }
    
    // Rysowanie piksela na ekranie
    public static void drawPixel(int x, int y) {
        // Kod do rysowania piksela w miejscu (x, y)
        System.out.println("Drawing pixel at (" + x + ", " + y + ")");
    }
    
    // Klasa reprezentująca punkt (x, y)
    static class Point {
        int x, y;
        
        Point(int x, int y) {
            this.x = x;
            this.y = y;
        }
    }
}

```

## Obliczanie współrzędnych barycentrycznych

Funkcja `computeBarycentric` oblicza współrzędne barycentryczne punktu `p` względem wierzchołków trójkąta `a`, `b` i `c`.

## Wypełnianie trójkąta

Funkcja `fillTriangle` iteruje przez wszystkie piksele w obszarze otaczającym trójkąt, oblicza współrzędne barycentryczne dla każdego piksela i sprawdza, czy piksel leży wewnątrz trójkąta. Jeżeli współrzędne barycentryczne wskazują, że piksel leży wewnątrz trójkąta, funkcja `drawPixel` rysuje ten piksel.

# Problem Przesłaniających Się Trójkątów i Rozwiązanie za pomocą Testu Z-Bufora

W grafice komputerowej, gdy mamy kilka trójkątów, które rzutowane na płaszczyznę przysłaniają się nawzajem, musimy określić prawidłowy kolor piksela. Aby to zrobić, używamy metody z-bufora. Wyjaśnijmy tę koncepcję w prosty sposób.

## Z-Buffer: Zasady Działania

Z-bufor, znany także jako bufor głębokości, to technika używana do eliminacji powierzchni zasłoniętych. Polega ona na przechowywaniu głębokości (współrzędnej z) każdego piksela renderowanej sceny.

### Krok po kroku:

#### Tworzenie Z-Bufora:

1. Tworzymy bufor, który ma ten sam rozmiar co bufor ramki (czyli przestrzeń, w której renderowany jest obraz). Ten nowy bufor to właśnie z-bufor.
2. Z-bufor nie przechowuje koloru piksela, ale jego głębokość (współrzędną z).
3. Z-bufor inicjujemy maksymalną możliwą wartością współrzędnej z w danej scenie. Na przykład, jeśli renderujemy scenę w 3D, ustawiamy każdą wartość w z-buforze na bardzo dużą wartość, aby początkowo wszystkie piksele były jak najdalej.

#### Rysowanie Trójkątów:

1. Podczas rysowania trójkątów, dla każdego piksela trójkąta obliczamy jego współrzędną z.
2. Sprawdzamy głębokość piksela (jego wartość z) i porównujemy ją z aktualnie przechowywaną wartością z w z-buforze dla tej samej współrzędnej ekranu (x, y).
3. Aktualizujemy Z-Bufor i Bufor Ramki:
   - Jeśli współrzędna z piksela jest mniejsza (piksel jest bliżej kamery) niż wartość w z-buforze, oznacza to, że ten piksel jest widoczny. W takim przypadku aktualizujemy z-bufor o nową wartość z i aktualizujemy bufor ramki o kolor tego piksela.
   - Jeśli współrzędna z piksela jest większa (piksel jest dalej od kamery), ignorujemy ten piksel, ponieważ jest zasłonięty przez inny trójkąt.

### Przykład Ilustracyjny

Wyobraźmy sobie, że renderujemy dwa trójkąty na ekranie. Trójkąt A jest bliżej kamery niż trójkąt B.

#### Inicjalizacja Z-Bufora:

Na początku z-bufor ma maksymalne wartości z, czyli np. 1.0 (zakładając, że wartości z są w zakresie od 0 do 1, gdzie 1 to najdalszy punkt).

#### Rysowanie Trójkąta A:

Dla każdego piksela trójkąta A obliczamy jego współrzędną z. Ponieważ jest to pierwszy rysowany trójkąt, wszystkie jego piksele będą bliżej niż początkowe wartości w z-buforze, więc zaktualizujemy zarówno z-bufor, jak i bufor ramki.

#### Rysowanie Trójkąta B:

Dla każdego piksela trójkąta B również obliczamy jego współrzędną z. Porównujemy współrzędną z każdego piksela trójkąta B z odpowiednią wartością w z-buforze. 
- Jeśli piksel trójkąta B ma współrzędną z większą niż ta w z-buforze (co oznacza, że jest dalej), ignorujemy ten piksel.
- Jeśli piksel trójkąta B ma współrzędną z mniejszą niż ta w z-buforze, aktualizujemy zarówno z-bufor, jak i bufor ramki.

```java

public class ZBuffering {

    public static void main(String[] args) {
        int width = 800;
        int height = 600;
        
        // Bufor ramki
        int[][] frameBuffer = new int[width][height];
        // Bufor głębokości (z-bufor)
        double[][] zBuffer = new double[width][height];
        
        // Inicjalizacja z-bufora maksymalnymi wartościami
        for (int y = 0; y < height; y++) {
            for (int x = 0; x < width; x++) {
                zBuffer[x][y] = Double.POSITIVE_INFINITY;
            }
        }
        
        // Przykładowe trójkąty z różnymi wartościami z
        drawTriangle(frameBuffer, zBuffer, new int[]{100, 150, 200}, new int[]{100, 200, 100}, 0.5);
        drawTriangle(frameBuffer, zBuffer, new int[]{150, 200, 250}, new int[]{150, 250, 150}, 0.3);
    }
    
    public static void drawTriangle(int[][] frameBuffer, double[][] zBuffer, int[] xPoints, int[] yPoints, double zValue) {
        // Zakładamy prostą rasteryzację trójkąta (dla uproszczenia)
        int minX = Math.min(xPoints[0], Math.min(xPoints[1], xPoints[2]));
        int maxX = Math.max(xPoints[0], Math.max(xPoints[1], xPoints[2]));
        int minY = Math.min(yPoints[0], Math.min(yPoints[1], yPoints[2]));
        int maxY = Math.max(yPoints[0], Math.max(yPoints[1], yPoints[2]));
        
        for (int y = minY; y <= maxY; y++) {
            for (int x = minX; x <= maxX; x++) {
                // Zakładamy, że piksel (x, y) należy do trójkąta (sprawdzanie jest pominięte dla uproszczenia)
                if (zValue < zBuffer[x][y]) {
                    zBuffer[x][y] = zValue;
                    frameBuffer[x][y] = getColor();
                }
            }
        }
    }
    
    public static int getColor() {
        // Zakładamy, że zwracamy kolor piksela (np. 0xFFFFFF dla białego)
        return 0xFFFFFF;
    }
}


```

### Inicjalizacja Z-Bufora:

- Ustawiamy wszystkie wartości w z-buforze na `Double.POSITIVE_INFINITY`, co oznacza, że początkowo wszystkie piksele są jak najdalej od kamery.

### Rysowanie Trójkąta:

Funkcja `drawTriangle` przyjmuje bufor ramki, z-bufor oraz współrzędne wierzchołków trójkąta oraz wartość z.
Iterujemy przez wszystkie piksele wewnątrz prostokąta otaczającego trójkąt.
Dla każdego piksela sprawdzamy, czy jego wartość z jest mniejsza niż aktualna wartość w z-buforze.
Jeśli tak, aktualizujemy z-bufor i rysujemy piksel w buforze ramki.


# Rasteryzacja i Jej Etapy: Proste Wyjaśnienie

Rasteryzacja to proces przekształcania trójwymiarowych obiektów na dwuwymiarowy obraz na ekranie. Składa się z kilku etapów: przygotowania danych trójkątów, wypełniania trójkątów, cieniowania pikseli i łączenia danych. Omówmy te etapy w prosty sposób.

## 1. Przygotowanie Danych Trójkątów (Triangle Setup)

W tym etapie generowane są dane potrzebne do wypełniania trójkątów, takie jak równania krawędzi. Ten etap jest nieprogramowalny, co oznacza, że działa na stałych funkcjach sprzętowych (fixed function).

- **Równania krawędzi:** Matematyczne wyrażenia określające granice trójkąta na ekranie.
- **Interpolacja:** Obliczanie, jak wartości takie jak kolor i głębokość zmieniają się wzdłuż krawędzi trójkąta.

## 2. Wypełnianie Trójkątów (Triangle Traversal)

W tym etapie generowane są fragmenty, czyli małe części trójkątów odpowiadające pikselom na ekranie. Obliczane są również interpolowane parametry cieniowania dla każdego fragmentu. Podobnie jak poprzedni etap, ten również jest nieprogramowalny.

- **Fragmenty:** Małe części trójkąta reprezentujące potencjalne piksele na ekranie.
- **Interpolowane parametry:** Parametry takie jak kolor, tekstura i głębokość są interpolowane na podstawie wierzchołków trójkąta.

## 3. Cieniowanie Pikseli (Pixel Shading)

W tym etapie obliczane są kolory pikseli na podstawie interpolowanych danych cieniowania. Etap ten jest wykonywany przez programowalne rdzenie GPU, co oznacza, że można stosować różne techniki, takie jak teksturowanie.

- **Pixel Shading:** Obliczanie koloru dla każdego piksela na podstawie światła, cieni i tekstur.
- **Teksturowanie:** Nakładanie tekstur na powierzchnie trójkątów w celu uzyskania bardziej realistycznego wyglądu.

## 4. Łączenie Danych (Merging)

Ten etap jest odpowiedzialny za obliczanie ostatecznego koloru pikseli na podstawie danych z poszczególnych fragmentów. Obejmuje to test z-bufora, obliczanie przezroczystości i umieszczenie danych w buforze ramki.

- **Test z-bufora:** Określanie, który piksel jest bliżej kamery i powinien być widoczny.
- **Przezroczystość:** Obliczanie efektów przezroczystości dla obiektów częściowo widocznych.
- **Bufor ramki:** Miejsce w pamięci, gdzie przechowywane są ostateczne dane obrazu, które zostaną wyświetlone na ekranie.

### Podsumowanie

- **Przygotowanie Danych Trójkątów:** Ustalanie granic trójkąta i interpolacja wartości.
- **Wypełnianie Trójkątów:** Generowanie fragmentów odpowiadających pikselom.
- **Cieniowanie Pikseli:** Obliczanie kolorów pikseli z zastosowaniem technik cieniowania.
- **Łączenie Danych:** Ostateczne ustalanie kolorów pikseli z uwzględnieniem widoczności i przezroczystości.


# Antialiasing: Zrozumienie i Zastosowanie

Antialiasing to technika stosowana w grafice komputerowej w celu zmniejszenia efektu "schodkowania" na krawędziach obiektów. Schodkowanie, czyli aliasing, jest wynikiem niskiej rozdzielczości i ograniczeń w próbkowaniu sygnałów. Omówmy to zagadnienie krok po kroku, wraz z odpowiednimi terminami i przykładami.

## Cel Antialiasingu

- **Redukcja efektu schodkowania:** Antialiasing wygładza krawędzie obiektów, eliminując widoczne, schodkowe przejścia między pikselami.
- **Realistyczny wygląd krawędzi:** Dzięki antialiasingowi obiekty na ekranie wyglądają bardziej naturalnie i mniej kanciasto.

## Aliasing Sygnału 1D

Aliasing w kontekście sygnałów 1D (jednowymiarowych) występuje, gdy sygnał jest próbkowany zbyt rzadko, co powoduje utratę informacji. Efekty aliasingu mogą powodować, że sygnał o wysokiej częstotliwości staje się nierozróżnialny od sygnału o niskiej częstotliwości.

- **Powód:** Zbyt mała częstotliwość próbkowania.
- **Efekt:** Utrata informacji, sygnał o wysokiej częstotliwości jest nierozróżnialny od sygnału o niskiej częstotliwości.

## Filtracja Sygnału 1D

Filtracja jest techniką stosowaną do eliminacji aliasingu poprzez wygładzanie sygnału. W grafice komputerowej filtracja pomaga w antyaliasingu.

- **Sekwencja wag b[i]:** Na potrzeby filtrowania sygnałów stosuje się sekwencję wag, nazywaną filtrem.
- **Normalizacja wag:** Wagi zazwyczaj są znormalizowane, co oznacza, że ich suma wynosi 1.
- **Symetryczność:** Filtr jest zazwyczaj symetryczny względem środkowego elementu.

## Konwolucja Sygnału z Filtrem (1D)

Konwolucja jest procesem matematycznym używanym do filtracji sygnałów. Przesuwamy okno filtra wzdłuż sygnału, uzyskując filtrowaną próbkę.

- **Filtracja:** Okno filtra przesuwane jest wzdłuż sygnału, aby uzyskać nowe, wygładzone wartości próbek.
- **Próbka filtrowana:** Wartość filtrowanej próbki jest wynikiem kontekstu otoczenia, czyli innych próbek w pobliżu.
- **Formuła konwolucji:** 

(a*b)[i] = ∑_{j=i-r}^{i+r} a[j] * b[i-j]

Jeśli mamy sygnał `a[i]` i filtr `b[i]`, to wartość filtrowana w punkcie `i` zależy od otoczenia sygnału `a` oraz wartości wag filtra `b`.

## Podsumowanie

- **Antialiasing:** Technika wygładzania krawędzi, aby uniknąć schodkowania.
- **Aliasing:** Wynik zbyt rzadkiego próbkowania, powodujący utratę informacji.
- **Filtracja:** Proces wygładzania sygnału za pomocą sekwencji wag, aby zmniejszyć aliasing.
- **Konwolucja:** Metoda matematyczna używana do filtracji sygnałów, biorąca pod uwagę otoczenie każdej próbki.

# Konwolucja sygnału 2D

Konwolucja sygnału 2D jest techniką stosowaną w przetwarzaniu obrazów do filtrowania, wygładzania, wyostrzania i wielu innych operacji. Jest to rozszerzenie konwolucji 1D na dwa wymiary.

## Definicja konwolucji 2D

Konwolucja 2D definiowana jest przez następujące równanie:

(f*h)[i,j] = ∑_k ∑_l f(k,l) * h(i−k,j−l)

- **f**: Obraz (macierz pikseli).
- **h**: Kernel (filtr), czyli mniejsza macierz używana do operacji konwolucji.

## Przykład obliczeń konwolucji 2D

Załóżmy, że mamy obraz **f** i kernel **h**. Obliczenie wartości piksela w wyniku konwolucji w danym punkcie polega na przemnożeniu wartości piksela obrazu przez odpowiednią wartość filtra, a następnie zsumowanie wszystkich tych iloczynów.

Na przykład:

f1 * h9 + f2 * h8 + f3 * h7 +
f4 * h6 + f5 * h5 + f6 * h4 +
f7 * h3 + f8 * h2 + f9 * h1


Wartości z filtra **h** (kernela) są nakładane na wartości piksela z obrazu **f**, a wynik jest sumowany, aby uzyskać końcową wartość piksela.

## Antialiasing

Antialiasing to technika mająca na celu redukcję efektu aliasingu, czyli "schodkowania" na krawędziach obiektów.

## Technika supersampling

Supersampling jest jedną z technik antyaliasingu. Proces ten składa się z dwóch kroków:

1. **Renderowanie obrazu w większej rozdzielczości:**
   Obraz jest renderowany w rozdzielczości wyższej niż docelowa, co pozwala na uzyskanie większej ilości informacji o krawędziach obiektów.

2. **Downsampling:**
   Obraz jest zmniejszany do docelowej rozdzielczości przy użyciu filtra, na przykład filtra pudełkowego (box filter). Proces ten polega na uśrednianiu grup pikseli, aby uzyskać jeden piksel w finalnym obrazie.

## Wada supersamplingu

Główną wadą supersamplingu jest koszt obliczeniowy. Renderowanie obrazu w wyższej rozdzielczości i późniejsze przeskalowanie wymaga znacznie więcej mocy obliczeniowej i pamięci, co może być problematyczne w aplikacjach o wysokich wymaganiach wydajnościowych.

```java

public class Convolution {
    public static int[][] applyConvolution(int[][] image, int[][] kernel) {
        int kernelHeight = kernel.length;
        int kernelWidth = kernel[0].length;
        int imageHeight = image.length;
        int imageWidth = image[0].length;
        int[][] output = new int[imageHeight][imageWidth];

        int kernelCenterX = kernelWidth / 2;
        int kernelCenterY = kernelHeight / 2;

        for (int i = 0; i < imageHeight; i++) {
            for (int j = 0; j < imageWidth; j++) {
                int sum = 0;
                for (int m = 0; m < kernelHeight; m++) {
                    for (int n = 0; n < kernelWidth; n++) {
                        int x = i + (m - kernelCenterY);
                        int y = j + (n - kernelCenterX);
                        if (x >= 0 && x < imageHeight && y >= 0 && y < imageWidth) {
                            sum += image[x][y] * kernel[m][n];
                        }
                    }
                }
                output[i][j] = sum;
            }
        }

        return output;
    }

    public static void main(String[] args) {
        int[][] image = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };

        int[][] kernel = {
            {1, 0, -1},
            {1, 0, -1},
            {1, 0, -1}
        };

        int[][] result = applyConvolution(image, kernel);

        for (int i = 0; i < result.length; i++) {
            for (int j = 0; j < result[0].length; j++) {
                System.out.print(result[i][j] + " ");
            }
            System.out.println();
        }
    }
}


```


