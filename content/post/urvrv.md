+++
title = "Uvod v računalniški vid in razpoznavanje vzorcev"
date = 2026-02-03T07:07:07+01:00
draft = false
math = true

summary = "Zapiski za predmet Uvod v računalniški vid in razpoznavanje vzorcev za zimski semester tretjega letnika FERI RIT UNI, ki zajemajo osnovne koncepte računalniškega vida, obdelavo slik, prepoznavanje vzorcev ter uvod v strojno učenje za analizo vizualnih podatkov."
summary_enable = true
summary_style = "subtitle"
+++

## Uvod v računalniški vid

### Osnovni pojmi

#### Zvezna in diskretna predstavitev signalov

Računalniki so diskretne naprave, saj temeljijo na obdelavi podatkov v obliki vrednosti 0 in 1. Zato zveznih signalov in slik ne moremo neposredno obdelovati, temveč jih moramo najprej pretvoriti v **diskretno obliko**.

Zvezni govor (npr. ko profesor govori) je **zvezni enodimenzionalni signal**. Modeliramo ga lahko z zvezno funkcijo ene zvezne neodvisne spremenljivke, ki je v tem primeru čas. Govor se skozi čas spreminja. Enačba:

\[
y = x(t)
\]

- ta signal je **enodimenzionalen**, ker je odvisen od ene spremenljivke (čas \(t\))
- **zvezni signal** je definiran **v vsakem časovnem trenutku**
- vrednost signala se skozi čas **neprekinjeno** spreminja

Da bi zvezni signal lahko obdelovali z računalnikom, izvedemo postopek **vzorčenja**. Pri tem si želimo, da bi v enakomerno razmaknjenih časovnih trenutkih odtipati vrednosti zveznega signala. S tem dobimo zaporedje številskih vrednosti, kar imenujemo **diskreten signal**. Ko imamo diskreten signal (številke v časovnih trenutkih) odtipamo signal na nek določen časovni interval npr. signal odtipamo na 5, 10, 15 milisekund.

Kakšna pa je vmes vrednost signala med dvema odčitkoma(npr. med 5 in 10 milisekund)?

Tam signal ni definiran, ker ga na teh mestih nismo odtipali. To je bistvena razlika med zveznim in diskretnim signalom. Za diskreten signal pravimo, da je vrednost funkcije definirana samo v določenih časovnih trenutkih npr. 5, 10, 15 mislisekund, za vrednosti vmes pa rečemo, da signal ni definiran-**TO JE OPIS DISKRETNEGA SINGALA**.

{{< alertBlockquote type="important" >}}
Diskreten signal je signal, pri katerem je vrednost funkcije definirana samo v določenih, ločenih časovnih trenutkih (npr. pri 5 ms, 10 ms, 15 ms),
medtem ko za vmesne časovne trenutke signal ni definiran, ker ga nismo odtipali (vzorčili).
{{< /alertBlockquote  >}}

---

##### 2D-slika

Zaenkrat smo si kot vrsto signala ogledali govor. kaj pa slika?

Pri sliki imamo dve osi, višino in dolžino oz. \(x\) in \(y\) os. Zvezno sliko lahko modeliramo kot zvezno funkcijo dveh neodvisnih spremenljivk (dve prostorski osi \(x\) in \(y\)). Enačba za sliko je: 

\[
I = I(x, y)
\]

- \(x\) in \(y\) sta prostorski koordinati  
- \(x, y \in \mathbb{R}\)
- slikovna funkcija je definirana v vsaki točki ravnine

Zvezna slika (prostorska funkcija) je definirana v vsaki točki ravnine. Katerokoli točko si izberemo, bo funkcija definirana. Za vsak \(x\) in \(y\) vemo vrednost funkcije.

Kaj pa zdaj ta vrednost pomeni?

Pri govoru npr. Večja je vrednost, močnejši je glas. Pri sliki pa je odvisno od naprave. Če bo naprava ultrazvok, bo vrednost predstavljala odboj, pri fotoaparatu bo vrednost predstavljala določen spekter barv, svetlost itd.

**Vrednost slikovne funkcije lahko pomeni:**
- svetlost (sivino),
- barvo,
- temperaturo,
- porazdelitev tlaka,
- oddaljenost od opazovalca,
- …

{{< alertBlockquote type="important" >}}
Zvezna slika je zvezna funkcija dveh neodvisnih spremenljivk (\(x\) in \(y\)), ki je definirana v vsaki točki ravnine.
{{< /alertBlockquote  >}}

Kako pa pridemo iz zvezne slike v diskretno sliko?

To dosežemo podobno kot pri zvoku s postopkom diskretizacije oz. vzorčenja. To pomeni, da ne bomo imeli vse podatke za vsak časovni trenutek. 

V smeri \(x\) bomo se zdaj sprehajali s korakom **\(\Delta x\)**. 
Podobno pa bomo diskritizirali tudi drugo prostorsko os \(y\) s korakom **\(\Delta y\)**.



Sedaj smo dobili **prostorske trenutke** (to je na presečiščih korakov **\(\Delta x\)** in **\(\Delta y\)**). Diskretna slika je definirana samo v teh diskretnih prostorskih trenutkih. V teh točkah imamo definirane podatke o vrednosti slikovne funkcije. 


