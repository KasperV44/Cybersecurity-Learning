Tehtävä 3: Digitaalinen allekijoitus ja todentaminen
Tehtävässä käytetiin aikaisemmin tehtyä väärennettyä yksityistä avainta, jonka avulla luotiin digitaalinen allekirjoitus ja todennettiin se julkisella avaimella.

Vaihe 1: Käytettiin OpenSSL rsault jonka avulla allekirjoitettiin tiedosto allekirjoitustiedostoksi
openssl rsautl -sign -inkey private.key -in SIGN_THIS.txt -out signature.dat

Vaihe 2: Varmistettiin allekirjoituksen aitous julkisella avaimella, jotta tiedetään, että viesti on aito
openssl rsautl -verify -pubin -inkey pub.pem -in signature.dat

Vaihe 3: Muutettiin allekirjoitus heksadesimaalimuotoon
openssl rsautl -sign -inkey private.key -in SIGN_THIS.txt -hexdump

Opittu:
Digitaalisen allekirjoituksen toimintaperiaate, joka toimii vähän niinkuin rsa salauksen vastaoperaationa.