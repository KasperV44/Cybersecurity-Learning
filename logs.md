# Opintopäiväkirja - Huhtikuu 2026

## 18.4.2026
- **Linux:** Suoritettu Linux Fundamentals Part 1. Opittu navigointi, tiedostojen luku ja SSH-yhteys.
- **Automaatio:** Luotu `thm`-alias Kalin `.zshrc`-tiedostoon OpenVPN-yhteyden helpottamiseksi.
- **Web:** Suoritettu "How the Web Works". Opittu HTTP-metodit (GET/POST) ja statuskoodit.

## 19.4.2026 -Päivä 3
- Pre-Security polun kaikki ilmaiset huoneet suoritettu. Opittu esim. tietokoneen komponenteista, käyttöjärjestelmistä ja kryptografiasta.
- Regex-perusteet aloitettu.

## 20.4.2026 - Päivä 4: OverTheWire - Bandit
- **Level 0:** `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If` - Tiedoston luku `cat`-komennolla.
- **Level 1:** `263JGJPfgU6LtdEvgfWU1XP5yac29mFx` - Opittu lukemaan erikoisnimetty tiedosto (`cat ./-`). Tajuttu, että joka tasolle kirjaudutaan uutena käyttäjänä.
- **Level 2:** `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx` - Käytetty lainausmerkkejä välimerkkejä sisältävissä tiedostoissa.
- **Level 3:** `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ` - Navigointi ja piilotetut tiedostot.
- **Level 4:** `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw` - `file ./*` -komennolla ASCII-tekstitiedoston tunnistus binäärin joukosta.
- **Level 5:** `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG` - Tiedostojen etsintä koon perusteella (`find -size 1033c`).
- **Level 6:** `morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj` - Etsintä koko järjestelmästä parametreilla `-user`, `-group` ja `-. Laitettu muistiinpanoihin virheiden suodattaminen, joka hyödyllinen find ja grep kanssa.
- Level 7: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc -Perus grep haku
- Level 8: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM - Sort ja Uniq käytetty






### Tekninen vinkki: Virheiden suodattaminen (I/O Redirection)
Kun etsitään tiedostoja (`find /`), terminaali täyttyy usein "Permission denied" -virheistä. Ne voi suodattaa pois ohjaamalla ne "mustaan aukkoon":
`find / -user bandit7 -group bandit6 -size 33c 2>/dev/null`

* **1** = Standard Output (normaali tulos)
* **2** = Standard Error (virheilmoitukset)
* **2>/dev/null** = Lähetetään virheet paikkaan, joka tuhoaa ne heti.