{{< alertBlockquote type="important" >}}
Digitalna oz. diskretna 2D-slika je diskretizirana zvezna 2D-slika. Vrednost slikovne funkcije obstaja samo v diskretnih prostorskih trenutnik oz. lokacijah: \[
I = I(i, j), \quad i, j \in \mathbb{N}
\]
{{< /alertBlockquote  >}}

Točka nima ploščine in nimamo naprave, ki bi znala zajeti nekaj iz prostora kar nima ploščine. Tega ne znamo naredit. V nekem malem območju zato ocenimo nek mali prostor za predstavitev izbrane točke.

Diskretna slika se najbolj pogosto definira oz. predstavi s pomočjo **matrike**. Pomembno je tudi omenit, da diskretne slike nimajo nikoli neskončno dimenzij-v realnem svetu ko pogledamo vidimo zmeraj neko omejeno območje. V primeru slik, če jih ne bi diskretizirali, bi imeli opravka z neskončnim številom podatkov oz. neskončnimi slikami, kar v praksi ni izvedljivo.



Vrednosti, ki smo jih prebrali v prostorskih trenutkih vpisujemo v matriko. 
Osnovni najmanjši gradnik diskretne slike se imenuje **piksel** (picture element oz. slikovni element). Eni programi imenujejo to tudi slikovna točka, kar pa je banalno, ker točk v prostoru ne moremo zajemat, ker točka nima ploščine. Imamo opravka z dimenzijo diskretne slike, podobno kot imamo dimenzije pri matrikah.
Število vrstic in število stolpcev je matrika dimenzije \(M \times N\). 

Štetje oz. indeksiranje je vedno problem (ali začeti z 1 ali z 0)-mi bomo indeksirali z 0. Vsako celico matrike (piksel) bomo označili z indeksom vrstice in stolpca \(p = (x, y)\) oz. \(p = (i, j)\).

Vrednosti iz grafa, kjer se po korakih sprehajamo, prenesemo v celice matrike
Npr. 1 korak v smeri\(x\) in 2 koraka v smer\(y\).



Vrednost diskretne slikovne funkcije v pikslu p označimo kot: 
\[
I(p) \text{ oz. } I(i, j)
\]

Ker je naša slika omejena ima \(M\) vrstic in \(N\) stolpcev, za vrednosti, ki so zunaj teh dimenzij pa **NE VEMO**.

{{< alertBlockquote type="note" >}}
Tu pri tem predmetu lahko dosti krat rečemo kot odgovor **NE VEMO**, pa še prav bo!
{{< /alertBlockquote  >}}

Najmanjši gradnik slike je piksel in slika ima vse skupaj \(M \times N\) pikslov. Je pa še alternativa za predstavitev slike v obliki satovja namesto matrike. Ene stvari se dajo s satovjem boljše rešit.

Vrednosti v matriki:
Rabimo neko podatkovno strukturo v katero bomo shranili matriko in določili kakšnega tipa so ti podatki. Za določanje tega imamo neka pravila oz. določila:

Najbolj pogosto, če delamo s sivinskimi slikami, piksel hrani vrednost sivine oz. svetlosti (brightness). Vrednost piksla (tj. sivina oziroma svetlost v tem pikslu) leži na intervalu \([0, Q]\). Kot tip se tu najbolj pogosto uporablja za hranjenje vrednosti vsakega piksla 8 bitov. Kot tip podatkov za matriko uporabimo tako 8 bitov. Zato imamo 8 bitne slike. Imamo slike po vrednostih od 0-255. Pri 8-bitnih slikah je 
\[
Q = 2^8 - 1 = 255
\]

- **Sivinske slike** vizualiziramo tako, da vrednost piksla pomeni en vstop v barvno paleto.  
V primeru sivinskih slik je to paleta sivin:

- vrednost **0** → črna barva  
- vrednost **127** → 50 % siva barva  
- vrednost **255** → bela barva

Ko delamo z barvnimi slikami pa uporabimo barvno paleto. Ko imamo barvo imamo 3 barve oz. 3 števila RGB. Piksel mora hranit 3 vrednost in rabimo 3x8 bitov:
- za rdečo barvo (red) 8 bitov, 
- za zeleno (green) 8 bitov 
- za modro (blue) 8 bitov. 

Če imamo sivinsko sliko, zakaj 8 bitov?
Normalen človek (če nismo supermani) razlikuje nekje 250 različnih barv, zato 8 bitov zadošča-od tukaj sledi 255 različnih nivojev, ker jih več enostavno človeško oko ne loči.

Nekatere medicinske naprave so zmožne piksle odčitat, da vrednost shranimo v 16 bitov in imamo 16 bitne slike. Ljudje jih ne ločimo, nekateri stroji pa jih znajo zajeti. Tako imamo lahko imamo 16 bitne sivinske slike. 

Pri delu z slikami in biti je tudi dobro omenit, da bite običajno probamo zbit ali pa zakodirat z manjšo količino-uporabljamo kompresijo, ker so slike prostorsko lahko zelo potratne.

##### Video
Videoposnetek pa je slika, ki se s časom spreminja.

Videoposnetek bi definirali s tremi neodvisnih spremenljivkami-\(x\) in \(y\) os, ter čas \(t\) skozi katerega se ti 2 komponenti spreminjata. 

Diskretni video je zaporedje diskretnih slik.

