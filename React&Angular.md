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
