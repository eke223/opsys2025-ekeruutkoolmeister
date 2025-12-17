# Praktikum Praktikum13 - Skriptimine Linuxis

## Ülesanne 3
```bash
#!/bin/sh

if [ -n "$1" ]; then
        nimi="$1"
        echo "Tere, $nimi!"
else
        echo "Tere!"
        echo "Sisesta oma nimi:"
        read nimi
fi

echo "Sisesta oma eriala:"
read eriala

echo "Sisesta oma matriklinumber:"
read matrikkel

echo "----"
echo "Nimi: $nimi"
echo "Eriala: $eriala"
echo "Matriklinumber: $matrikkel"
```
<img width="1077" height="637" alt="image" src="https://github.com/user-attachments/assets/0c6da2e7-8cac-49c5-832c-0f86399a3de3" />

---
## Ülesanne 4
```bash
#!/bin/bash

if [ $# -ne 2 ]; then
    echo "Kasutus: $0 vana_laiend uus_laiend"
    exit 1
fi

vana=".$1"
uus=".$2"

for fail in $(ls)
do
    if [ "${fail##*.}" = "$1" ]; then
        uusnimi="${fail/$vana/$uus}"
        mv "$fail" "$uusnimi"
        echo "Muudeti: $fail -> $uusnimi"
    fi
done
```

<img width="1069" height="586" alt="image" src="https://github.com/user-attachments/assets/80acef24-aa62-4c7f-a01e-bf65c3133fa2" />

---
## Ülesanne 5
```bash
#!/bin/bash

if [ -z "$1" ]; then
    echo "Kasutus: $0 protsessi_nimi"
    exit 1
fi

IFS=$'\n'

for rida in $(ps -A)
do
    puhas=$(echo " $rida" | tr -s ' ')
    pid=$(echo "$puhas" | cut -d ' ' -f2)
    nimi=$(echo "$puhas" | cut -d ' ' -f5)

    if [ "$nimi" = "$1" ]; then
        echo "Leitud protsess: $nimi (PID: $pid)"
    fi
done
```
<img width="1084" height="546" alt="image" src="https://github.com/user-attachments/assets/ea2a5569-71c7-4f45-80a0-2bdfdb7c45ba" />

---
## Ülesanne 6
```bash
#!/bin/bash

aste () {
    alus=$1
    astendaja=$2
    tulemus=1

    for (( i=0; i<astendaja; i++ ))
    do
        tulemus=$((tulemus * alus))
    done

    echo $tulemus
}

vastus=$(aste 9 5)
echo "9^5 = $vastus"
```
<img width="1153" height="670" alt="image" src="https://github.com/user-attachments/assets/6fcafe51-cfa3-4cd2-89bf-2b9bb6d48ebc" />

---
## Ülesanne 7
<img width="1920" height="1078" alt="image" src="https://github.com/user-attachments/assets/90548d4b-0730-4988-9e96-ab04cc2910f6" />

---
