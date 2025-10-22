# Praktikum 5 – Failiõigused Linuxis

### Ülesanne 5-1

a) Faili lugemiseks on minimaalselt vaja:  
- kaustal '/tmp/kaust' õigust 'x' (sisenemiseks);  
- failil 'minufail.txt' õigust 'r' (lugemiseks).

b) Faili kustutamiseks on minimaalselt vaja:  
- kataloogil '/tmp/kaust' õigusi 'w' ja 'x';  
- kaustal pole vaja õigusi.
---

### Ülesanne 5-2

Käsk 'chmod a=x skriptifail' annab ainult käivitusõiguse, kuid mitte lugemisõigust.  
Shell peab skripti enne käivitamist lugema, seega on vaja ka 'r' õigust.

Shelliskript vajab vähemalt õigusi 'r+x'.

---

### Ülesanne 5-3

Igal kasutajal on oma nimeline grupp, et vaikimisi 'umask 0002' ei muudaks faile teiste kasutajate poolt kirjutatavaks.  
See võimaldab turvaliselt jagada faile grupipõhiselt, ilma et teised kasutajad saaksid neid muuta.

---

### Ülesanne 5-4

Minimaalsed õigused:
- kaust 'majasiseseks-kasutamiseks': grupile 'x'
- fail 'uusfail.txt': grupile 'r'
 <img width="1234" height="621" alt="image" src="https://github.com/user-attachments/assets/d2cb31fe-cba2-40af-b76d-7a0e8b0b204a" />

 ---
 
### Ülesanne 5-5

- Setuid-õigus võimaldab programmi käivituda faili omaniku õigustes, andes ajutiselt kõrgemad õigused tavalisele kasutajale.

<img width="1547" height="704" alt="image" src="https://github.com/user-attachments/assets/cf50ba66-c088-4eb4-ac85-e36a9cb33b9d" />

 ---
 
### Ülesanne 5-6

Jah, setuid kasutamine võib vähendada süsteemi turvalisust.

- Kui setuid on seatud root-omanduses programmile, siis käivitudes saab programm töötada root-õigustes, mis võib võimaldada tavalisel kasutajal teha toiminguid, mida tal tavaliselt lubatud pole.  
- Turvarisk tekib, kui programm sisaldab vigu või pahatahtlikku käitumist, mis võimaldab tõsta õigusi või pääseda süsteemile ligi, mis muidu oleks keelatud.  
- Seetõttu peab setuid olema seatud ainult kontrollitud ja piiratud programmidele, mis vajavad kõrgemaid õigusi, ning tavaliste programmide puhul on see turvarisk.

 ---
 
### Ülesanne 5-7

- faili omanik (nt Peeter)
- kataloogi omanik (antud juhul Opetaja)
- root kasutaja

 ---
 
### Ülesanne 5-8

<img width="1762" height="814" alt="image" src="https://github.com/user-attachments/assets/074153bc-1a15-4f0d-b692-aa3a00d19eaf" />

### Ülesanne 5-9

- Faili sisu ei saa keegi muuta (chattr +i teeb faili immutable).

- Faili testfail-2 saab kustutada ainult käsudega:

```
sudo chattr -i testfail-2 
sudo rm testfail-2
```
 ---
