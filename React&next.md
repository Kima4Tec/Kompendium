# 📘 React & Next.js Kompendium

## Del 1 – Introduktion

* Hvad er React?
* Hvad er et bibliotek?
* SPA vs MPA
* Virtual DOM
* React DOM

---

## Del 2 – JSX

```jsx
function App() {
  return <h1>Hello World</h1>;
}
```

* JSX
* Expressions
* Fragments
* Conditional Rendering
* Lister

---

## Del 3 – Components

* Functional Components
* Props
* Children
* Composition
* Genbrug

---

## Del 4 – State

* useState()

```jsx
const [count, setCount] = useState(0);
```

* Immutable state
* Opdatering af objekter
* Arrays

---

## Del 5 – Events

```jsx
<button onClick={handleClick}>
```

* onClick
* onChange
* onSubmit
* Event objects

---

## Del 6 – Forms

* Controlled Components
* Uncontrolled Components
* Validation

---

## Del 7 – useEffect

* Livscyklus
* Dependency Array
* Cleanup

---

## Del 8 – Hooks

* useState
* useEffect
* useMemo
* useCallback
* useRef
* useContext
* Custom Hooks

---

## Del 9 – Routing

React Router

eller

Next.js App Router

* layout.tsx
* page.tsx
* loading.tsx
* error.tsx
* not-found.tsx

---

## Del 10 – API

Fetch

Axios

Server Components

Client Components

---

## Del 11 – Authentication

JWT

Cookies

NextAuth (kort)

Refresh Token

---

## Del 12 – Performance

Memo

Lazy Loading

Suspense

---

## Del 13 – Deployment

Vercel

Docker


Det er en rigtig god idé at starte React-delen med disse emner. De bygger oven på hinanden og giver en god introduktion, inden du begynder at skrive komponenter.

---

# Del 1 – Introduktion

## Hvad er React?

**React** er et **JavaScript-bibliotek** udviklet af Meta (Facebook) til at bygge brugergrænseflader (User Interfaces - UI).

I stedet for at skrive hele hjemmesiden som én stor HTML-side opdeles den i små genbrugelige **komponenter**.

Eksempel:

En webshop kan opdeles i:

* Navbar
* Produktkort
* Søgefelt
* Kurv
* Footer

Hver del er sin egen React-komponent.

Fordele:

* Genbrug af kode
* Nemmere vedligeholdelse
* Hurtigere udvikling
* Dynamiske brugergrænseflader

React bruges blandt andet af:

* Facebook
* Instagram
* Netflix
* Airbnb
* Discord

---

## Hvad er et bibliotek?

React er **ikke et framework**.

Det er et **JavaScript-bibliotek**.

Et bibliotek hjælper med én bestemt opgave.

I Reacts tilfælde:

> At bygge brugergrænseflader.

Et framework styrer derimod hele applikationen.

Eksempler:

| Bibliotek | Framework    |
| --------- | ------------ |
| React     | Angular      |
| jQuery    | ASP.NET Core |
| Lodash    | Django       |
| Axios     | Laravel      |

### React

React bestemmer kun, hvordan UI'et bygges.

Du vælger selv:

* Routing
* State management
* HTTP-klient
* Formularer
* osv.

Eksempel:

* React Router
* Axios
* Redux
* Zustand
* TanStack Query

### Angular

Angular kommer med næsten alt indbygget:

* Routing
* HTTP Client
* Formularer
* Dependency Injection
* CLI
* Guards
* Services

Derfor kaldes Angular et **framework**.

---

## SPA vs MPA

Der findes to måder at bygge websites på.

### MPA (Multi Page Application)

Ved en MPA henter browseren en helt ny side fra serveren hver gang brugeren klikker på et link.

Eksempel:

```
Forside
   ↓
Server
   ↓
Ny HTML-side

Produkter
   ↓
Server
   ↓
Ny HTML-side
```

Fordele

* Simpel struktur
* God SEO
* Mindre JavaScript

Ulemper

* Langsommere navigation
* Hele siden genindlæses

---

### SPA (Single Page Application)

En SPA loader kun én HTML-side.

Derefter skifter React kun de dele af siden, der ændrer sig.

Eksempel:

```
App loader én gang

↓

Bruger klikker

↓

Kun indholdet opdateres
```

Fordele

* Hurtig navigation
* Flydende oplevelse
* Mindre datatrafik

Ulemper

* SEO kræver ekstra arbejde
* Første indlæsning kan være større

---

## React og Next.js

