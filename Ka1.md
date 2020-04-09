## Oppgave 1 
Emri i skedarit: `programi_im.py`

Shkruani një program që shfaq në ekran "Ky është programi im".

<details><summary>💾 Zgjidhje alternative </summary>
<p>

``` python
print("Ky është programi im")
```

</p>
</details>


***

## Informacione personale 
Emri i skedarit: `person.py`
1.Shkruani emrin, telefonin dhe adresën tuaj në ekran në të njëjtën linjë.
2.Shkruajeni emrin, telefonin dhe adresën tuaj në ekran në secilin rresht.


<details><summary>💾 Zgjidhje alternative </summary>
<p>

``` python
# 1
print("Perparim Shala 049000111 Rr.Ilaz Kodra, Drenas")

# 2
print("Perparim Shala\n 049000111\n Rr.Ilaz Kodra, Drenas")
# apo
print("Perparim Shala")
print("049000111")
print("Rr.Ilaz Kodra, Drenas")
```

</p>
</details>


***

## Oppgave 2
### 2a
Skriv en klasse Motorsykkel.java. Klassen skal inneholde følgende instansvariabler:
- `private int kilometerstand`
- `private String registreringsnummer`
- `private int produksjonsnummer`

Klassen skal også inneholde en konstruktør som tar inn registreringsnummeret. Instansvariabelen `kilometerstand` skal starte med verdien `0`.

I tillegg skal klassen inneholde en `private static int teller`, som starter med verdien `0`. Denne skal dere ta i bruk i konstruktøren, slik at hvert nye `Motorsykkel`-objekt får et unikt produksjonsnummer.

<details><summary>💾 Løsningsforslag </summary>
<p>

```java
class Motorsykkel {
    private int kilometerstand;
    private String registreringsnummer;
    private int produksjonsnummer;
    private static int teller = 0;
    
    public Motorsykkel (String regnr) {
        this.kilometerstand = 0;
        registreringsnummer = regnr;
        
        this.produksjonsnummer = teller;
        teller++;
    }
}
```

</p>
</details>


### 2b
Skriv en metode `public int hentKilometerstand`. Metoden tar ikke imot noen parametere, men skal returnere antall kilometer motorsykkelen har kjørt. Skriv deretter en tilsvarende metode `public int hentProduksjonsnummer`.

<details><summary>💾 Løsningsforslag </summary>
<p>

```java
public int hentKilometerstand() {
    return kilometerstand;
}

public int hentProduksjonsnummer() {
    return produksjonsnummer;
}
```

</p>
</details>

### 2c
Skriv en metode `public void kjoer` som tar imot et parameter `int antallKilometer`. Metoden skal legge `antallKilometer` til instansvariabelen `int kilometerstand`.

<details><summary>💾 Løsningsforslag </summary>
<p>

```java
public void kjoer(int antallKilometer) {
    kilometerstand += antallKilometer;
}
```

</p>
</details>

### 2d
Skriv en klasse `MotorsykkelProgram.java`. Klassen skal inneholde en `main`-metode. Opprett et objekt av klassen `Motorsykkel` inne i `main`-metoden med et registreringsnummer.

Deretter skal dere skrive en `while`-løkke som skal gå 5 ganger. For hver gjennomkjøring av løkken skal dere kalle på `Motorsykkel`-objektets `kjoer`-metode med `10` som parameter.

<details><summary>💾 Løsningsforslag </summary>
<p>

```java
class MotorsykkelProgram {
    public static void main(String[] args) {
        Motorsykkel m1 = new Motorsykkel("AB1234");

        int t = 0;
        while (t < 5) {
            m1.kjoer(10);
            t++;
        }
    }
}
```

</p>
</details>

### 2e
Hvis vi kalte på `Motorsykkel`-objektets `hentKilometerstand`-metode nå, hvilket resultat får vi?

<details><summary>💾 Løsningsforslag </summary>
<p>

```java
System.out.println(m1.hentKilometerstand()); // 50
```

</p>
</details>

### 2f
Vi tenker oss at vi oppretter to `Motorsykkel`-objekter til. Hvilke produksjonsnummere vil de ha?

<details><summary>💾 Løsningsforslag </summary>
<p>

```java
Motorsykkel m2 = new Motorsykkel("HELLO1");
Motorsykkel m3 = new Motorsykkel("22TUUT");
System.out.println("m2: " + m2.hentProduksjonsnummer()); //1
System.out.println("m3: " + m3.hentProduksjonsnummer()); //2
```

</p>
</details>


***
