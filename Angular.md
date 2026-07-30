# 📗 Angular Kompendium

# Indholdsfortegnelse

- [Del 1 – Introduktion](#del-1--introduktion)
  - [Angular](#angular)
  - [TypeScript](#typescript)
  - [Angular CLI](#angular-cli)
  - [Projektstruktur](#projektstruktur)



---

## Del 2 – Components

```ts
@Component(...)
```

* Template
* Styles
* Selector

---

## Del 3 – Templates

Interpolation

```html
{{ user.name }}
```

Property Binding

```html
[src]="image"
```

Event Binding

```html
(click)="save()"
```

Two-way Binding

```html
[(ngModel)]
```

---

## Del 4 – Directives

* ngIf
* ngFor
* ngSwitch
* Custom Directives

---

## Del 5 – Services

```ts
@Injectable()
```

Singleton Services

Dependency Injection

---

## Del 6 – Routing

* Routes
* Lazy Loading
* Guards
* Resolver

---

## Del 7 – Forms

Template Forms

Reactive Forms

Validation

---

## Del 8 – RxJS

* Observable
* Subject
* BehaviorSubject
* pipe()
* map()
* switchMap()
* mergeMap()
* tap()
* filter()

---

## Del 9 – HTTP

HttpClient

Interceptors

JWT

---

## Del 10 – Signals

* signal()
* computed()
* effect()

(Nye Angular-versioner)

---

## Del 11 – State Management

* Services
* Signals
* NgRx (introduktion)

---

## Del 12 – Deployment

Build

Environment

Docker



---

[Indholdsfortegnelse](#Indholdsfortegnelse)

---
# Del 1 – Introduktion

## Angular

Angular er et **frontend-framework**, udviklet af Google, som bruges til at bygge moderne webapplikationer (Single Page Applications - SPA).

I modsætning til almindelige hjemmesider, hvor hele siden genindlæses ved hvert klik, opdaterer Angular kun de dele af siden, der ændrer sig. Det giver en hurtigere og mere flydende brugeroplevelse.

Angular bygger på en række centrale principper:

* **Komponentbaseret arkitektur** – applikationen opdeles i små genanvendelige komponenter.
* **TypeScript** – al kode skrives som udgangspunkt i TypeScript.
* **Data Binding** – automatisk synkronisering mellem brugerfladen og data.
* **Dependency Injection (DI)** – Angular håndterer automatisk oprettelse og levering af services.
* **Routing** – navigation mellem forskellige sider uden genindlæsning.
* **RxJS** – håndtering af asynkrone data via Observables.

### Fordele ved Angular

* Struktureret projektopbygning
* Indbygget routing
* Indbygget formularvalidering
* Dependency Injection
* TypeScript giver færre fejl
* Velegnet til store og komplekse applikationer
* Langtidssupport fra Google

### Ulemper

* Stejlere indlæringskurve end React
* Mere "boilerplate"-kode
* Større framework

---

# TypeScript

TypeScript er et programmeringssprog udviklet af Microsoft og er en udvidelse af JavaScript.

Alt gyldigt JavaScript er også gyldigt TypeScript, men TypeScript tilføjer blandt andet:

* Statiske typer
* Interfaces
* Enums
* Klasser
* Generics
* Moderne ES-funktioner

Eksempel:

```typescript
let navn: string = "Kim";
let alder: number = 27;

function hils(navn: string): string {
    return `Hej ${navn}`;
}
```

### Fordele ved TypeScript

* Finder fejl allerede under kompilering
* Bedre IntelliSense
* Mere læsbar kode
* Lettere vedligeholdelse
* Velegnet til store projekter

Angular er bygget oven på TypeScript og bruger sproget som standard.

---

# Angular CLI

CLI står for **Command Line Interface**.

Angular CLI er et værktøj, der automatiserer mange af de opgaver, man normalt selv skulle udføre.

CLI kan blandt andet:

* Oprette nye projekter
* Starte udviklingsserver
* Generere komponenter
* Generere services
* Generere guards
* Generere pipes
* Bygge projektet
* Køre tests

## Installation

Node.js skal være installeret først.

Installer Angular CLI globalt:

```bash
npm install -g @angular/cli
```

Kontroller installationen:

```bash
ng version
```

eller

```bash
ng v
```

---

# Oprettelse af et Angular-projekt

Opret et nyt projekt:

```bash
ng new MitProjekt
```

CLI stiller typisk følgende spørgsmål:

```
Would you like to enable Server-Side Rendering (SSR)?
```

Normalt vælges:

```
No
```

Herefter:

```
Would you like to use zoneless?
```

Normalt:

```
No
```

CSS-præprocessor:

```
CSS
```

Efter projektet er oprettet:

```bash
cd MitProjekt
```

Start udviklingsserveren:

```bash
ng serve
```

eller

```bash
ng serve --open
```

Serveren starter typisk på:

```
http://localhost:4200
```

Hvis port 4200 er optaget:

```bash
ng serve --port 4300
```

---

## Generering af filer

Opret en komponent:

```bash
ng generate component home
```

Kort version:

```bash
ng g c home
```

Opret en service:

```bash
ng g s services/auth
```

Opret en guard:

```bash
ng g guard guards/auth
```

Opret et interface:

```bash
ng g interface models/user
```

Opret en model:

```bash
ng g class models/user
```

---

## Byg projektet

Udviklingsversion:

```bash
ng build
```

Produktionsversion:

```bash
ng build --configuration production
```

Output placeres i:

```
dist/
```

---

# Projektstruktur

Et Angular-projekt består af en række mapper og filer.

```
my-app/
│
├── src/
│   ├── app/
│   ├── assets/
│   ├── environments/
│   ├── styles.css
│   ├── index.html
│   └── main.ts
│
├── public/
├── node_modules/
├── angular.json
├── package.json
├── tsconfig.json
└── package-lock.json
```

---

## app/

Her ligger næsten al den kode, man selv skriver.

Eksempel:

```
app/
│
├── components/
├── pages/
├── services/
├── models/
├── interfaces/
├── guards/
├── interceptors/
├── pipes/
├── directives/
├── shared/
└── app.routes.ts
```

### Components

Indeholder brugergrænsefladen.

Eksempel:

```
login.component.ts
login.component.html
login.component.css
```

---

### Services

Forretningslogik.

Eksempel:

* API-kald
* Login
* Token-håndtering

```typescript
@Injectable({
  providedIn: 'root'
})
export class AuthService { }
```

---

### Models

Klasser, som beskriver data.

```typescript
export class User {

    id!: number;

    name!: string;

}
```

---

### Interfaces

Beskriver strukturen på objekter.

```typescript
export interface User {

    id: number;

    name: string;

}
```

---

### Guards

Beskytter routes.

Eksempel:

```typescript
admin
/login
/profile
```

En guard kan kontrollere:

* Er brugeren logget ind?
* Har brugeren rollen Admin?

---

### Interceptors

Opsnapper alle HTTP-kald.

Bruges ofte til:

* Tilføje JWT-token
* Global fejlbehandling
* Loading-spinner

---

### Pipes

Formatterer data.

Eksempel:

```html
{{ today | date }}
{{ price | currency }}
```

Man kan også lave egne pipes.

---

### Directives

Ændrer HTML-elementers opførsel.

Eksempler:

```html
*ngIf

*ngFor

[ngClass]

[ngStyle]
```

Man kan også udvikle egne directives.

---

### Shared

Genbrugelige komponenter.

Eksempel:

* Navbar
* Footer
* Buttons
* Modal
* Card

---

## assets/

Indeholder statiske filer.

Eksempel:

```
assets/
│
├── images/
├── icons/
├── logo.png
└── pdf/
```

---

## environments/

Indeholder miljøspecifik konfiguration.

Eksempel:

Udvikling:

```
apiUrl = http://localhost:5000
```

Produktion:

```
apiUrl = https://api.minside.dk
```

> **Bemærk:** I nyere Angular-versioner (bl.a. Angular 19 og 20) er `environments`-mappen ikke længere oprettet som standard. Hvis man ønsker miljøspecifikke konfigurationer, skal de oprettes manuelt eller konfigureres via Angular CLI.

---

## main.ts

Applikationens startpunkt.

Her starter Angular hele applikationen.

Eksempel:

```typescript
bootstrapApplication(AppComponent);
```

---

## index.html

Den eneste HTML-fil, browseren indlæser direkte.

Angular indsætter automatisk applikationen i:

```html
<app-root></app-root>
```

---

## styles.css

Globale CSS-regler.

Disse gælder for hele applikationen.

---

## package.json

Beskriver projektets afhængigheder og scripts.

Eksempel:

```json
"scripts": {
  "start": "ng serve",
  "build": "ng build"
}
```

---

## node_modules/

Alle installerede npm-pakker.

Denne mappe oprettes automatisk med:

```bash
npm install
```

Den skal **ikke** versionsstyres i Git.

---

## angular.json

Angular CLI's konfigurationsfil.

Her defineres blandt andet:

* Build-konfiguration
* Assets
* Styles
* Scripts
* Produktionsopsætning

---

## tsconfig.json

TypeScript-konfiguration.

Her angives blandt andet:

* Compiler-indstillinger
* Strict mode
* Målversion af JavaScript
* Modulopløsning

---

### Typisk arbejdsflow

1. Installer Node.js og Angular CLI.
2. Opret et nyt projekt med `ng new`.
3. Gå ind i projektmappen (`cd`).
4. Start udviklingsserveren med `ng serve`.
5. Opret komponenter og services med `ng generate`.
6. Udvikl og test applikationen løbende.
7. Byg en produktionsversion med `ng build --configuration production`.

Denne struktur giver en god adskillelse mellem præsentation (komponenter), logik (services), data (models/interfaces) og konfiguration, hvilket gør Angular velegnet til både små og store applikationer.








---
---





# 📙 React vs Angular

| React                 | Angular                 |
| --------------------- | ----------------------- |
| Bibliotek             | Framework               |
| JavaScript/TypeScript | TypeScript              |
| JSX                   | HTML Templates          |
| useState              | Signals/Component State |
| useEffect             | Lifecycle Hooks         |
| React Router          | Angular Router          |
| Fetch/Axios           | HttpClient              |
| Props                 | @Input                  |
| Callback              | @Output                 |
| Context               | Services                |
| Hooks                 | Dependency Injection    |

---

# Kapitel om arkitektur

Begge kompendier bør have kapitler om:

## Mappestruktur

### React

```text
app/
components/
hooks/
services/
lib/
types/
```

### Angular

```text
app/
components/
pages/
services/
models/
guards/
interceptors/
```

---

## Authentication

* Login
* JWT
* Refresh Token
* HttpOnly Cookie
* Protected Routes
* Route Guards

---

## API

* REST
* CRUD
* Fetch
* Error Handling

---

## Bedste praksis

React

* Små komponenter
* Custom Hooks
* Genbrug
* Memoization

Angular

* Services til forretningslogik
* Standalone Components
* Signals (i nyere Angular)
* Reactive Forms

---


På den måde bliver kompendierne ikke kun teori, men en praktisk guide til at bygge moderne full-stack applikationer med de teknologier, du bruger.