React bruges ofte til at bygge **SPA'er**, hvor alt kører i browseren.

**Next.js** bygger oven på React og kan både lave:

* SPA
* Server Side Rendering (SSR)
* Static Site Generation (SSG)
* Hybrid-løsninger

Derfor bruges Next.js ofte til hjemmesider, webshops og større webapplikationer, hvor man ønsker bedre SEO og hurtigere første indlæsning.

---

## Virtual DOM

En af Reacts største styrker er **Virtual DOM**.

Normalt ser processen sådan ud:

```
Data ændres

↓

Browser ændrer HTML

↓

Browser tegner siden igen
```

Dette kan være langsomt.

React bruger derfor en **Virtual DOM**.

Virtual DOM er en kopi af den rigtige DOM, som ligger i hukommelsen.

Når data ændrer sig:

1. React laver en ny Virtual DOM.
2. React sammenligner den med den gamle (diffing).
3. React finder kun de elementer, der har ændret sig.
4. Kun disse elementer opdateres i browserens DOM.

Eksempel:

Før:

```
Navn: Kim
Alder: 25
```

Efter:

```
Navn: Kim
Alder: 26
```

Kun alderen opdateres.

Ikke hele siden.

Fordele:

* Hurtigere rendering
* Færre DOM-opdateringer
* Bedre performance

---

## React DOM

React består faktisk af flere pakker.

Den vigtigste er:

```
react
```

Denne indeholder selve React.

Når React skal vise noget i browseren bruges:

```
react-dom
```

React DOM er forbindelsen mellem React og browserens HTML-side.

Eksempel:

```tsx
import { createRoot } from "react-dom/client";
import App from "./App";

createRoot(document.getElementById("root")!).render(
  <App />
);
```

Her sker følgende:

1. Browseren finder elementet med id `root`.
2. React opretter en "root".
3. React viser komponenten `App`.
4. React DOM sørger for at opdatere HTML'en, når data ændrer sig.

---

# Opstart af et React-projekt (Vite)

Den mest almindelige måde at starte et nyt React-projekt på i dag er med **Vite**, som er hurtigere end den ældre Create React App.

### 1. Opret projekt

```bash
npm create vite@latest mit-react-projekt
```

### 2. Vælg

```
Framework:
React

Variant:
TypeScript
```

### 3. Gå ind i mappen

```bash
cd mit-react-projekt
```

### 4. Installer afhængigheder

```bash
npm install
```

### 5. Start udviklingsserveren

```bash
npm run dev
```

Du vil typisk få en adresse som:

```
http://localhost:5173
```

Projektet åbnes automatisk i browseren, eller du kan selv besøge adressen.

---

# Opstart af et Next.js-projekt

Next.js er et React-framework, der gør det nemt at bygge komplette webapplikationer med blandt andet routing, server-side rendering og API-routes.

### 1. Opret projekt

```bash
npx create-next-app@latest mit-next-projekt
```

### 2. Under installationen bliver du typisk spurgt om:

```
✔ Would you like to use TypeScript? Yes
✔ Would you like to use ESLint? Yes
✔ Would you like to use Tailwind CSS? Yes
✔ Would you like your code inside a src/ directory? Yes (valgfrit)
✔ Would you like to use App Router? Yes
✔ Would you like to use Turbopack? Yes
✔ Would you like to customize the import alias? No
```

### 3. Gå ind i projektmappen

```bash
cd mit-next-projekt
```

### 4. Start udviklingsserveren

```bash
npm run dev
```

Applikationen kan derefter åbnes på:

```
http://localhost:3000
```

---

# Kort opsummering

| Emne         | React                                | Next.js                                  |
| ------------ | ------------------------------------ | ---------------------------------------- |
| Hvad er det? | JavaScript-bibliotek til UI          | React-framework                          |
| Routing      | Eksternt bibliotek (fx React Router) | Indbygget filbaseret routing             |
| Rendering    | Primært Client-Side Rendering (CSR)  | CSR, SSR, SSG og ISR                     |
| SEO          | Kræver ekstra arbejde                | Meget god understøttelse                 |
| Typisk brug  | SPA'er og dashboards                 | Webapps, webshops og offentlige websites |

> **Tænk på React som et bibliotek, der fokuserer på UI, mens Next.js spiller en rolle, der minder mere om Angular som en komplet platform. Angular er stadig et mere omfattende framework med mange funktioner indbygget, mens Next.js bygger oven på React og samler de vigtigste værktøjer til moderne webudvikling.




Build

---
