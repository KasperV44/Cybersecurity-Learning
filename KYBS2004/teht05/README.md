Tehtävä 5: ECDSA allekirjoituyksen luominen
Tehtävässä muokatiin skripitä, jonka jälkeen luotiin uudet allekirjoitukset käytämällä edellisessä tehtävässä murrettua avainta

Vaihe 1: Importattiin sys kirjasto ja tehtiin sign-funktiolla kutsu, joka otti vastaan 5 argumettia
import sys

sign(sys.argv[1], sys.argv[2], sys.argv[3], sys.argv[4], sys.argv[5])

Vaihe 2: Skripti suoritettiin murretulla avaimella, 2 allekirjoitetullla tiedostolla, kiinteällä noncella ja ulostulolla

python3 ecdsa_sign.py cracked-privkey.pem signable1.txt signable2.txt 4 oma_signature.txt

Opittu: Tehtävä korosti entisestään miten tärkeitä satunnaislukujen merkitys on kryptografiassa. 