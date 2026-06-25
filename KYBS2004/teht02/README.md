Tehtävä 2: rsa purkaminen väärennetyllä avaimella

Tehtävässä käytettiin edellisen harjoituksen alkutekijöitä joidenka avulla muodostetiin uusi yksityinen avain

Vaihe 1: käytettiin python skriptiä jolle syötettiin alkuperäinen julkinen avain ja läydetyt alkutekijät, josta skripti loi toimivan yksityisen avaimen.

python3 reconstruct_privkey.py pub.pem 273643268872207043202341435615638028633 322152572734945839280701082177632281147 > private.key

Vaihe 2: Kun yksityinen avain oli käytössä purettiin salatun tiedoston sisältö OpenSSL rsault-työkalulla

openssl rsautl -decrypt -inkey private.key -in encrypted_flag.rsa

Opittu: Jos julkisen avaimen alkutekijät on saatu selville salattua sisältöä on helppo päästä käyttämään. RSA salaus on täysin riippuvainen alkutekijöiden jaon vaikeudesta.