📦 Projekt: Przepompownia (CODESYS)
Opis:
Projekt przedstawia automatykę przepompowni zbudowaną w środowisku CODESYS. Zbiornik napełniany cieczą jest opróżniany przez trzy pompy sterowane w zależności od poziomu cieczy.

⚙️ Logika działania:
Pompa 1: załącza się przy poziomie 2 m, wyłącza przy 1 m

Pompa 2: załącza się przy 4 m, wyłącza przy 3 m

Pompa 3: załącza się przy 5 m, wyłącza przy 4 m

Pompy uruchamiane są w kolejności: Pompa1 → Pompa2 → Pompa3

🔒 Zabezpieczenia każdej pompy:
xCzf – czujnik kolejności faz

xTermik – zabezpieczenie termiczne

xPrzeciazenie – zabezpieczenie przeciążeniowe

Sygnał z każdego zabezpieczenia musi mieć wartość logiczną 1, by umożliwić uruchomienie pompy.

🧠 Logika styczników:
Pompy są załączane poprzez styczniki.

Styczniki posiadają styki pomocnicze – dają potwierdzenie załączenia do wejść PLC.

Jeśli sygnał potwierdzenia nie pojawi się w czasie tCzasPotwierdzeniaZalaczenia, generowana jest awaria.

🔧 Tryb pracy:
xEnable – odstawienie pompy (blokada)

xTrybManual + xPracaManual – tryb ręczny

W momencie awarii – pompa wyłączana

Awarię można skasować przez reset xEnable

Zliczanie: czasu pracy (dokładność do 15 s) oraz ilości załączeń

🖥️ Wizualizacja:
Projekt zawiera dedykowaną wizualizację HMI z pełnym podglądem stanu pomp, poziomu cieczy oraz trybu pracy.




# 💧 Pumping Station Project (CODESYS)

**Description**:  
This project demonstrates the automation of a pumping station built in the CODESYS environment. The tank is filled with liquid and then emptied using three pumps controlled based on the current liquid level.

---

## ⚙️ Logic of Operation:

- **Pump 1**: Turns on at 2 m, turns off at 1 m  
- **Pump 2**: Turns on at 4 m, turns off at 3 m  
- **Pump 3**: Turns on at 6 m, turns off at 5 m  

- Pumps are started in order: **Pump1 → Pump2 → Pump3**

---

## 🔐 Safety Features for Each Pump:
- `xCzf` – phase sequence sensor  
- `xTermik` – thermal protection  
- `xPrzeciążenie` – overload protection  

Each protection signal must be logically `TRUE` (1) to allow pump operation.

---

## 🧠 Contactor Logic:
- Pumps are switched via contactors.  
- Contactors have auxiliary contacts used to confirm engagement to the PLC input.

If confirmation is not received within the time specified by `tCzasPotwierdzeniaZalaczenia`, an alarm is generated.

---

## 🛠️ Modes of Operation:
- `xEnable` – disables the pump (lockout)  
- `xTrybManual` + `xPracaManual` – manual mode  


