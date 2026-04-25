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

## 21.4.2026 - Päivä 5: OverTheWire - Bandit

- Level 9: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey -Strings ja grep putkitus
- Level 10: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr -Base64 decoodaus
- Level 11: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4 -Echo ja tr tr 'A-Za-z' 'N-ZA-Mn-za-m', jolla saa kääntymään rot13
- Level 12: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn -xxd, gzip, bzip2, tar, tiedostojen decompressointia. kesti hetki päästä alkuun ja tajuta miten gzip,bzip2 ja tar toimii. Sen jälkeen helppoa toistoa.
- Level 13: ssh hommat jäi kesken ssh -i jotain jotain jotain 

## 22.4.2026 - Päivä 6: OverTheWire - Bandit
- Level 13 tehty -ssh hommat kaipaa kyl viel harjotteluu
- Level 14 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo - nc yhteys portti 30000
- Level 15: kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx - openssh
- Level 16: nmap portti scan ja siit vaa testailuu mikä on oikee
- Level 17: x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO - diff vertailu, aika helppo taso tähän kohtaan
- Level 18 cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8 -käskyjä voi antaa vaikka ei ole sisällä
- Päivän mietteet: paljon ssh juttuja opittu, joutu googlettamaan aika paljon ja miettimään miten asioita tehdään tai miten ne toimivat. Enää ei ollut niin selvää mitä komentoa käyttää missäkin tasossa kun aikaisemmin se oli aika helppoa.

## 23.4.2026 - Päivä 7: Youtube videot
Tänään oli vähän laiskempi päivä ja tyydyin kattomaan Networkchuckin linux videoita. 

## 25.4.2026 - Päivä 8: Linux kertailua
Katoin Youtubesta ratkaisuja OTW Bandit tasoihin, joita olin aiemmin vetänyt läpi ja muistelin komentoja ja niiden käyttöä. Kokeilin myös toissapäivänä oppimiani komentoja esim apropos, jolla pystyy hakemaan komentoja jos ei muista tarkalleen nimeä. 

### Tekninen vinkki: Virheiden suodattaminen (I/O Redirection)
Kun etsitään tiedostoja (`find /`), terminaali täyttyy usein "Permission denied" -virheistä. Ne voi suodattaa pois ohjaamalla ne "mustaan aukkoon":
`find / -user bandit7 -group bandit6 -size 33c 2>/dev/null`

* **1** = Standard Output (normaali tulos)
* **2** = Standard Error (virheilmoitukset)
* **2>/dev/null** = Lähetetään virheet paikkaan, joka tuhoaa ne heti.

