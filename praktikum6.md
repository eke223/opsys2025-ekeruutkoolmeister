# Praktikum 6 – Protsessi signaalid, sisendid ja väljundid

### Ülesanne 6-1
<img width="1037" height="606" alt="image" src="https://github.com/user-attachments/assets/36e18360-6698-4054-a15c-9cfbd6d7648e" />

### Ülesanne 6-2
<img width="1319" height="708" alt="image" src="https://github.com/user-attachments/assets/000da42f-d0bd-4c20-8e16-f4f83ed2dee7" />

### Ülesanne 6-3
ps -axu | grep daemon | grep -v grep | tr -s ' ' | cut -d' ' -f11-
<img width="1225" height="677" alt="image" src="https://github.com/user-attachments/assets/64ca1350-61bb-43c9-84f8-d476575b0fee" />

### Ülesanne 6-4
<img width="1158" height="733" alt="image" src="https://github.com/user-attachments/assets/9650e6c8-c899-4d8f-950f-1551b014b472" />

## Ülesanne 6-5
| ID | Nimi | wParam | lParam | Kirjeldus |
|----|------|---------|---------|------------|
| 512 | WM_MOUSEMOVE | 0 | 983619 | Saadetakse, kui hiir liigub akna kliendialas. |
| 16 | WM_CLOSE | 0 | 0 | Saadetakse, kui kasutaja sulgeb akna (nt klõpsab X-nuppu). |
| 537 | ??? | 7 | 0 | Tegelikult WM_MOUSEHWHEEL|


**Selgitus:**
Sõnumid näitavad, kuidas Windows suhtleb akendega. Näiteks hiire liigutused ja akna sulgemine tekitavad erinevaid teateid, mida rakendus saab töödelda.

**Allikad:**
- [WM_MOUSEMOVE – Microsoft Docs](https://learn.microsoft.com/en-us/windows/win32/inputdev/wm-mousemove)  
- [WM_CLOSE – Microsoft Docs](https://learn.microsoft.com/en-us/windows/win32/winmsg/wm-close)
- [WM_MOUSEHWHEEL – Microsoft Docs](https://learn.microsoft.com/en-us/windows/win32/inputdev/wm-mousehwheel)
