# LAB 9
# Utilizarea texturării în OpenGL

## Utilizarea pentru texturare imagini cu transparență și fără. Ce observați?

Atunci când se texturizează imagini cu transparență (canalul alfa), aceasta permite obiectelor texturate să aibă zone semi-transparente. Acest lucru este util pentru obiecte sau texturi care au margini netede sau detalii fine care ar trebui să apară parțial transparente. Este important să setați corespunzător proprietățile de amestecare (blending) pentru a gestiona transparența.

În cazul texturării imaginilor fără transparență, acestea vor fi considerate opace, iar textura va acoperi complet obiectul fără nicio transparență.

## Formate de imagine aplicate în procesul de texturare în OpenGL:

OpenGL suportă o varietate de formate de imagine pentru texturi, inclusiv:
- **RGB:** Folosit pentru texturi color fără canal alfa.
- **RGBA:** Permite texturarea cu informații despre transparență (canal alfa).
- **Sunt suportate și alte formate, cum ar fi formatul comprimat (DXT, ETC), formatul de adâncime, și altele. Utilizarea depinde de cerințele specifice ale aplicației.**

## Modificarea culorii obiectului texturat prin manipularea canalelor RGB:

Modificarea canalelor RGB ale unui obiect texturat afectează culorile texturii. De exemplu, dacă se mărește valoarea canalului roșu (R), textura va deveni mai roșie; dacă se scade, va deveni mai verde.

## Diferențe între scena cu iluminare activată și dezactivată în contextul obiectelor texturate:

**Iluminare activată:**
- Texturile vor reacționa la iluminare, reflectând lumină și umbre în funcție de poziția și intensitatea sursei de lumină.
- Diferitele culori ale obiectului texturat vor fi afectate de iluminare, ceea ce adaugă realism.

**Iluminare dezactivată:**
- Texturile vor fi afișate cu culorile lor originale, fără a fi influențate de sursele de lumină din scenă.
- Imaginea texturată poate să pară mai uniformă și să se bazeze doar pe culorile din textură.

# LAB 10
## - Tema lab 10
## 1.Rolul comenzilor GL.Push() și GL.Pop():

GL.Push() și GL.Pop() sunt comenzi în OpenGL utilizate pentru a gestiona stiva de matrice de transformare.
GL.Push() salvează matricea de transformare curentă pe stivă, permițând modificarea acesteia fără a afecta starea matricei de transformare precedentă.
GL.Pop() elimină matricea de transformare curentă de pe stivă, revenind la starea anterioară.
Aceste comenzi sunt necesare în situații în care se efectuează transformări diferite pentru obiecte diferite sau pentru a păstra o matrice de transformare specifică pentru o anumită parte a scenei.

## 2.Efectul metodelor GL.Rotate(), GL.Translate() și GL.Scale():

GL.Rotate(angle, x, y, z): Rotirea unui obiect în jurul axei specificate.

GL.Rotate(45.0f, 0.0f, 1.0f, 0.0f); // Rotire de 45 de grade în jurul axei Y
GL.Translate(x, y, z): Translatarea unui obiect pe axele specificate.

GL.Translate(2.0f, 0.0f, 0.0f); // Translatare de 2 unități pe axa X
GL.Scale(x, y, z): Scalarea unui obiect pe axele specificate.

GL.Scale(2.0f, 1.0f, 1.0f); // Scalare dublă pe axa X
Aceste transformări pot fi combinate pentru a obține o varietate de efecte asupra obiectelor în scenă. De exemplu, pentru a crea o cutie rotită și mărită, poți folosi:

GL.Push();
GL.Rotate(45.0f, 0.0f, 1.0f, 0.0f); // Rotire de 45 de grade în jurul axei Y
GL.Scale(2.0f, 1.0f, 1.0f); // Scalare dublă pe axa X
// Desenează cutia aici
GL.Pop();

## 3.Nivele de manipulări ierarhice:

Numărul de nivele suportate depinde de implementarea specifică și de resursele hardware disponibile. În general, majoritatea implementărilor OpenGL suportă un număr semnificativ de nivele de manipulare ierarhică (Push/Pop). Cu toate acestea, nu există o limită strictă specificată în specificațiile OpenGL.
Este important să gestionezi cu atenție Push/Pop pentru a evita depășirea stivei, iar o practică bună este să echilibrezi fiecare apel Push cu un apel corespunzător Pop.
