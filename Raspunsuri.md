## Problema 1
Dacă este modificată constanta MatrixMode.Projection, proiectarea corectă a scenei 3D nu mai are loc, ceea ce duce la o afișare incorectă a obiectelor pe ecran.

## Problema 3
1. Ce este un viewport?

Un viewport este o zonă dreptunghiulară din fereastra de afișare în care sunt desenate obiectele OpenGL. Practic, el definește porțiunea din fereastră unde vor fi mapate coordonatele din scena 3D (coordonatele normalizate). Setarea unui viewport se face cu funcția glViewport(x, y, width, height), unde x și y definesc colțul din stânga jos, iar width și height specifică dimensiunile dreptunghiului de afișare.

2. Ce reprezintă conceptul de frames per second (FPS) din punctul de vedere al bibliotecii OpenGL?

În OpenGL, frames per second (FPS) reprezintă numărul de cadre pe secundă care sunt desenate și afișate pe ecran de către aplicație. Un FPS mai mare indică o performanță mai bună și o animație mai fluidă. FPS este calculat ca raportul dintre numărul de cadre renderizate și timpul total de execuție. Bibliotecile OpenGL permit controlul vitezei de randare pentru a ajusta performanța și fluiditatea graficii, ceea ce este important în aplicațiile interactive.

3. Când este rulată metoda OnUpdateFrame()?

Metoda OnUpdateFrame() este apelată înainte de randarea fiecărui cadru, având rolul de a actualiza starea logică a aplicației (de exemplu, poziția obiectelor, animațiile sau interacțiunile cu utilizatorul). Aceasta se ocupă de logica de calcul și procesare necesară pentru a pregăti scena înainte de randare.

4. Ce este modul imediat de randare?

Modul imediat de randare este o metodă de randare disponibilă în versiunile mai vechi de OpenGL, în care fiecare punct, linie sau poligon era desenat imediat ce era specificat prin funcții. În acest mod, datele geometrice erau trimise la GPU cadru cu cadru, ceea ce făcea ca această metodă să fie mai puțin eficientă decât tehnicile moderne bazate pe „vertex buffers” (VBOs) sau „vertex array objects” (VAOs).

5. Care este ultima versiune de OpenGL care acceptă modul imediat?

Ultima versiune de OpenGL care acceptă modul imediat este OpenGL 3.2, în care modul imediat a devenit depășit (deprecated). Începând cu OpenGL 3.3 și versiunile superioare, acest mod nu mai este suportat oficial și a fost înlocuit de metodele moderne de randare (ex. VBO, VAO).

6. Când este rulată metoda OnRenderFrame()?

Metoda OnRenderFrame() este rulată atunci când un nou cadru este gata să fie desenat pe ecran. Aceasta este responsabilă de efectivul proces de randare a scenei, inclusiv desenarea obiectelor și aplicarea eventualelor efecte vizuale. Ea este executată de fiecare dată când este nevoie să se actualizeze conținutul afișat în fereastră.

7. De ce este nevoie ca metoda OnResize() să fie executată cel puțin o dată?

Metoda OnResize() trebuie executată cel puțin o dată pentru a ajusta corect viewport-ul și matrițele de proiecție în funcție de dimensiunea actuală a ferestrei de afișare. Această metodă recalibrează proiecția scenei 3D astfel încât să se potrivească cu dimensiunea și proporțiile ferestrei, asigurându-se că imaginea afișată nu este distorsionată sau decupată.

8. Ce reprezintă parametrii metodei CreatePerspectiveFieldOfView() și care este domeniul de valori pentru aceștia?

Metoda CreatePerspectiveFieldOfView() este folosită pentru a seta o proiecție în perspectivă pentru o scenă 3D, utilizând următorii parametri:

- fieldOfViewY: unghiul de vedere pe verticală (în radiani), reprezentând cât de „larg” este câmpul vizual. Domeniul tipic de valori este între 45 și 90 de grade (aproximativ 0.785 radiani - 1.57 radiani).
- aspectRatio: raportul dintre lățimea și înălțimea ferestrei de vizualizare. Valoarea acestuia trebuie să fie un număr pozitiv.
- znear: distanța până la planul apropiat de tăiere (near clipping plane). Această valoare trebuie să fie un număr pozitiv, foarte aproape de 0 (de exemplu, 0.1).
- zfar: distanța până la planul îndepărtat de tăiere (far clipping plane). Valoarea trebuie să fie un număr pozitiv, mai mare decât znear.

Acești parametri controlează cum este proiectată scena 3D pe ecran, determinând zona vizibilă din spațiul 3D și modul în care sunt percepute distanțele între obiecte.
