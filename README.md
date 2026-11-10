# Platforma pentru organizarea activitatilor de voluntariat

Proiect pentru disciplina Tehnologii Web, directia P5 - Comunitate, voluntariat si organizatii neguvernamentale.

## Problema abordata

Anunturile, inscrierile si listele de participanti sunt adesea gestionate separat, prin mesaje, retele sociale sau fisiere. Aplicatia le centralizeaza, astfel incat organizatorii sa poata urmari activitatile si locurile disponibile, iar voluntarii sa gaseasca oportunitati si sa isi gestioneze inscrierile.

## Obiective

- Centralizarea activitatilor de voluntariat si a informatiilor organizatiilor.
- Consultarea si filtrarea activitatilor dupa oras, categorie si data.
- Gestionarea inscrierilor fara duplicate active si fara depasirea capacitatii.
- Evidenta participarii si schimbul de date prin CSV.
- Separarea drepturilor de acces intre voluntari, organizatori si administratori.

## Utilizatori vizati

- **Volunteer:** consulta activitati, se inscrie si isi retrage propriile inscrieri.
- **Organizer:** creeaza activitati, gestioneaza prezenta si importa/exporta date pentru propriile activitati.
- **Admin:** modereaza activitatile nepotrivite.
- **Vizitator neautentificat:** consulta lista publica si filtreaza activitatile.

## Echipa si responsabilitati

| Membru | Grupa | Responsabilitati asumate |
|---|---|---|
| Unguroiu Petre-Mihai | 8 | Backend |
| Jderu Darius | 4 | Frontend |

Persoana de contact: Darius Jderu (darius.jderu05@e-uvt.ro)

## Functionalitati propuse

Autentificare cu roluri, creare de activitati, consultare si filtrare, inscriere si retragere, marcarea prezentei, exportul participantilor si importul prezentei in CSV, moderarea activitatilor. Modelul preliminar include si feedback, cu prioritate mai mica.

Domeniul proiectului este gestionarea activitatilor si a participarii. Procesarea platilor si donatiilor nu este inclusa.

## Tehnologii alese

| Componenta | Tehnologie |
|---|---|
| Frontend | Angular si TypeScript |
| Backend | Python si FastAPI |
| Persistenta | Baza de date relationala; PostgreSQL |
| Versionare si colaborare | Git si GitHub |

Justificarile sunt prezentate in [planul de implementare](docs/implementation-plan.md).

## Documentatia proiectului

- [Cerinte functionale si nefunctionale, prioritizate](docs/requirements.md)
- [Scenarii de utilizare](docs/use-cases.md)
- [Wireframe-uri si fluxuri de navigare](docs/wireframes/Wireframe.pdf)
- [Arhitectura aplicatiei](docs/architecture.md)
- [Modelul de date si endpoint-urile principale](docs/data-model.md)
- [Tehnologii, versionare si plan de implementare](docs/implementation-plan.md)
