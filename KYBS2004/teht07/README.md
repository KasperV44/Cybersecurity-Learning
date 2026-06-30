Tehtävä 7: MD5 evilize
Tehtävä vastasi erittäin paljo edellistä, mutta asiaa vietiin hieman pidemälle tekemällä kaksi tiedostoa jotka suorittivat koodia ja omasivat saman md5-tiivisteen.

Vaihe 1: Luotiin törmäys tiedostot md5_fastcollilla ja erotettiin blob2. Yhdistetiin osat skripteiksi.
../md5/hashclash-static-release-v1.2b/bin/md5_fastcoll -p prefix -o col1 col2
tail -n +8 col1 > blob2
cat col1 middle blob2 suffix > non-malicious.py
cat col2 middle blob2 suffix > malicious.py

Vaihe 2: Tarkistetiin MD5 summat ja tiedostojen eriäväisyys
md5sum non-malicious.py malicious.py
python3 non-malicious.py
python3 malicious.py

Opittu: Vahvisti edellisestä tehtävästä opittua faktaa, että tiedoston turvallisuudesta ja luotettavuudesta ei voi varmistua ainoastaan MD5 summan avulla. 