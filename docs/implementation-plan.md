# Plan de implementare

## Justificarea tehnologiilor

**Angular si TypeScript:** permit organizarea interfetei in componente reutilizabile, separarea paginilor prin rutare, construirea formularelor si comunicarea HTTP cu API-ul. Tipurile explicite ajuta la mentinerea structurilor de date comune interfetei.

**FastAPI si Python:** permit definirea operatiilor API si validarea datelor prin scheme. Documentatia OpenAPI generata faciliteaza verificarea contractelor si integrarea cu frontend-ul. Backend-ul concentreaza autorizarea si regulile de business.

**PostgreSQL:** este gratuita, open-source si este potrivita pentru relatiile dintre utilizatori, organizatii, activitati si inscrieri. Cheile straine, constrangerile si tranzactiile sustin integritatea datelor.

**Git si GitHub:** asigura istoricul modificarilor, colaborarea si urmarirea contributiilor individuale.

## Strategia de versionare

- `main` pastreaza versiunea stabila.
- Fiecare functionalitate este dezvoltata pe un branch, de exemplu `feature/event-registration`.
- Commiturile descriu concret modificarile si sunt facute pe masura progresului.
- Integrarea se realizeaza prin pull request.
- Documentatia se actualizeaza impreuna cu modificarile de model, API sau comportament.
- Secretele si configuratiile locale sensibile sunt excluse prin `.gitignore`; exemplele de configurare nu contin valori reale.

## Plan de implementare

| Perioada | Activitati | Dependente | Rezultat verificabil |
|---|---|---|---|
| Saptamana 8 | Configurarea proiectelor, schema bazei de date si date demonstrative | Modelul preliminar | Angular si FastAPI pornesc; backend-ul poate citi/scrie in baza de date. |
| Saptamana 8 | Autentificare, roluri si structura navigarii | Configurare si utilizatori | Login functional si blocarea operatiilor nepermise. |
| Saptamana 9 | Creare, consultare si filtrare activitati | Baza de date si autorizare | Activitatea publicata este salvata si afisata in lista. |
| Saptamana 9 | Inscriere, lista proprie si retragere | Activitati si autentificare | Inscriere persistenta, prevenirea duplicatelor si eliberarea corecta a locului. |
| Saptamana 10 | Integrare, verificari si corectii | Fluxul principal | Un flux complet functioneaza din interfata pana la baza de date. |
| Saptamana 10 | README de rulare, date de demonstratie si pregatirea prezentarii | Prototip integrat | Aplicatia poate fi pornita si demonstrata reproductibil. |

## Prioritizarea activitatilor

Prioritate au configurarea bazei de date, autentificarea si functionalitatile necesare fluxului principal: crearea si afisarea activitatilor, inscrierea voluntarilor si retragerea inscrierilor. Frontend-ul si backend-ul vor fi dezvoltate in paralel si integrate treptat. Dupa stabilizarea acestui flux, vor fi implementate evidenta prezentei, importul/exportul CSV si moderarea. Testarea si corectarea erorilor vor avea loc pe tot parcursul dezvoltarii.

## Repartizarea responsabilitatilor

| Membru | Grupa | Componente si sarcini asumate |
|---|---|---|
| Unguroiu Petre-Mihai | 8 | Backend: implementarea API-ului in FastAPI, configurarea bazei de date PostgreSQL, autentificarea si autorizarea pe roluri, gestionarea activitatilor si inscrierilor, validarea datelor, evidenta prezentei, importul/exportul CSV si operatiile de moderare. |
| Jderu Darius | 4 | Frontend: implementarea interfetei in Angular, navigarea intre pagini, formularele de autentificare si creare a activitatilor, lista si filtrele activitatilor, gestionarea inscrierilor din interfata, paginile pentru prezenta si moderare, importul/exportul CSV din interfata si integrarea cu API-ul. |
