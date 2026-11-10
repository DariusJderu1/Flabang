# Scenarii de utilizare

## 1. Crearea unei activitati

**Actor:** Organizer. 

**Preconditii:** organizator autentificat; organizatia si categoria exista.

**Pasi:**
1. Organizatorul acceseaza formularul de creare.
2. Completeaza titlul, descrierea, categoria, locatia, intervalul si capacitatea.
3. Trimite formularul prin `POST /api/events`.
4. Backend-ul verifica rolul, organizatia si datele primite.
5. Activitatea este salvata si interfata afiseaza confirmarea.

**Rezultat:** o inregistrare events este asociata organizatiei, categoriei si creatorului. Regula propusa pentru prototip: formularul permite salvarea ca DRAFT sau publicarea ca PUBLISHED.

**Verificare:** la crearea unei activitati PUBLISHED cu capacitate 20, aceasta apare in lista publica cu 20 de locuri disponibile. O activitate DRAFT nu apare in lista publica.

**Alternative/erori:** capacitate 0 sau sfarsit anterior inceputului: 400, fara salvare. Utilizator neautentificat: 401; rol nepermis: 403.

## 2. Inscrierea la o activitate

**Actor:** Volunteer. 

**Preconditii:** voluntar autentificat; activitate PUBLISHED, viitoare, cu cel putin un loc liber; fara inscriere activa a acestui voluntar.

**Pasi:**
1. Voluntarul filtreaza lista activitatilor.
2. Deschide activitatea dorita si solicita inscrierea.
3. Frontend-ul trimite `POST /api/events/{id}/registrations`.
4. Backend-ul verifica disponibilitatea si absenta unei inscrieri active duplicate.
5. Backend-ul salveaza inscrierea REGISTERED, initial cu prezenta PENDING.
6. Interfata afiseaza confirmarea si actualizeaza disponibilitatea.

**Rezultat:** inscrierea leaga voluntarul de activitate si este recuperabila din baza de date.

**Verificare:** o activitate cu 20 de locuri libere ajunge la 19 dupa inscriere. Retrimiterea cererii nu creeaza o a doua inscriere activa si returneaza 409.

**Alternative/erori:** capacitate epuizata: 409; activitate inexistenta: 404; activitate indisponibila: cerere respinsa. La doua cereri simultane pentru ultimul loc, cel mult una reuseste.

## 3. Retragerea unei inscrieri

**Actor:** Volunteer. 

**Preconditii:** voluntar autentificat; exista o inscriere REGISTERED care ii apartine.

**Pasi:**
1. Voluntarul acceseaza propriile inscrieri.
2. Selecteaza inscrierea si confirma retragerea.
3. Frontend-ul trimite `DELETE /api/registrations/{id}`.
4. Backend-ul verifica apartenenta inscrierii.
5. Statusul devine CANCELLED si se completeaza cancelled_at.
6. Interfata afiseaza rezultatul.

**Rezultat:** inregistrarea este pastrata pentru istoric si nu mai ocupa un loc.

**Verificare:** daca erau 19 locuri libere, dupa retragere sunt 20. Repetarea retragerii nu elibereaza un loc suplimentar.

**Alternative/erori:** inscrierea altui voluntar: 403, fara modificari; identificator inexistent: 404.
