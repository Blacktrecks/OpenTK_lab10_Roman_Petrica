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
