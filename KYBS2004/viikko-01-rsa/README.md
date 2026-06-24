Viikko 1
Ekan viikon tehävänä oli murtaa 256-bittinen rsa-avain alkutekijöihin.

Vaihe 1: Etsiä avain ja hakea modulus heksadesimaalimuodossa OpenSSL avulla.
openssl rsa -pubin -in pub.pem -modulus -noout

Vaihe 2: Muutta luku kymmenjärjestelmä muotoon Python skriptin avulla.
python3 -c "import sys; print(int(' Luku         ', 16))"

Vaihe 3: Tekijöiden etsiminen Msieve avulla
msieve -v Luku

Opittu
Tehtävä oli aika yksinkertainen ja se opetti, että lyhyet rsa-avaimet on todella helppo murtaa ihan perus tietokoneellakin. Nykyään pitäisi siis käyttää pidempiä avaimia esim 2048 bittisiä, jolloin lasketa-aika olisi nykykoneilla liian pitkä murtamiseen. 