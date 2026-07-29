# De fire søjler i OOP

| OOP-princip     | Hvad betyder det?                                    | Eksempel                              |
| --------------- | ---------------------------------------------------- | ------------------------------------- |
| **Indkapsling** | Beskytter data og samler data + metoder i én klasse. | `private` felter og `public` metoder  |
| **Abstraktion** | Skjuler kompleksitet og viser kun det nødvendige.    | `LavKaffe()` uden at kende detaljerne |
| **Arv**         | En klasse arver fra en anden.                        | `Hund` arver fra `Dyr`                |
| **Polymorfi**   | Samme metode kan opføre sig forskelligt.             | `LavLyd()` giver "Vov!" eller "Miau!" |


De **fire søjler i objektorienteret programmering (OOP)** er grundlaget for, hvordan man designer programmer i f.eks. **C#**.

## 1. Indkapsling (Encapsulation)

**Definition:** Samler data (felter/egenskaber) og de metoder, der arbejder med dataene, i én klasse. Samtidig beskytter man data mod direkte adgang.

### Simpel forklaring

Tænk på en **bil**. Du kan trykke på speederen, men du kan ikke selv ændre motorens indre dele. Bilen styrer selv, hvordan motoren fungerer.

### C#-eksempel

```csharp
public class BankKonto
{
    private decimal saldo;

    public void Indsæt(decimal beløb)
    {
        saldo += beløb;
    }

    public decimal HentSaldo()
    {
        return saldo;
    }
}
```

Her er `saldo` **private**, så ingen kan ændre den direkte:

❌ Ikke tilladt:

```csharp
konto.saldo = 1000000;
```

Man skal i stedet bruge metoderne:

```csharp
konto.Indsæt(500);
Console.WriteLine(konto.HentSaldo());
```

**Fordel:**

* Beskytter data.
* Forhindrer fejl.
* Gør koden mere sikker.

---

## 2. Abstraktion (Abstraction)

**Definition:** Skjuler den komplicerede implementering og viser kun det, brugeren behøver at vide.

### Simpel forklaring

Når du bruger en **fjernbetjening**, trykker du på en knap. Du behøver ikke vide, hvordan elektronikken inde i fjernbetjeningen virker.

### C#-eksempel

```csharp
public class Kaffemaskine
{
    public void LavKaffe()
    {
        OpvarmVand();
        MalBønner();
        BrygKaffe();
    }

    private void OpvarmVand() { }
    private void MalBønner() { }
    private void BrygKaffe() { }
}
```

Brugeren kalder kun:

```csharp
maskine.LavKaffe();
```

Den ved ikke (og behøver ikke vide), hvad der sker indeni.

**Fordel:**

* Gør programmer lettere at bruge.
* Skjuler unødvendige detaljer.

---

## 3. Arv (Inheritance)

**Definition:** En klasse kan arve egenskaber og metoder fra en anden klasse.

### Simpel forklaring

Hvis du har en klasse **Dyr**, kan både **Hund** og **Kat** arve fra den. De får automatisk de fælles egenskaber.

### C#-eksempel

```csharp
public class Dyr
{
    public void Sov()
    {
        Console.WriteLine("Dyret sover");
    }
}

public class Hund : Dyr
{
    public void Gø()
    {
        Console.WriteLine("Vov!");
    }
}
```

Nu kan man skrive:

```csharp
Hund hund = new Hund();

hund.Sov();
hund.Gø();
```

Selvom `Sov()` ikke findes i `Hund`, virker den, fordi den er arvet fra `Dyr`.

**Fordel:**

* Genbruger kode.
* Mindre dobbeltarbejde.
* Lettere vedligeholdelse.

---

## 4. Polymorfi (Polymorphism)

**Definition:** Den samme metode kan opføre sig forskelligt afhængigt af objektets type.

### Simpel forklaring

Alle dyr kan **lave en lyd**, men lyden er forskellig.

### C#-eksempel

```csharp
public class Dyr
{
    public virtual void LavLyd()
    {
        Console.WriteLine("Dyret laver en lyd");
    }
}

public class Hund : Dyr
{
    public override void LavLyd()
    {
        Console.WriteLine("Vov!");
    }
}

public class Kat : Dyr
{
    public override void LavLyd()
    {
        Console.WriteLine("Miau!");
    }
}
```

Brug:

```csharp
Dyr dyr1 = new Hund();
Dyr dyr2 = new Kat();

dyr1.LavLyd(); // Vov!
dyr2.LavLyd(); // Miau!
```

Selvom begge variabler er af typen `Dyr`, udfører de hver deres version af `LavLyd()`.

**Fordel:**

* Mere fleksibel kode.
* Let at udvide med nye klasser.

---

### Kort beskrevet

* **Indkapsling** = **Beskyt data**
* **Abstraktion** = **Skjul kompleksiteten**
* **Arv** = **Genbrug kode**
* **Polymorfi** = **Samme metode – forskellig opførsel**

Det er netop disse fire principper, der gør OOP-kode mere **sikker, overskuelig, genbrugelig og nem at udvide**.
