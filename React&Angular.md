* 📘 **React & Next.js Kompendium**
* 📗 **Angular Kompendium**

Et tredje kapitel kan være:

* 📙 **React vs Angular – Cheat Sheet**

---

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

Build

---

# 📗 Angular Kompendium

## Del 1 – Introduktion

* Angular
* TypeScript
* CLI
* Projektstruktur

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
