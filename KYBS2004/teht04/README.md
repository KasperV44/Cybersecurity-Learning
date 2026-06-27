Tehtävä 4: ECDSA salauksen murtaminen

Harjoituksessa murrettiin EDCDSA salaus, löytämällä kaksi samaa satunnaislukua, jolla 2 eri tiedostoa oli allekirjoitettu, jonka ansioista pystytiin laskemaan salainen avain.

Vaihe 1: Haettiin tiedostojen SHA1 hashit
sha1sum signable1.txt signable2.txt

Vaihe 2: Allekirjoituksessa olivat DER muodossa ja ne purettiin OpenSSL asn1parse työkalulla, josta nähtiiin r ja s muuttujat. Tästä huomattiin että samaa satunnaialukua oli käytetty.
openssl asn1parse -inform DER -in username-signable1.txt.sig.der
openssl asn1parse -inform DER -in username-signable2.txt.sig.der

Vaihe 3: Syötettiin saadut arvot python skriptiin, joka laski noncen ja salaisen avaimen eksponentin

Opittu: Mielenkiintoinen tehtävä. Murtamiseen ei tarvittu edes julkista avainta vaan pelkästään tiedostojen julkiset allekirjoitukset ja tiivisteet riitivät paljastamaan salaisen avaimen, koska samaan noncea oli käytetty kahdesti.