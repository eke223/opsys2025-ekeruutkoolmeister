# Praktikum 7 – Haakimine

## 1. Miks uued andmekandjad vajavad lähtestamist?

Uued andmekandjad vajavad lähtestamist, sest neil puudub partitsioonitabel ehk struktuur, mis määratleb, kuidas ja kus andmed kettale salvestatakse. Lähtestamisel luuakse andmekandja algusesse partitsioonitabel (nt GPT või MBR), mis võimaldab operatsioonisüsteemil draivi adresseerida ja sellele partitsioone luua. Ilma lähtestamiseta ei tea süsteem, kuidas draivi sektorid on jaotatud ega saa sinna failisüsteemi kirjutada.

---

## 2. GPT eelised MBR-i ees

1. **Suurem partitsioonimaht** – GPT toetab kuni 9,4 zettabaiti ja üle 128 partitsiooni, samas kui MBR on piiratud 2 TB ja 4 esmase partitsiooniga.  
2. **Uuenduslik struktuur** – GPT salvestab varukoopia partitsioonitabelist ketta lõppu, mis võimaldab taastamist, kui alguse tabel rikutakse.  
3. **Kontrollsummad ja vigade avastamine** – GPT kasutab CRC32 kontrollsummasid, et avastada ja parandada tabeli korruptsiooni.  
4. **Ühilduvus ja tulevikukindlus** – GPT on osa UEFI standardist, mis on tänapäevaste süsteemide vaikimisi käivitustehnoloogia, erinevalt MBR-ist, mis on BIOS-i pärand.

---

## 3. Tõend Windowsi võrguketta haakimise kohta

https://kodu.ut.ee/~ekeruut/opsys/hdd.png

---

## 4. Linux (Ubuntu) – käsu ls -la /mnt/ut/public_html/opsys/ väljund

<img width="1249" height="669" alt="image" src="https://github.com/user-attachments/assets/e6e21a3c-3161-432f-b8d9-19e1e94ac5c4" />

---

## 5. Mida mõjutasid mount-käsu parameetrid -o ro ja -t auto?

- `-o ro` tähendab, et seade haagitakse ainult lugemisõigustes (*read-only*), mis välistab andmete kogemata muutmise.  
- `-t auto` laseb süsteemil automaatselt tuvastada failisüsteemi tüübi (nt ntfs, vfat, ext4), määrates sobiva draiveri ilma käsitsi sekkumiseta.

---

## 6. Millise väärtusega asendas Ubuntu `auto` mount-tüübi?

Ubuntu asendaks `-t auto` parameetri tegeliku failisüsteemi tüübiga (nt vfat, ntfs, ext4) vastavalt seadmel tuvastatule kuid mul mälupulka ei ole.

---

## 7. Automaatne 4 TB ketta ühendamine (fstab)

<img width="823" height="575" alt="image" src="https://github.com/user-attachments/assets/ccbe6652-6121-4f00-91c1-dd4415f62f05" />

---

