## 1. Authentication vs Authorization

**Authentication**

* Hvem er brugeren?
* Login med brugernavn og adgangskode.
* ASP.NET Core Identity verificerer brugeren.

**Authorization**

* Hvad må brugeren?
* Roller (`Admin`, `Member`)
* Claims
* Policies

Eksempel:

```csharp
[Authorize]
public IActionResult Profile()
{
}
```

```csharp
[Authorize(Roles = "Admin")]
public IActionResult DeleteUser()
{
}
```

---

### 2. ASP.NET Core Identity

Hvad er Identity?

Identity er Microsofts medlemssystem til ASP.NET Core.

Det håndterer blandt andet:

* Brugere
* Password hashing
* Login
* Roller
* Claims
* Email-verifikation
* Password reset
* Lockout
* 2FA

Du slipper derfor for selv at skrive alt dette.

---

### 3. Identity-klasser

```text
IdentityUser
        ▲
        │
ApplicationUser
```

Eksempel:

```csharp
public class ApplicationUser : IdentityUser
{
    public string FirstName { get; set; } = "";
}
```

---

### 4. Login-flow

```text
Bruger
    │
    ▼
Login
    │
    ▼
UserManager.PasswordSignInAsync()
    │
    ▼
Identity kontrollerer password
    │
    ▼
JWT genereres
    │
    ▼
Access Token
    │
    ▼
Refresh Token
    │
    ▼
HttpOnly Cookie
```

---

### 5. UserManager

Eksempel:

```csharp
var user = await _userManager.FindByEmailAsync(email);
```

```csharp
await _userManager.CreateAsync(user, password);
```

```csharp
await _userManager.CheckPasswordAsync(user, password);
```

---

### 6. SignInManager

```csharp
await _signInManager.PasswordSignInAsync(...)
```

eller

```csharp
await _signInManager.SignOutAsync();
```

---

### 7. RoleManager

```csharp
await _roleManager.CreateAsync(
    new IdentityRole("Admin"));
```

Tilføj rolle:

```csharp
await _userManager.AddToRoleAsync(user, "Admin");
```

---

### 8. Claims

```text
Name
Email
Role
UserId
```

Eksempel:

```csharp
var role = User.FindFirst(ClaimTypes.Role)?.Value;
```

---

### 9. JWT

Vi gennemgår:

* Header
* Payload
* Signature

Eksempel:

```text
Header

↓

Payload

↓

Signature
```

---

### 10. Refresh Token

Hvorfor?

Fordi Access Token udløber.

Refresh Token bruges til at hente et nyt Access Token uden, at brugeren skal logge ind igen.

---

### 11. HttpOnly Cookie

Fordele:

✔ Beskytter mod XSS

✔ Kan ikke læses af JavaScript

✔ God praksis til Refresh Tokens

---

### 12. Roller

```text
Admin

↓

Member

↓

Guest
```

Eksempel:

```csharp
[Authorize(Roles="Admin")]
```

---

### 13. Policies

```csharp
[Authorize(Policy="Over18")]
```

eller

```csharp
builder.Services.AddAuthorization(options =>
{
    options.AddPolicy("Over18",
        p => p.RequireClaim("Age", "18"));
});
```

---

