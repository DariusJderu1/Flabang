# Cerinte si prioritizare

## Niveluri de prioritate

- **P1 - prototip:** necesar pentru fluxul complet demonstrat la etapa 3.
- **P2 - aplicatie finala:** obligatoriu pentru versiunea finala, dupa stabilizarea fluxului principal.
- **P3 - extindere:** functionalitate suplimentara, abordata daca timpul permite.

Prioritatea indica ordinea implementarii

## Cerinte functionale

| Cerinta si criteriu de acceptare | Prioritate |
|---|---|
| Autentificare cu email si parola. Datele valide returneaza un token asociat identitatii si rolului; datele gresite produc 401. | P1 |
| Lista publica afiseaza doar activitati PUBLISHED si permite filtrarea dupa oras, categorie si data. Fiecare rezultat indica locurile disponibile. | P1 |
| Organizer creeaza o activitate asociata organizatiei si unei categorii. Capacitatea trebuie sa fie pozitiva, iar sfarsitul nu poate preceda inceputul. | P1 |
| Volunteer se inscrie la o activitate publicata, viitoare, cu locuri disponibile. O inscriere activa duplicata sau lipsa locurilor produce 409. | P1 |
| Volunteer consulta si retrage doar propriile inscrieri. Retragerea schimba statusul in CANCELLED si elibereaza locul o singura data. | P1 |
| Organizer consulta participantii si marcheaza PRESENT sau ABSENT doar pentru propriile activitati. | P2 |
| Organizer exporta participantii la propria activitate in CSV. | P2 |
| Organizer importa prezenta din CSV cu coloanele email si attendance. Se raporteaza numarul randurilor importate si erorile pe rand. | P2 |
| Admin elimina o activitate prin statusul REMOVED; aceasta dispare din lista publica si nu mai accepta inscrieri. | P2 |
| Organizer modifica, publica sau anuleaza propriile activitati. Publicarea trece activitatea din DRAFT in PUBLISHED; anularea blocheaza inscrierile noi. | P2 |
| Voluntarul poate oferi rating si comentariu pentru propria participare. Regula propusa: cel mult un feedback per inscriere cu prezenta PRESENT. | P3 |

## Cerinte nefunctionale

| Cerinta si verificare | Prioritate |
|---|---|
| Persistenta: dupa reincarcarea paginii si repornirea aplicatiei, datele salvate pot fi recuperate. | P1 |
| Autorizare pe server: lipsa unui token valid blocheaza operatiile protejate; un rol nepotrivit sau accesul la resursele altuia este respins. | P1 |
| Parolele sunt stocate sub forma de hash; parolele, tokenurile si cheile reale nu sunt incluse in Git. | P1 |
| Validare pe server pentru campurile obligatorii, tipuri si reguli de business. Interfata afiseaza mesaje clare si pastreaza datele utile corectarii formularului. | P1 |
| Datele participantilor sunt accesibile doar utilizatorului vizat, organizatorului autorizat si operatiilor administrative permise; lista publica nu expune aceste date. | P1 |
| Sunt folosite interogari parametrizate; continutul utilizatorilor nu este injectat ca HTML nesigur. Se verifica intrari SQL/HTML malitioase. | P1 |
| Ecranele principale sunt utilizabile pe desktop si telefon, fara suprapuneri sau controale inaccesibile. | P2 |
| Formularele au etichete, controalele pot fi accesate cu tastatura, focusul este vizibil, iar mesajele nu sunt comunicate exclusiv prin culoare. | P2 |
| README documenteaza instalarea si rularea; dependentele sunt declarate, iar datele demonstrative nu contin date personale reale. | P1 |

Adaptarea la desktop si telefon si accesibilitatea formularelor sunt luate in considerare din wireframe-uri.
