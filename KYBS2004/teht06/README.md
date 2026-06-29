Tehtävä 6: md5 collision
Tehtävässä tutustuttiin md5 heikkouteen luomalla törmäys eli kaksi erilaista tiedostoa, jotka tuottavat saman md5-arvon.

Vaihe 1: Käytettiin md5_fastcoll työkalua luomaan kaksi uutta tiedostoa käyttäen pohjana valmiiina olevaa tiedostoa
./hashclash-static-release-v1.2b/bin/md5_fastcoll -p COLLIDE_THIS.txt -o file1.bin file2.bin

Vaihe 2: Tarkistettiin luotujen tiedostojen tiivisteet md5sum komennolla
md5sum file1.bin
md5sum file2.bin

Huomattiin, että tiivisteet olivat samat, vaikka tiedostojen sisällöt olivat erilaiset

Opittu: Harjoituksessa näytettiin miksi md5 algoritmi ei ole paras valinta nykypäivänä. Työkalaluilla on helppo luoda saman md5-arvon omaava tiedosto. Nykyään pitäisi siis käyttää esim sha-256.