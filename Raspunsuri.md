# Răspunsuri tema 3

## Întrebarea 2
Anti-aliasing este o tehnică folosită pentru a reduce efectele vizuale nedorite cauzate de eșantionarea discretă a obiectelor grafice, cum ar fi marginile zimțate (aliasing). În general, aliasing-ul apare atunci când marginile drepte ale obiectelor sunt reprezentate pe o grilă pixelată, cum ar fi un ecran, și nu se aliniază perfect cu pixelii.
Pentru a reduce acest efect, anti-aliasing-ul funcționează prin suprapozarea mai multor mostre (sampling) pentru fiecare pixel și calcularea unei culori medii. Acest lucru face tranzițiile între obiecte și fundal mai fine și marginile mai netede.

## Întrebarea 3
- GL.LineWidth(float): Această comandă setează grosimea liniilor. De exemplu, dacă GL.LineWidth(2.0) este apelată, toate liniile desenate ulterior vor fi de două ori mai groase decât dimensiunea implicită.

- GL.PointSize(float): Setează dimensiunea punctelor desenate. De exemplu, GL.PointSize(5.0) va face ca toate punctele să aibă diametrul de 5 pixeli.

Ambele comenzi trebuie plasate în afara secțiunilor GL.Begin() pentru a avea efect, deoarece setările generale de stil se aplică înainte de începerea desenării unui obiect. Ele afectează toate obiectele care sunt desenate ulterior până când sunt setate noi dimensiuni pentru linii sau puncte.

## Întrebarea 4
- LineLoop: Desenează o serie de linii conectate între vertexuri, iar ultimul vertex este conectat înapoi la primul, formând o buclă închisă. Ideal pentru a desena contururi sau forme poligonale.

- LineStrip: Desenează o linie continuă prin conectarea fiecărui vertex la următorul, fără a conecta ultimul vertex la primul. Formează o linie deschisă.

- TriangleFan: Desenează un grup de triunghiuri care împărtășesc un vertex central (primul vertex). Fiecare triunghi este creat cu un nou vertex și primele două vertexuri ale triunghiului anterior. Util pentru desenarea de forme circulare sau discuri.

- TriangleStrip: Desenează o serie de triunghiuri conectate, unde fiecare triunghi după primul este format din două vertexuri ale triunghiului anterior și un vertex nou. Această metodă este eficientă pentru a desena suprafețe complexe cu puține vertexuri.

## Întrebarea 6
Utilizarea de culori diferite pe un obiect 3D, fie prin gradient, fie prin selectarea culorilor pentru fiecare față, ajută la îmbunătățirea percepției adâncimii și a detaliilor obiectului. Un obiect cu o singură culoare poate părea plat și greu de distins. În schimb, variațiile de culoare fac ca obiectul să fie mai realist, subliniind formele și contururile sale.

Avantajele includ:

- Adâncime vizuală: Culorile mai deschise sau mai închise pot sugera iluminarea sau umbrirea suprafeței, oferind o iluzie de tridimensionalitate.
- Îmbunătățirea esteticii: Face obiectele mai atractive și mai ușor de diferențiat.
- Realism: Utilizarea culorilor sau texturilor variate face ca obiectele să arate mai naturale.

## Întrebarea 7
Un gradient de culoare este o tranziție treptată între două sau mai multe culori. Acest efect este utilizat frecvent pentru a crea tranziții netede între culori și poate fi aplicat atât la obiecte 2D cât și 3D pentru a simula efecte de lumină sau texturi mai complexe.

În OpenGL, se poate obține un gradient de culoare aplicând culori diferite pentru fiecare vertex folosind glColor() înainte de a specifica vertexurile. OpenGL va interpola automat culorile între vertexuri, rezultând un gradient pe suprafața obiectului.

## Întrebarea 10
Când se aplică o culoare diferită fiecărui vertex într-o linie sau un triunghi desenat în modul strip (de exemplu, TriangleStrip sau LineStrip), OpenGL va interpola culorile între vertexuri. Acest proces de interpolare rezultă într-un efect de gradient pe segmentele respective.

Pentru linii, fiecare segment de linie dintre două vertexuri va avea o tranziție graduală între cele două culori definite la fiecare capăt al segmentului.

Pentru triunghiuri, se va crea un gradient de culoare pe întreaga suprafață a triunghiului, ceea ce poate ajuta la simularea iluminării sau texturilor pe obiecte complexe.