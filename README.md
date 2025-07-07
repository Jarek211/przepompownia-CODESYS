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

