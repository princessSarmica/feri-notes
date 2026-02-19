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

Da bi zvezni signal lahko obdelovali z računalnikom, izvedemo postopek **diskretizacije** (**vzorčenja**). Pri tem si želimo, da bi v enakomerno razmaknjenih časovnih trenutkih odtipati vrednosti zveznega signala. S tem dobimo zaporedje številskih vrednosti, kar imenujemo **diskreten signal**. Ko imamo diskreten signal (številke v časovnih trenutkih) odtipamo signal na nek določen časovni interval npr. signal odtipamo na 5, 10, 15 milisekund.

Kakšna pa je vmes vrednost signala med dvema odčitkoma(npr. med 5 in 10 milisekund)?

Tam signal ni definiran, ker ga na teh mestih nismo odtipali. To je ključna razlika med zveznim in diskretnim signalom. Za diskreten signal pravimo, da je vrednost funkcije definirana samo v določenih časovnih trenutkih npr. 5, 10, 15 mislisekund, za vrednosti vmes pa rečemo, da signal ni definiran-**TO JE OPIS DISKRETNEGA SINGALA**.

> [!IMPORTANT]
> Diskreten signal je signal, pri katerem je vrednost funkcije definirana samo v določenih, ločenih časovnih trenutkih (npr. pri 5 ms, 10 ms, 15 ms),
medtem ko za vmesne časovne trenutke signal ni definiran, ker ga nismo odtipali (vzorčili).

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

> [!IMPORTANT]
> Zvezna slika je zvezna funkcija dveh neodvisnih spremenljivk (\(x\) in \(y\)), ki je definirana v vsaki točki ravnine.

Kako pa pridemo iz zvezne slike v diskretno sliko?

To dosežemo podobno kot pri zvoku s postopkom diskretizacije oz. vzorčenja. To pomeni, da ne bomo imeli vse podatke za vsak časovni trenutek. 

V smeri \(x\) bomo se zdaj sprehajali s korakom **\(\Delta x\)**. 
Podobno pa bomo diskritizirali tudi drugo prostorsko os \(y\) s korakom **\(\Delta y\)**.



Sedaj smo dobili **prostorske trenutke** (to je na presečiščih korakov **\(\Delta x\)** in **\(\Delta y\)**). Diskretna slika je definirana samo v teh diskretnih prostorskih trenutkih. V teh točkah imamo definirane podatke o vrednosti slikovne funkcije. 


> [!IMPORTANT]
> Digitalna oz. diskretna 2D-slika je diskretizirana zvezna 2D-slika. Vrednost slikovne funkcije obstaja samo v diskretnih prostorskih trenutnik oz. lokacijah: \[
I = I(i, j), \quad i, j \in \mathbb{N}
\]

Točka nima ploščine in nimamo naprave, ki bi znala zajeti nekaj iz prostora kar nima ploščine. Tega ne znamo naredit. V nekem malem območju zato ocenimo nek mali prostor za predstavitev izbrane točke.

Diskretna slika se najbolj pogosto definira oz. predstavi s pomočjo **matrike**. Pomembno je tudi omenit, da diskretne slike nimajo nikoli neskončno dimenzij-v realnem svetu ko pogledamo vidimo zmeraj neko omejeno območje. V primeru slik, če jih ne bi diskretizirali, bi imeli opravka z neskončnim številom podatkov oz. neskončnimi slikami, kar v praksi ni izvedljivo.



Vrednosti, ki smo jih prebrali v prostorskih trenutkih vpisujemo v matriko. 
Osnovni najmanjši gradnik diskretne slike se imenuje **piksel** (picture element oz. slikovni element). Eni programi imenujejo to tudi slikovna točka, kar pa je zavajajoče, saj točke v prostoru ne moremo zajemat, ker točka nima ploščine. Imamo opravka z dimenzijo diskretne slike, podobno kot imamo dimenzije pri matrikah.
Število vrstic in število stolpcev je matrika dimenzije \(M \times N\). 

Štetje oz. indeksiranje je vedno problem (ali začeti z 1 ali z 0)-mi bomo indeksirali z 0. Vsako celico matrike (piksel) bomo označili z indeksom vrstice in stolpca \(p = (x, y)\) oz. \(p = (i, j)\).

Vrednosti iz grafa, kjer se po korakih sprehajamo, prenesemo v celice matrike
Npr. 1 korak v smeri\(x\) in 2 koraka v smer\(y\).



Vrednost diskretne slikovne funkcije v pikslu p označimo kot: 
\[
I(p) \text{ oz. } I(i, j)
\]

Ker je naša slika omejena ima \(M\) vrstic in \(N\) stolpcev, za vrednosti, ki so zunaj teh dimenzij pa **NE VEMO**.

> [!INFO]
> Tu pri tem predmetu lahko dosti krat rečemo kot odgovor **NE VEMO**, pa še prav bo!

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

---

##### Video
Videoposnetek pa je slika, ki se s časom spreminja.

Videoposnetek bi definirali s tremi neodvisnih spremenljivkami-\(x\) in \(y\) os, ter čas \(t\) skozi katerega se ti 2 komponenti spreminjata. 

Diskretni video je zaporedje diskretnih slik.

---

#### Kontrastna in prostorska ločljivost slike

Nalednja dva pojma sta **prostorska** in **kontrastna ločljivost**. 

---

##### Kontrastna ločljivost

> [!IMPORTANT]
> **Kontrastna ločljivost** je tesno povezana s številom bitov, ki jih uporabljamo za predstavitev vrednosti piksla. Predstavlja število različnih sivinskih nivojev, ki jih lahko vsebuje slika.

###### Teoretična kontrastna ločljivost

**Teoretična maksimalna kontrastna ločljivost** je določena s številom možnih vrednosti piksla in je enaka:

\[
Q + 1
\]

kjer je \(Q\) največja možna vrednost piksla.

Pri 8-bitni sivinski sliki velja:
\[
Q = 2^8 - 1 = 255
\]

kar pomeni, da ima slika 256 različnih sivinskih nivojev.

###### Dejanska kontrastna ločljivost

**Dejanska kontrastna ločljivost** pomeni število sivinskih nivojev, ki so dejansko prisotni v sliki. Določimo jo tako, da v sliki preštejemo različne sivinske vrednosti.

- višja kontrastna ločljivost → več sivinskih nivojev  
- nižja kontrastna ločljivost → manj sivinskih nivojev  

Višja kontrastna ločljivost omogoča ohranitev več podrobnosti v sceni.  
Z več sivinskimi nivoji lahko natančneje predstavimo prehode med svetlimi in temnimi območji slike.

Manjša kontrastna ločljivost pomeni, da se bližnji sivinski nivoji zlijejo med seboj, kar povzroči izgubo informacij –  
podrobnosti se združijo z večjimi, enotnimi območji slike.

###### Vpliv kontrastne ločljivosti na analizo slike

Če želimo biti pri analizi slike natančni, kontrastne ločljivosti ne smemo zmanjševati, saj bi s tem izgubili pomembne podrobnosti.

Kadar pa nas zanimajo predvsem večje oblike oziroma večji objekti na sliki, je zmanjšanje kontrastne ločljivosti smiselno.  
Pri realno-časovnih aplikacijah, kjer je čas obdelave omejen, lahko z zmanjšanjem kontrastne ločljivosti:
- zmanjšamo količino podatkov,
- pospešimo obdelavo,
- prihranimo prostor za shranjevanje in prenos.

###### Kdaj uporabiti zmanjšano kontrastno ločljivost

- ko nas zanimajo predvsem velike oblike in objekti na sliki  
- ko želimo prihraniti čas obdelave in prostor za shranjevanje  

###### Kdaj zmanjšane kontrastne ločljivosti ne uporabiti

- ko je potrebna visoka natančnost  
- ko so pomembne podrobnosti in detajli na sliki  

---

##### Prostorska ločljivost

> [!IMPORTANT]
> **Prostorska ločljivost** je določena kot število pikslov na določeno mersko enoto. Omogoča povezavo med svetom pikslov (meritve v slikah) in realnim svetom, kjer uporabljamo merske enote, kot so mm, cm ali m.

Izražena je kot:
- število pikslov na mersko enoto (npr. piksel/mm)

Prostorsko ločljivost lahko definiramo posebej:
- v smeri osi \(x\),
- v smeri osi \(y\).

V večini aplikacij predpostavimo, da so piksli **kvadratni**, zato sta ločljivosti v obeh smereh enaki.

> [!WARNING]
> **Prostorske ločljivosti ne smemo zamenjevati z velikostjo slike. Čeprav sta prostorska ločljivost in velikost slike pogosto povezani med sabo, to NISTA ISTA POJMA!**

> **Primer: A4 list**
>
> Dimenzije A4 lista:  
> – \(y = 297\,\text{mm}\)  
> – \(x = 210\,\text{mm}\)
>
> Če A4 list skeniramo ali fotografiramo pri prostorski ločljivosti **100 pikslov na mm**, dobimo sliko velikosti:  
> – \(29700 \times 21000\) pikslov
>
> Če isti list zajamemo pri prostorski ločljivosti **1 piksel na mm**, dobimo sliko velikosti:  
> – \(297 \times 210\) pikslov
>
> V obeh primerih gre za isti fizični objekt, vendar z različno prostorsko ločljivostjo in posledično različno velikostjo slike.  
> **Iz primera vidimo, da večja prostorska ločljivost ne pomeni večjega objekta, temveč le natančnejši opis istega objekta.**

###### Prostorska ločljivost z vidika obdelave slik

Višja prostorska ločljivost pomeni:
- več podrobnosti,
- več informacij,
- večjo porabo procesorskega časa,
- večjo velikost slike.

Če je na sliki objekt, bo pri prostorski ločljivosti **100 pikslov na mm** en milimeter objekta opisan s 100 piksli. Pri prostorski ločljivosti **1 piksel na mm** bo isti milimeter opisan le z enim pikslom.

Če podrobnosti niso pomembne in nas zanimajo le **grobe oblike**, si lahko privoščimo zmanjšanje prostorske ločljivosti. To bo pomenilo, da se bo del informacij iz slike posledično izgubil (detajli se zlijejo z večjimi področji). Manjša prostorska ločljivost pa bo posledično pomenila tudi manjšo velikost slike.

###### Pomen prostorske ločljivosti v praksi

Brez podane prostorske ločljivosti (npr. pri medicinskem slikanju) bi zdravniku lahko povedali le, da je tumor velik **35 pikslov**, kar nima pravega pomena. Ko pa poznamo prostorsko ločljivost, lahko isto informacijo izrazimo v realnih merah, na primer: približno 2 mm. To omogoča smiselno interpretacijo slike v realnem svetu.

---

Pikslu \(p = [i, j]\) lahko v sliki \(I\) definiramo njegove sosede (tj. sosednje piksle) na dva načina:

- **v 4-sosedstvu**
- **v 8-sosedstvu**

**4 sosedstvo** pomeni da bomo imeli 4 sosede. To so tisti piksli s kateri ima naš piksel skupno stranico.
Če bi stvar posplošili v 3D-nimamo piksel, ampak imamo voksel(x,y,z). Ima toliko sosedov kolikor ima skupnih ploskev (6 sosedov). 

**8 sosedstvo** pa pomeni, da ima piksel 8 sosedov. 4 piksli so tisti s katerimi si deli stranico, ostale 4 piksli pa so še tisti s katerimi se dotika v kotih. V 3d bi pa imeli prav tako tiste s katerimi se stika na vogalih-skupaj 26 pikslov. (3x3x3-1)-pri tem računamo še -1, da odštejemo ta piksel, ki ga opazujemo oz. od katerega sosede gledamo.

Sosedstvo je pomembno v funkcijah, kjer moramo določiti, v kakšnem okolju naj algoritmi upoštevajo sosede piksle ali voksle.

---

### Uporabljene oznake

- **Konsistentnost uporabljenih oznak** skozi zapiske.  
- **Vektorji** – majhne ali velike črke, zapisane krepko (odvisno od opazovanega prostora).  
  *Primer:* vektor **b** = [b₀, b₁, ..., bₙ₋₁], vektor **A**  
- **Matrike** – velike črke, zapisane v *sans-serif* pisavi.  
  *Primer:* matrika **A**  
- **Slika** – I  
- **Zaporedje 2D-slik** – I  
- **Velikost slike (št. vrstic in stolpcev)** – M × N  
- **Piksel** – p = [i, j]  
- **Točke, premice in ravnine v prostoru** – črke zapisane *kurzivno*.  
  *Primer:* ravnina Π  
- **Funkcije** – velike črke, zapisane v *kaligrafski pisavi*.  
  *Primer:* funkcija F()  
- **Standardni odklon** – σ  
- **Povprečje** – \(\bar{p}\)  
- **Absolutna vrednost** – |p|  
- **Delta (Δ)** – znak delta, označba za spremembo ali razliko vrednosti (npr. Δx = sprememba v x)

---

### Operacije nad slikami

**Operacije nad slikami** so podobne matričnemu računu in jih opravljamo na nivoju istoležnih pikslov.

- **Seštevanje/odštevanje slik:**  
  \[
  C = A \pm B \quad \Rightarrow \quad C(i,j) = A(i,j) \pm B(i,j)
  \]

  > Seštevanje/odštevanje slik-vzamemo istoležne piksle iz slike A in istoležne piksle iz slike B in jih seštejemo.

- **Množenje/deljenje slik:**  
  \[
  C = A \cdot / B \quad \Rightarrow \quad C(i,j) = A(i,j) \cdot / B(i,j)
  \]

  > Množenje/deljenje slik-vzamemo ij-ti piksel iz prve slike in ij-ti piksel iz druge slike in shranimo rezultat na ij-ti piksel v rezultatu.

- **Množenje s skalarjem:**  
  \[
  C = \alpha A \quad \Rightarrow \quad C(i,j) = \alpha A(i,j)
  \]

- **Kvadriranje slik:**  
  \[
  C = A^2 \quad \Rightarrow \quad C(i,j) = (A(i,j))^2
  \]

## Model kamere in zajemanje slik

### Zajemanje slik s kamerami CCD

#### Proces formiranja slike

Kako pridemo do slike?  

Imamo **fotoaparat** – leče, zaslonko, zadaj imamo film ali danes senzor. Ko pritisnemo gumb za slikanje, se zaslonka odpre, svetloba pride na senzor in slika se shrani na pomnilni medij.

Danes digitalni fotoaparati temeljijo na **senzorju**, občutljivem na svetlost. Temu seznoru pravimo **CCD senzor**. Poleg njega pa je še **CMOS senzor**, ki se pogosto uporablja pri fotoaparatih na telefonih. Ta senzor je cenejši, vendar deluje podobno kot CCD.  

---

##### Senzor CCD

Senzor CCD je običajno pravokotne oblike in razdeljen na posamezne elemente, ki so zloženi v matriki po vrsticah in stolpcih. Vsak elementek CCD je občutljiv na svetlost in iz njega nastane **en piksel**. Elementke CCD si lahko predstavljamo kot kvadratne "koše", ki zbirajo svetlobo. Vsako polje lahko meri količino svetlobne energije, ki pade nanjo, pri čemer se količina svetlobna energije, ki pade na dano polje meri skozi neko določeno časovno obdobje.

---

##### Svetloba in fotoni

Svetloba sestoji iz **fotonov**, ki jih lahko predstavljamo kot žogice. Ko pritisnemo sprožilec, svetloba pride skozi lečo in zaslonko do senzorja. V kvadratne "koše" se ujame več fotonov tam, kjer je svetloba močnejša, in manj fotonov tam, kjer je temneje. **Večja svetlost bo pomenila večji naboj v elementku CCD.**

To je bil sedaj opisan prvi korak, kjer smo akumulirali svetlobni naboj. Sedaj sledi pretvorba tega ujetega svetlobnega naboja v sliko.

---

##### Pretvorba svetlobnega naboja v sliko

Akumulirani svetlobni naboj pretvorimo v **zvezni signal** (napetost v odvisnosti od časa). Pretvorba poteka **vrstico po vrstici**, podobno kot igra "4 v vrsto": spodnja vrstica se obdeluje prva. Začnemo s spodnjo linijo našega senzorja (matrike) in naboj pretvorimo v zvezni signal (napetost v odvisnosti od časa). Višji kot je svetlobni naboj notri, višja bo napetost in večja bo amplituda (podobno je obratno-nižji bo naboj notri, manjša bo napetost). Vrstico za vsak element pretvorimo v vrednost svetlobnega signala. Na koncu pride kontrolni signal in se vrstica shrani (posreduje v serijski izhodni register). Nato gre naslednja vrstica po podobnem postopku notri za obdelavo.  

Za tem korakom sledi diskretizacija signala.

---

##### Diskretizacija in AD pretvorba

Register posreduje prejet naboj polja (enega na enkrat) v izhodni **ojačevalnik**, ki zgenerira ustrezen analogni oz. zvezni signal, pri čemerdobimo v signalu večje razlike. Ta signal gre nato v **AD pretvornik**, da pretvorimo analogni signal v digitalni signal (diskretizacija). V fotoaparatih je čas vzorčenja oz. trenutki ko bo signal diskretniziran (\(\Delta T\)) tovarniško zapečeno. Ta vrednost določa koliko vzorcev moremo dobit, da lahko dobimo vsako vrstico.

Če napetost preseže maksimalno vrednost \(U_\text{MAX}\), AD pretvornik odreže višek. AD pretvornik shrani vrednosti v **register**, običajno 8-bitni, ki lahko hrani **256 različnih nivojev** (od 0 do 255). Vsak ta nivo dobi neko številko oz. indeks. Po AD pretvorbi dobimo **matriko**, ki je enake velikosti in ima enako število elementov kot senzor CCD.  

Postopek ponavljamo za vse vrstice senzorja. Za eno vrstico dobimo signal, to damo v AD pretvornik. V posameznem trenutku ne vrnemo napetost, ampak številko nivoja v katerega je svetlobna točka padla. Ko pridemo do kontrolnega signala vzamemo naslednjo vrstico in spet pretvorimo. 

Branje oz. formiranje slike, po tem postopku, se lahko ponovi večkrat na sekundo (npr. 30 fps), lahko pa traja tudi več ur (npr. v astronomiji).

Za korakom diskretizacije sledi shranjevanje slike.

---

##### Shranjevanje slike

Matriko na koncu shranimo v **pomnilnik** – to je slika v surovem formatu. Pri videu se ta postopek zgodi večkrat na sekundo.

---

Zgoraj opisan postopek velja za sivinsko sliko. Pri barvni sliki pa so potrebni za vsako barvo 3 komponente RGB. Kako priti torej do barvnih slik?

Obstajata 2 pristopa:
- **single-shot** (zaslonka se 1x odpre)
- **multi-shot** (zaslonka se večkrat odpre)

Dodatno pa glede na ceno obstaja še ločitev na **cenejši** in **dražji način**.

---

##### Single-shot

Eden cenejših pristopov za zajem barvne slike je **single-shot** metoda. Svetloba je sestavljena iz različnih valovnih dolžin, pri čemer nas pri barvnem zajemu zanimajo tri osnovne komponente: **rdeča (R), zelena (G) in modra (B)**.  

Če senzor ni opremljen z nobenim filtrom, se fotoni sicer ujamejo, vendar dobimo le sivinsko sliko brez barvnih informacij. Zato se pri single-shot pristopu uporablja **barvni filter**, najpogosteje **Bayerjev filter**. Z njim se izvede postopek Bayerjevega demoziciranja s čimer dobimo digitalno barvno sliko.

Bayerjev filter je razporejen v matriki:
- v eni vrstici se izmenjujeta rdeča in zelena barva,
- v naslednji vrstici pa zelena in modra barva.
Gre za interpoliranje podatkov na osnovi vrednosti sosednjih pikslov.

Filter mora biti dovolj velik, da prekrije celoten senzor. Če je posamezen CCD element prekrit z rdečim filtrom, bo zaznal le rdeče fotone, medtem ko se zeleni in modri izgubijo. Enako velja za zelene in modre filtre – vsak element zazna le eno barvno komponento.

###### Single-shot – cenejša rešitev

Pri tej rešitvi imamo še vedno **en sam CCD senzor**, pretvorba signala pa poteka podobno kot pri sivinski sliki. Razlika je v tem, da vsak piksel izmeri **le eno barvno komponento**, za popoln RGB zapis pa potrebujemo še preostali dve.

Manjkajoči barvni komponenti se določita **hevristično z interpolacijo** iz sosednjih pikslov. Na primer:  
če je pri nekem pikslu izmerjena zelena vrednost, se rdeča in modra komponenta izračunata s pomočjo interpolacijskih funkcij in vrednosti bližnjih pikslov.

Na ta način dobimo tri matrike:
- matriko rdeče barve (R),
- matriko zelene barve (G),
- matriko modre barve (B).

To predstavlja osnovni **single-shot pristop**, ki je cenovno ugoden, vendar manj natančen.

###### Single-shot – dražja rešitev

Dražja rešitev predpostavlja uporabo **treh senzorjev**, pri čemer je vsak namenjen določenemu barvnemu spektru (R, G ali B). Najdražji del sistema sta senzor in leča.

Ena izmed izvedb je, da so senzorji zloženi kot nekakšen **sendvič** in izdelani iz posebnih materialov, ki prepuščajo le določeno valovno dolžino svetlobe. Tako vsak senzor neposredno zajame svojo barvno komponento brez potrebe po interpolaciji.

Druga rešitev pa je da imamo 3 senzorje, ki so prostorsko razmaknjeni po fotoaparatu, ki ima na vhodu stekleno prizmo. Sem noter pride svetloba, ki se na tej prizmi nato lomi. Imamo 3 senzorje in svetloba se lomi na enega od treh senzorjev. Fotoni se zgrabijo na pravilen senzor s pomočjo steklene prizme, ki razprši to svetlobo. Za vsaki senzor treba ponoviti to zgodbo enako kot prej-to je natančneje, ampak je zato tudi dražje.

---

##### Multi-shot

###### Multi-shot pristop

Multi-shot metoda ne pomeni, da uporabnik večkrat ročno pritisne sprožilec, temveč da se **zaslonka samodejno odpre večkrat**, običajno trikrat – enkrat za vsako barvno komponento. Senzor se tukaj zaporedoma 3x v zelo kratkem časovnem intervalu izpostavi svetlobi (sceni). Pri tem se ob odpiranju zaslonke pred senzor položi filter, ki prepušča le določeno barvno komponento.

Pri tem uporabljamo različne vrste filtrov. Ti so lahko mehanski ali akustični. Pri mehanskih filtrih je pred senzorjem nameščen filter, ki prepušča določeno barvo:
1. najprej rdečo – zajame se rdeča komponenta,
2. nato se filter zamenja in zajame modra komponenta,
3. na koncu še zelena komponenta.

Vsaka barva se zajame ločeno, nastali signali pa se združijo v končno barvno sliko.

Ta pristop ni primeren za hitro spreminjajoče se scene, saj lahko pride do **zamegljenosti**, zato se uporablja predvsem pri statičnih prizorih.

---

##### Velikost senzorjev

Senzorji so lahko zelo majhni, poznamo pa tudi **full-frame senzorje**, ki so bistveno večji. Velikost senzorja in posameznih elementov močno vpliva na kakovost slike.

Če na zelo majhen senzor pade velika količina fotonov, se kakovost slike poslabša. Zato velja, da so **večji senzorji in večji piksli praviloma boljši**, saj omogočajo boljši zajem svetlobe.

---

### Modeli kamer

V računalniškem vidu je pri določenih aplikacijah nujno razumeti **matematično formiranje slike** – torej kako se slika opiše z matematičnimi modeli.

Obravnavali bomo:
- matematične modele kamere,
- načine, kako proces zajema slike opisati z matematičnimi formulami.

Modela, kot sta **kamera obskura** in **kamera s tankimi lečami**, sta pogosto preveč poenostavljena, medtem ko je **kamera z lečami** najbolj realističen model.

---

#### Kamera na luknjico (camera obscura)

**Kamera na luknjico** je eden najstarejših modelov kamere, poznan že v času Aristotla. Gre za zelo preprosto napravo, ki jo sestavljata majhna odprtina (luknjica) in slikovna ravnina. Scena pred kamero se skozi odprtino preslika na notranjo, hrbtno stran kamere, kjer nastane obrnjena slika. Delovanje kamere na luknjico temelji na **perspektivni projekciji**.

Luknjico lahko matematično obravnavamo kot **eno samo točko v prostoru**. Iz vsake točke opazovane scene potuje svetlobni žarek, ki gre skozi luknjico in se projicira na slikovno ravnino. Točka na sliki nastane tam, kjer ta premica seka slikovno ravnino. Na ta način se vsaka točka v prostoru preslika v ustrezno točko na sliki.

Zaradi perspektivne projekcije se velikost objektov na sliki spreminja glede na njihovo oddaljenost od kamere. Če imamo dva enako velika predmeta, ki se nahajata na različnih razdaljah od kamere, bo:
- bolj oddaljen predmet na sliki videti manjši,
- bližji predmet pa večji,

čeprav sta v resničnem svetu enake velikosti. Ta opisan **perspektivni efekt** je ena ključnih lastnosti perspektivne projekcije.

Stari fotoaparati so za zajem slike uporabljali **fotografski film**. Po zajemu je bilo film potrebno razviti v temnici, kjer so ga s posebnimi kemičnimi tekočinami obdelali, da se je slika trajno zapisala.

##### Koordinatni sistem kamere na luknjico

Kameri na luknjico priredimo koordinatni sistem:

- $O$ – izhodišče je v luknjici  
- $\Pi'$ – slikovna ravnina  
- $\mathbf{i}$ in $\mathbf{j}$ – bazna vektorja ravnine, ki je paralelna ravnini $\Pi'$  
- $f'$ – oddaljenost ravnine $\Pi'$ od luknjice v smeri vektorja $\mathbf{k}$ (merjeno pozitivno)  
- $C'$ – slikovni center (središče)  
  - leži na presečišču optične osi in ravnine $\Pi'$  

- Optična os:
  - je pravokotna na ravnino $\Pi'$
  - poteka skozi luknjico

- Točko $C'$ lahko uporabimo kot izhodišče slikovne ravnine  
  - pomembno za kalibracijo kamere

##### Kako določimo za točko v sceni njen položaj na sliki?

Glede na definiran koordinatni sistem imamo torej projekcijsko oz. slikovno ravnino, ki jo definiraza bazna vektorja $\mathbf{i}$ in $\mathbf{j}$. Imamo pa še točko $P$, ki se preko perspektivne projekcije preslika v točko $P'$.

- Točka $P$ – točka iz scene  

$$
P = [x, y, z]
$$

- Točka $P'$ – slika točke $P$ na slikovni ravnini  

$$
P' = [x', y', z']
$$

- Točka $P'$ leži na slikovni ravnini, zato velja:

$$
z' = f'
$$

- Koordinati $x'$ in $y'$ določimo iz opazovanja geometrije (perspektivna projekcija):

$$
x' = \frac{f' x}{z}
$$

$$
y' = \frac{f' y}{z}
$$

Zanima nas določitev koordinat točke $P'$.  
Poznamo koordinate točke $P$:

$$
P(x, y, z)
$$

Te koordinate so podane v nekih merskih enotah, npr.:

$$
P(100, 200, 450)
$$

kjer vrednosti lahko predstavljajo centimetre (lahko pa tudi dm, m itd.).

Točka $P$ se preko **perspektivne projekcije** preslika v točko $P'$.

Točka $P'$ ima koordinate:

$$
P'(x', y', z')
$$

Ker točka $P'$ leži na slikovni ravnini, velja:

$$
z' = f'
$$

Vprašanje pa je, kako določimo $x'$ in $y'$.  
To določa matematični model perspektivne projekcije:

$$
x' = f' \left(\frac{x}{z}\right)
$$

$$
y' = f' \left(\frac{y}{z}\right)
$$

Ti dve formuli povesta, kako se točka preslika na slikovno ravnino.

Pomembno:  
$x'$, $y'$ in $z'$ so še vedno izraženi v isti merski enoti kot $x$, $y$, $z$. **Tukaj še ne govorimo o pikslih.**  
Če so $x, y, z$ podani v cm, so tudi $x', y', z'$ v cm.

> Primer
>
>Podano imamo točko $P$ s koordinatami ($x, y, z$), ter podatek za oddaljenost ravnine od luknjice ($f'$):
>
> $$ P(100, 200, 450), \quad f' = 150 $$
>
> Zanima nas določitev koordinat točke $P'$. Ker točka $P'$ leži na slikovni ravnini, velja $z' = f'$. V tem primeru to pomeni, da je $z' = 150$. Določiti moramo torej $x'$ in $y'$.
>
> Izračun:
>
> $$ x' = f' \cdot \left(\frac{x}{z}\right) = 150 \cdot \left(\frac{100}{450}\right) = 33{,}3 $$
>
> $$ y' = f' \cdot \left(\frac{y}{z}\right) = 150 \cdot \left(\frac{200}{450}\right) = 66{,}6 $$

##### Omejitve modela kamere na luknjico

Model kamere na luknjico je nekoliko **preoptimističen**, saj predpostavlja, da je luknjica idealna točka. V resnici pa ta luknjica ni matematična točka, ampak ima določeno ploščino, predstavlja odprtino (npr. krožno), skozi katero v praksi ne prehaja le en žarek ampak več žarkov. Ker skozi odprtino prehaja več žarkov, se preslikana točka na slikovni ravnini nekoliko **razmaže** (ni popolnoma ostra). Manjša kot je odprtina, manjša je razmazanost.

Zato v model kamere uvedemo **leče** (običajno pred odprtino). S tem imamo luknjico, pred njo pa zbiralne (konveksne) leče.

Leče omogočijo:
- boljšo fokusacijo žarkov,
- ostrejšo sliko,
- bolj realističen model kamere.

---

#### Model s tankimi lečami

Lastnost zbiralne leče katera sestavlja ta model je, da **fokusira oziroma zbira žarke**. Žarki, ki izhajajo iz iste točke, se zaradi leče ne razpršijo, temveč se na koncu zberejo v eni točki na slikovni ravnini. Lastnosti leče določata dve goriščni točki. Ti dve točki sta na razdalji $f$, kjer je $f$ **goriščna razdalja** leče.

##### Koordinatni sistem modela s tankimi lečami

Koordinatno izhodišče sedaj postavimo v **središče leče**.

Ponovno imamo točko:

$$
P(x, y, z)
$$

Podobno kot pri sistemu modela kamere na luknjico, nas tudi sedaj zanima kam na slikovni ravnini se preslika dana točka $P$. Ker imamo odprtino, skozi lečo potuje več žarkov iz iste točke.

Pri tem na zbiralni leči obravnavamo tri značilne (mejne) primere (žarke):

- Žarek, ki je **vzporeden optični osi**, se po prehodu skozi lečo lomi skozi drugo gorišče in se nato seka s slikovno ravnino.

- Žarek, ki gre ravno skozi **središče leče**, se ne lomi in potuje naravnost do slikovne ravnine.

- Žarek, ki gre skozi **prvo goriščno točko**, se po prehodu skozi lečo lomi tako, da postane vzporeden optični osi, nato pa se seka s slikovno ravnino.

> [!IMPORTANT]
> Če je objekt (npr. točka $P$) na ustrezni razdalji, se vsi trije žarki zberejo v isti točki na slikovni ravnini. **VENDAR TO NE VELJA VEDNO!**. Velja samo takrat, ko je objekt (npr. točka $P$ v našem primeru) na primerni razdalji od slikovne ravnine, da se bodo dani žarki zbrali v isti točki. V takem primeru je scena v **ostrem fokusu** in velja relacija oziroma enačba:
>
> $$\frac{1}{z'} - \frac{1}{z} = \frac{1}{f}$$
>
> kjer:
> - $z$ predstavlja razdaljo objekta,
> - $z'$ predstavlja razdaljo slike,
> - $f$ predstavlja goriščno razdaljo.
>
> Če ta pogoj ni izpolnjen, se žarki ne zberejo v eni točki in slika ni ostra.

**FOV (Field of View)** predstavlja del scene, ki se projicira na senzor oziroma kamero.

FOV je odvisen od:
- lastnosti leče,
- velikosti senzorja.

To je tisti del prostora, ki ga kamera "vidi".

##### Omejitve modela

Idealnih tankih leč s popolnimi lastnostmi v praksi ne moremo izdelati. Zato je tudi model "kamera na luknjico z lečo", še vedno nekoliko **preoptimističen matematični model** realne kamere.

---

#### Model z debelimi lečami

Najbolj realističen model je **model kamere z debelimi lečami**. To je najboljši približek dejanskemu fizikalnemu dogajanju v kameri.

Debela leča je poleg:

- dveh goriščnic,
- goriščne razdalje $f$,

opisana še z:

- **glavnima točkama leče**,
- **razdaljo med njima**.

S temi parametri lahko natančneje opišemo obnašanje debele leče.

##### Koordinatni sistem modela z debelimi lečami

Ponovno nas zanima:

- kako se točka projicira na slikovno ravnino,
- kako se žarki lomijo oziroma zbirajo.

Tudi debela leča ima lastnost zbiranja žarkov, vendar je model nekoliko bolj kompleksen kot pri tanki leči.

Pri modelu debele leče obravnavamo tri značilne primere:

- Žarek, ki je **vzporeden optični osi**, se lomi tako, da pri drugi glavni točki spremeni smer in se pod določenim kotom preslika na slikovno ravnino.

- Žarek, ki gre skozi **prvo gorišče**, se po lomljenju usmeri tako, da postane vzporeden optični osi.

- Žarek, ki zadene **prvo glavno točko**, se preslika skozi drugo glavno točko in nato seka slikovno ravnino.

---

##### Omejitve modela

Tudi ta model je še vedno **preoptimističen**, saj popolne leče v praksi ne moremo izdelati.

V realnih sistemih se pojavljajo:
- geometrijska popačenja,
- optične aberacije,
- druge nepravilnosti.

---

### Parametri kamere

Ne glede na to, kateri model uporabimo (luknjica, tanka leča, debela leča), ostajamo pri istem osnovnem principu:

Imamo točko v prostoru:

$$
P(x, y, z)
$$

Ta točka se preslika na slikovno ravnino v koordinatah, ki so še vedno izražene v **merskih enotah** (npr. cm, mm). V praksi pa kamera na koncu ne vrne koordinat v centimetrih, temveč **pikslih**.

> [!IMPORTANT]
> **Notranji parametri kamere** omogočijo preslikavo iz sveta merskih enot v svet pikslov. Tako dobimo končno digitalno sliko, kjer je vsaka točka predstavljena kot piksel.

Če želimo uporabiti matematične enačbe projekcije, pa moramo poznati **koordinatni sistem naše kamere**. Za dosego tega, pa je potrebno točke, ki smo jih dobili iz koordinatnega sistema v naravi pretvorit v koordinatni sistem, kot bi ga zajela naša kamera. Določitev tega nam omogočajo **zunanji parametri kamere**.

> [!IMPORTANT]
> **Zunanji parametri kamere** so potrebni za merjenje razdalj, ter opis lege in orientacije v prostoru. Zunanji parametri kamere so potrebni, ker ne znamo neposredno meriti lokacije točke glede na koordinatni sistem kamere in moramo svetovni koordinatni sistem pretvoriti v koordinatni sistem kamere.

#### Notranji parametri kamere

Imamo koordinatni sistem kamere in znamo izmeriti lokacijo točke glede nanj. V kamero vstavimo **CCD senzor**. Tudi za senzor lahko vpeljemo koordinatni sistem.

- Izberemo koordinatno izhodišče.
- Glede na izhodišče štejemo piksle.

Na ta način preslikamo točke iz koordinatnega sistema kamere v koordinatni sistem v pikslovnem sistemu.

Na senzorju se nahaja **središče slikovne ravnine**, vendar pikslov ne merimo glede na sredino senzorja.

Piksle začnemo šteti od:

- vrstice: 0, 1, 2, 3, ...
- stolpca: 0, 1, 2, 3, ...

in **ne uporabljamo negativnih števil**. Zaradi tega koordinatno izhodišče slikovnega sistema ni v središču senzorja, temveč v enem od njegovih vogalov.

##### Glavna točka – parametra \( u_0 \) in \( v_0 \)

Prva dva notranja parametra sta:

- \( u_0 \) – premik v smeri vrstic
- \( v_0 \) – premik v smeri stolpcev

Ta dva parametra določata, kje se nahaja **koordinatno izhodišče** glede na pikslovni koordinatni sistem.

##### Parametra \( \alpha \) in \( \beta \)

Naslednja dva notranja parametra sta:

- \( \alpha \)
- \( \beta \)

V teh dveh parametrih je skrita **velikost piksla**.


> [!WARNING]
> \( \alpha \) in \( \beta \) nista neposredno velikosti piksla, temveč predstavljata produkt goriščne razdalje in prostorske ločljivosti. Pri tem je \( \alpha \) prostorska ločljivost v smeri \( x \), \( \beta \) pa prostorska ločljivost v smeri \( y \).

Velja:

- \( \alpha = f \cdot s_x \)
- \( \beta = f \cdot s_y \)

kjer:
- \( f \) – goriščna razdalja,
- \( s_x \) – prostorska ločljivost v smeri \( x \),
- \( s_y \) – prostorska ločljivost v smeri \( y \).

Ključni namen teh parametrov je:

> prehod iz merskih enot (cm, mm) v svet pikslov.

##### Kot theta \( \theta \)

Mi uvedemo koordinatni sistem, ki je enak velikosti našega senzorja. Kot med baznimi vektorji je \( 90^\circ \) stopinj, ampak v praksi takšnega senzorja ne znamo naredit, da bi imel točno \( 90^\circ \). Zato rečemo, da je kot med osema (osema po vrsticah in stolpcih) kot \( \theta \). To je kot med osjo vrstic in osjo stolpcev.

Parameter \( \theta \) opisuje napako pri izdelavi senzorja (odstopanje od pravokotnosti).

##### Pet notranjih parametrov kamere

Skupaj imamo torej 5 notranjih parametrov:

1. \( u_0 \) – premik kamere v smeri vrstic
2. \( v_0 \) – premik kamere v smeri stolpcev
3. \( \alpha \) – skaliranje v smeri \( x \)
4. \( \beta \) – skaliranje v smeri \( y \)
5. \( \theta \) – kot med osema

Pomen:
- 2 parametra za premik koordinatnega sistema,
- 2 parametra za pretvorbo iz cm (oz. merskih enot) v piksle,
- 1 parameter za napako pri izdelavi senzorja.

##### Kalibracijska matrika \( K \)

Iz teh parametrov lahko sestavimo **kalibracijsko matriko** velikosti \( 3 \times 3 \):

\[
K =
\begin{bmatrix}
\alpha & -\alpha \cot \theta & u_0 \\
0 & \dfrac{\beta}{\sin \theta} & v_0 \\
0 & 0 & 1
\end{bmatrix}
\]

Ta matrika omogoča prehod iz koordinat kamere v pikslovni sistem. S pomočjo te matrike naredimo projekcijsko matriko $M$ velikosti \( 3 \times 4 \) oz. perspektivno projekcijsko matriko.

##### Projekcijska matrika

S pomočjo notranjih in zunanjih parametrov dobimo **projekcijsko matriko**:

\[
M = K [R , t]
\]

Imenujemo jo tudi **perspektivna projekcijska matrika** in je velikosti \(3 \times 4\).

##### Model kamere – matrična enačba

Model kamere je zapisan kot:

\[
p = \frac{1}{z} M P
\]

##### Homogene koordinate

Točka v prostoru:

\[
P = (x, y, z)
\]

v homogenih koordinatah zapišemo kot:

\[
P = (x, y, z, 1)
\]

Dodamo pa ji še četrto komponento oziroma dimanzijo z vrednostjo 1, da lahko izvajamo matrični račun.

##### Projekcija

- \( P \) – točka v prostoru (v homogenih koordinatah)
- \( p \) – projicirana točka na sliki

Mala črka \( p \) predstavlja slikovno točko po projekciji.

To predstavlja celoten matematični model kamere:
3D točka → projekcija → 2D piksel.

---

#### Zunanji parametri kamere

Poleg notranjih parametrov pa potrebujemo tudi **zunanje parametre kamere**.

Imamo koordinatni sistem kamere, vendar v realnosti ne moremo meriti prostora neposredno glede na središče leče.

Običajno imamo:

- referenčni realni (world) koordinatni sistem,
- merilni sistem (npr. laser), s katerim izmerimo koordinate točk v prostoru.

Točke, ki jih izmerimo z laserjem, so podane v **world koordinatnem sistemu**. Za model kamere pa potrebujemo točke v **koordinatnem sistemu kamere**. Zato moramo pretvoriti točke iz realnega (world) koordinatnega sistema v koordinatni sistem kamere. S tem dobimo točke, ki bi jih imeli, če bi laser šel iz kamere.

##### Povezava koordinatnih sistemov

Imamo torej dva koordinatna sistema:

- svetovni (world) koordinatni sistem
- koordinatni sistem kamere

Da ju pa povežemo in da lahko izvedemo pretvorbo iz enega koordinatnega sistema v drugega, moramo izvesti:

1. **Translacijo** (poravnava izhodišč)
2. **Rotacijo** (poravnava osi)

###### Translacija

Translacija je podana s tremi parametri:

- premik po osi \( x \)
- premik po osi \( y \)
- premik po osi \( z \)

To zapišemo kot translacijski vektor:

\[
t =
\begin{bmatrix}
t_x \\
t_y \\
t_z
\end{bmatrix}
\]

###### Rotacija

Rotacijo definiramo s tremi koti:

- rotacija okoli osi \( x \)
- rotacija okoli osi \( y \)
- rotacija okoli osi \( z \)

Te kote običajno označimo kot:

\[
\alpha, \beta, \gamma
\]

Rotacijo izvedemo kot kompozitum rotacij:

1. najprej okoli osi \( x \),
2. nato okoli osi \( y \),
3. nato okoli osi \( z \).

Rotacijsko matriko zapišemo kot kompozitum rotacij:

\[
R = R_x R_y R_z
\]

kjer so

\[
R_x =
\begin{bmatrix}
1 & 0 & 0 \\
0 & \cos \alpha & \sin \alpha \\
0 & -\sin \alpha & \cos \alpha
\end{bmatrix}
\]

\[
R_y =
\begin{bmatrix}
\cos \beta & 0 & -\sin \beta \\
0 & 1 & 0 \\
\sin \beta & 0 & \cos \beta
\end{bmatrix}
\]

\[
R_z =
\begin{bmatrix}
\cos \gamma & \sin \gamma & 0 \\
-\sin \gamma & \cos \gamma & 0 \\
0 & 0 & 1
\end{bmatrix}
\]

\* Koti so merjeni v protiurni smeri.

Zunanji parametri so torej:

- 3 parametri translacije
- 3 parametri rotacije

Skupaj 6 \text{ zunanjih parametrov}

S temi parametri podamo transformacijo med obema koordinatnima sistemoma.

S zunanjimi in notranjimi parametri imamo sedaj imamo popoln model kamere. Imamo 5 notranjih in 6 zunanjih parametrov kamere. Te parametre pa moremo nekje dobit-temu pravimo **kalibracija kamere**.

---

### Geometrijsko kalibriranje kamer

#### Parametri kamere in kalibracija

Notranji parametri kamere modelirajo lastnosti kamere. Omogočajo pretvorbo merskega sveta (realnih enot) v svet pikslov, tako da na koncu dobimo sliko v pikslih. Za to so zadolženi **notranji parametri kamere**. Skupaj imamo **5 notranjih parametrov kamere**.

Drugi nabor parametrov so **zunanji parametri kamere**. Vse točke v sceni bi morali meriti glede na koordinatni sistem kamere, kar je v praksi nemogoče. Zato potrebujemo referenčni (world) koordinatni sistem, katerega v koordinatni sistem kamere pretvorijo zunanji parametri kamere. Skupaj imamo **6 zunanjih parametrov kamere**.

Ali nam lahko kdo poda vseh 11 parametrov kamere?

**Notranji parametri**
Nemogoče je izdelati dve popolnoma enaki kameri. Tudi če je leča izdelana strojno, bo druga leča vedno nekoliko drugačna.

**Zunanji parametri**
Te je še težje podati. Položaj točk v prostoru merimo glede na nek referenčni koordinatni sistem, kar prav tako ni popolnoma natančno oziroma neposredno podano.

Zato je nemogoče, da bi nam nekdo enostavno "serviral" vse parametre kamere. Potrebujemo **kalibriranje kamere**. Geometrijsko kalibriranje pomeni, da se naučimo (ocenimo) parametre kamere.

Potrebujemo **korespondenčne pare**:

- poznano neko točko v prostoru, npr.  
  \[
  P_1 = (x_1, y_1, z_1)
  \]
  katere koordinate poznamo,
- ter piksel na sliki, v katerega se ta točka preslika.

Takšne pare zapišemo kot:

\[
\{ (P_i, p_i) \}
\]

kjer:
- \(P_i\) predstavlja točko v prostoru,
- \(p_i\) pa njen pripadajoči piksel na sliki.

Potrebujemo torej točke v prostoru, za katere vemo, v kateri piksel se preslikajo. 

S pomočjo **kalibracijskega objekta** dosežemo, da moramo neposredno izmeriti samo 1 ali 2 točki, nato pa lahko iz njih določimo še vse ostale točke.

Kalibracijo lahko izvedemo tudi ročno, tako da sami izberemo določene točke. Vendar je tak pristop časovno potraten.

Vse kalibracijske metode so **optimizacijske metode**.

Imamo matematični model kamere:

\[
p = \frac{1}{z} M P
\]

kjer:
- \( p \) predstavlja **piksel**,
- \( P \) predstavlja točko v prostoru (v homogenih koordinatah),
- \( M \) je projekcijska matrika.

Neznanka v tej enačbi je **projekcijska matrika \( M \)**.

#### Linearni postopek kalibriranja

Problem linearne metode je, da deluje pravilno le, če imamo **perfektno izmerjene korespondenčne pare**.

V praksi pa vedno pride do napak pri določanju teh točk:
- napaka pri določanju pikslov,
- napaka pri merjenju točk v realnem svetu.

Bolj kot so podatki nenatančni, slabši je rezultat kalibracije.

##### Postopek

Začnemo s projekcijsko enačbo.

Za vsak korespondenčni par \((P_i, p_i)\):

- dobimo **2 enačbi**,
- ki ju zapišemo kot **2 vrstici** v matriki sistema.

Če imamo \( n \) korespondenčnih parov, ima matrika sistema \(2n \text{ vrstic}\), ker iz vsakega para dobimo dve enačbi.

Na primer:
- 1. in 2. vrstica → prvi korespondenčni par
- 3. in 4. vrstica → drugi korespondenčni par
- itd.

Za kalibracijo kamere potrebujemo **12 enačb** (ker ima projekcijska matrika \( M \) 12 elementov). Za vsak korespondenčni par pa dobimo 2 enačbi in 2 vrstici v matriki P. 

Ker iz vsakega korespondenčnega para dobimo 2 enačbi:

\[
\frac{12}{2} = 6
\]

Potrebujemo **minimalno 6 korespondenčnih parov**.

- Če imamo **točno 6 parov**, dobimo eksaktno rešitev.
- Če imamo **več kot 6 parov**, dobimo sistem s presežkom enačb.

V primeru, da imamo več kot 6 parov se pojavijo srednje minimizacije oz. napake, vendar je rezultat te kalibracije boljši. Več korespondenčnih parov kot uporabimo, bolj robusten in natančen je rezultat.

> [!WARNING]
> Pri izbiri točk za kalibracijo:
>
> **TOČKE NE SMEJO LEŽATI V ISTI RAVNINI!**
>
> Če bi vse točke ležale v isti ravnini:
> - bi kalibracija še vedno dala rešitev,
> - vendar bi pri reprojekciji (preslikavi iz pikslov nazaj v realni svet) dobili napake.
>
> Zato morajo biti točke razporejene v prostoru in ne smejo vse ležati na isti ravnini.

#### Geometrijsko kalibriranje kamere

Sistem lahko zapišemo kot:

$$
P \times \mathbf{m} = \mathbf{0}
$$

Dimenzije:

- $P \in \mathbb{R}^{2n \times 12}$
- $\mathbf{m} \in \mathbb{R}^{12 \times 1}$
- $\mathbf{0} \in \mathbb{R}^{2n \times 1}$

(Trivialna rešitev je, da bi $\mathbf{m}$ bil iz samih ničel, to nas ne zanima.)

Ta metoda (geometrijsko kalibriranje kamere), je precej občutljiva – podatki morajo biti zelo točni. Parametri kamere so v projekcijski matriki $M$.

Iz piksla lahko pridemo nazaj v prostor, kar pa brez modela

$$
\mathbf{p} = \frac{1}{z} M \mathbf{P}
$$

ne moremo.

Cilj je narediti sistem računalniškega vida – od zajema do končne odločitve.

## Predobdelava slik

Pri predobdelavi slik sta ključna dva cilja:

1. Želimo popraviti napake, ki so se zgodile pri zajemu slike.
2. V slikah želimo poudariti informacijo, ki nas zanima.

Če imamo vpliv nad okoljem, kjer zajemamo sliko (npr. svetila), potem lahko, če vidimo, da slika ni ustrezna, poskusimo ponovno zajeti sliko, pri tem pa popravimo dejavnike v okolju (npr. osvetlitev, svetila).

Če pa delamo s satelitskimi slikami ali medicinskimi napravami, pa je problem, da se ne moremo vrniti nazaj in slike ponovno zajeti  
Podobno velja tudi za slike v naravi, kjer je veliko odvisno od vremena.

Če se lahko vrnemo, poskusimo sliko popraviti že pri zajemu. Če to ni mogoče, pa moramo problem rešiti programsko.

Če sami načrtujemo (dizajniramo) sistem, lahko veliko stvari izboljšamo že v fazi zasnove. Lažje pa nam je tudi, če poznamo podatke o degradaciji slike (napakah ob zajemu).

Pri obdelavi slik velja:

- Če uporabimo pravo metodo za določeno degradacijo, bo rezultat uspešen.
- Če uporabimo metodo, ki ni primerna za dano degradacijo, lahko sliko še poslabšamo.

Podobno kot pri zdravilih:
- Če vzamemo zdravilo za bolezen, ki je nimamo, nam ne bo koristilo in lahko celo škoduje.
- Enako velja pri obdelavi slik – napačna metoda lahko sliko poslabša.

Slika obstaja v nekem prostoru, obdelava slike pa jo transformira v nov prostor.

Te transformacije:
- povzročijo izgubo določenih informacij,
- niso bijektivne.

Obdelava slik je običajno sestavljena iz več zaporednih transformacij.

> **Operacije pri obdelavi slik**
>
> **1. Točkovne (pixel-to-pixel) operacije**
>
> Pixel-to-pixel operacije delujejo tako, da vzamemo en pixel, ga podamo v neko funkcijo (operacijo) in dobimo nov (spremenjen) pixel. Vsak izhodni pixel je odvisen samo od ustreznega vhodnega pixla.
>
> **2. Lokal­ne operacije (z okolico)**
>
> Pri tej varianti vzamemo pixel, upoštevamo tudi njegove sosednje pixle (okolico), vse skupaj podamo v funkcijo in dobimo ven nov pixel. Izhodna vrednost je torej odvisna od lokalne okolice.
>
> **3. Algoritemske metode**
>
> Gre za kompleksnejše postopke, kjer obdelava temelji na določenem algoritmu, ki lahko vključuje več korakov, pravil ali odločitev.
>
> **4. Globoko učenje**
>
> Sem spadajo globoko učenje (deep learning), nevronske mreže in druge metode umetne inteligence.
>

### Spreminajnje kontrasta

Točkovna operacija deluje tako, da imamo neko sliko in nad vsakim pixlom izvedemo isto transformacijo.

#### Linearizacija sivin

Prvi tak postopek je **linearizacija sivin**.

Imamo formulo:

$$
g' = \frac{Q}{\max - \min} \left( g - \min \right)
$$

Linearizacija se pogosto uporablja za vizualizacijo. Lahko pa se uporablja tudi kot vmesni korak pri nadaljnji obdelavi slike.

#### Histogram sivin

Histogram sivin je vektor (polje), ki ima toliko elementov, kolikor znaša kontrastna ločljivost slike. Posamezen element histograma sivin beleži število pixlov, ki imajo določeno sivinsko vrednost.

Primer:
8-bitna sivinska slika ima 256 sivinskih nivojev. Zato ima histogram 256 elementov in kontrastno ločljivost 256.

Če seštejemo vse elemente histograma, dobimo skupno število vseh pixlov v sliki.

Histogram sivin običajno vizualiziramo s pomočjo **stolpčnih grafov**.

Histogram sivin **ne vsebuje prostorske informacije**.

To pomeni, da v histogramu samo štejemo pixle. Notri v histogramu tako **ni informacije o tem, kje v sliki se posamezni pixli nahajajo**.

Zato lahko:
- dve sliki enake velikosti
- z enakim histogramom sivin

vsebujeta popolnoma različne vsebine.

Pri delu s histogrami sivin poskušamo histogram "razpotegniti", da so sivinske vrednosti čim bolj enakomerno porazdeljene in histogram s tem kar se da uravnan. Najbolj ostri vrhovi na histogramu običajno predstavljajo ključne oziroma bistvene elemente slike. Histogram sivin sam po sebi ni metoda za spreminjanje kontrasta, nam pa pomaga pri analizi kontrasta slike.

##### Metoda: Izenačitev histograma

**Izenačitev histograma** pomeni, da želimo doseči, da so vse sivinske vrednosti približno enako zastopane. V praksi tega popolnoma ne moremo doseči, je pa to cilj metode.

Z vidika kontrasta:

- Najvišje (ostre) vrhove na histogramu raztegnemo,
  da postanejo bolj kontrastni.
- Kjer so doline (manj zastopane vrednosti),
  sklepamo, da informacija ni tako pomembna,
  zato tam lahko izgubimo nekaj podatkov.

> [!WARNING]
> Izenačitev histograma ni isto kot linearizacija!

##### Prenosne funkcije

**Prenosne funkcije** lahko vizualiziramo v grafu prenosnih funkcij.
Če gre prenosna funkcija nad identiteto, potem točkovna operacija sliko posvetli. Če pa gre prenosna funkcija pod identiteto, pa točkovna operacija sliko potemni.

> [!WARNING]
> Linearizacija ne posvetli slike!

---

### Lokalne operacije oz. filtriranje slik

Imamo sliko in izbran pixel.  
Pri filtriranju slik opazujemo:

- izbran pixel
- njegovo okolico

Vzeli bomo ta pixel in njegove sosednje pixle, jih podali v funkcijo, in dobili nov rezultat. Pri tem poznamo točkovne operacije in filtriranje.

#### Točkovne operacije
- Delamo pixel po pixel.
- Lahko uporabljamo isto matriko oziroma sliko za vhod in izhod.
- Vsak pixel je obdelan neodvisno od drugih.

#### Filtriranje
- Uporabljamo pixel in njegovo okolico.
- Potrebujemo **novo sliko (novo matriko)** za zapis rezultatov.
- Ne pišemo nazaj na isto lokacijo (zaradi tega temu pravimo filtriranje, saj imamo vhodno in izhodno filtrirano sliko).

Vprašanje pri filtriranju je, kako določiti funkcijo $F$, ki iz vhodnih vrednosti generira novo vrednost pixla.

Filter si lahko predstavljamo kot **črno škatlo**, nekaj damo notri in dobimo nekaj nazaj ven.

Večina filtrov je:

1. **Linearnih**
2. **Premično neodvisnih**

##### 1. Linearnost

Če imamo dva vhoda $x_1$ in $x_2$:

- Če v sistem podamo $x_1$, dobimo določen rezultat.
- Če podamo $x_2$, dobimo določen **drugačen** rezultat.

Če pa podamo linearno kombinacijo obeh vhodov:

$$
a x_1 + b x_2
$$

potem dobimo na izhodu linearno kombinacijo $x_1$ in $x_2$:

$$
a F(x_1) + b F(x_2)
$$

Ne glede na vrstni red podajanja vhodov, ali prvo damo notri kot vhod $x_1$ in potem $x_2$, ali pa obratno. To je lastnost linearnega sistema.

##### 2. Premična neodvisnost

Sistem je premično neodvisen, če:

- posledica ne prehiteva vzroka,
- odziv sistema ni odvisen od absolutne lokacije, ampak le od relativnega premika.

> Primer:
> Ne slišimo zvoka, če prej ne potrkamo po tabli.

Obnašanje filtra oziroma črne škatle lahko opišemo s pomočjo **enotinega odziva (impulznega odziva)**. Ta popolnoma določa obnašanje linearnega premično neodvisnega sistema.

#### Definicija filtra

##### Določitev filtra

Najprej je potrebno določiti filter. Učinek filtra mora biti tak, kot si ga želimo. Filter je podan z **enotnim (impulznim) odzivom**. Enotni odziv je matrika, ki vsebuje koeficiente (uteži).

Običajno filter označimo s $H$, kjer je $H$ matrika.

##### Matrika filtra (maska)

Tej matriki določimo:

- velikost (dimenzijo),
- vrednosti (koeficiente / uteži).

###### Dimenzija filtra

Velikost oziroma dimenzija filtra določa kako veliko okolico pixla bomo opazovali. Filter položimo tako, da pokrije izbran pixel, ter njegovo okolico. S tem definiramo lokalno območje obdelave.

###### Vrednosti uteži (koeficientov)

Števila (uteži) v matriki določajo kako bo funkcija kombinirala vrednosti pixlov, ter kakšen bo učinek filtriranja.

> [!IMPORTANT]
> Dimenzija maske določa **katero okolico opazujemo**, vrednosti v maski pa določajo **kako jo obdelamo**. To dvoje skupaj določa lastnosti filtra.

##### Implementacija

Implementacijsko je najlažje definirati maske oziroma okolice pikslov kot kvadratno masko (npr. 3×3, 5×5), saj jo lahko preprosto implementiramo s for-zankami.

Če imamo za okolico masko drugačne (ne kvadratne) oblike (npr. krožno ali nepravilno obliko), uporabimo kvadratno matriko, vrednosti, ki jih ne želimo upoštevati, pa nastavimo na 0.

#### filtriranje

Ko imamo enkrat definiran filter, lahko začnemo s filtriranjem. Vsaka maska ima **sredino** (sredinski element maske). Masko navidezno postavimo nad sliko tako, da prekrije del slike. Nato izračunamo **skalarni produkt** med **vrednostmi maske** in **vrednostmi pixlov slike**, ki jih maska prekriva. 

To pomeni:

- vsak pixel množimo z ustrezno vrednostjo v maski,
- vse zmnožke seštejemo,
- dobimo novo vrednost za en pixel izhodne slike.

To je izračun za en pixel.

Za implementacijo potrebujemo 4 for-zanke:

1. Zanka čez vse vrstice za vse piksle slike
2. Zanka čez vse stolpce za vse piksle slike
3. Zanka čez vrstice za vse piksle maske
4. Zanka čez stolpce za vse piksle maske

Skupaj torej 4 for-zanke. Temu postopku pravimo **konvolucija**.

$I$ je vhodna slika.

##### Problemi pri konvoluciji

###### Problem robnih pixlov

Kaj narediti z robnimi pixli, ko del maske pade izven slike?

**Možna rešitev 1: Ničelno dopolnjevanje (zero padding)**

Če maska pade izven slike:

- vrednosti izven slike obravnavamo kot 0
- to pomeni, da vrednosti maske izven slike množimo z 0

Prednost:
- dimenzije vhodne in izhodne slike ostanejo enake.

**Možna rešitev 2: Ocenjevanje manjkajočih vrednosti**

- Manjkajoče pixle si "izmislimo" oziroma jih ocenimo.
- (npr. kopiranje robnih vrednosti, zrcaljenje ipd.)

**Možna rešitev 3: Brez filtriranja robov**

- Če pixel nima vseh sosedov okrog sebe, ga ne filtriramo.
- S tem zmanjšamo dimenzije slike:

  - po vrsticah za $L$
  - po stolpcih za $K$

Slabost:
- Kljub temu, da je ta rešitev najbolj točna, spremenimo z njo dimenzije slike, kar običajno ni zaželeno.

###### Problem vrednosti po filtriranju

Po filtriranju dobimo celoštevilčno vrednost, vendar v realnosti dobimo realna (decimalna) števila, ki po vrednosti padejo izven intervala $[0, 255]$. Teoretično to ni problem, problem pa nastane pri vizualizaciji. Takšne slike namreč ne moremo neposredno prikazati.

Za rešitev tega problema se lahko uporabi:
1. Skaliranje vrednosti nazaj v ustrezen interval
2. Zaokroževanje na celoštevilske vrednosti

###### Še ena dilema: Kje je sredina maske?

Če je dimenzija filtra **liha** (npr. 3×3, 5×5), sredino ni težko določiti. Če pa je filter **sodih dimenzij** (npr. 2×2), pa ni jasno, kaj je sredina maske. Sredino maske poravnamo s pixlom na sliki, vendar kdo določi, kateri element je sredinski?

**To mora določiti avtor filtra!**

> Primer:
> - Pri filtru 2×2 lahko določimo, da je sredina zgornji desni pixel.

---

### Odstranjevanje šuma z lokalnimi operatorji

Šum je moteča komponenta v slikah, ki jo lahko odstranimo s filtri.

Filtri za odstranjevanje šuma zmanjšajo šum, vendar pa vnesejo nove probleme.

Glavni problemi:
- zapacajo (zabrišejo) robove med regijami na sliki.
- robovi med objekti na sliki lahko po filtriranju niso več jasno definirani.

Zato moramo vedno uravnotežiti med **pacanjem robov** in **odstranjevanjem šuma**.

#### Nizko sito (Low-pass filter)

Nizko sito:

- pusti nizke frekvence pri miru,
- visoke frekvence odstrani oziroma zaduši.

> [!WARNING]
> Nizke frekvence NE pomenijo, da imajo piksli nizke vrednosti. Visoke frekvence pa NE pomenijo, da imajo piksli visoke vrednosti. Nizka in visoka frekvenca nista povezani s slikovno funkcijo. Frekvenca ni povezana z absolutno vrednostjo piksla, ampak s hitrostjo spreminjanja slikovne funkcije!

##### Kaj pomeni nizka frekvenca

Opazujemo, kako se vrednosti slikovne funkcije spreminjajo v prostoru.

- Če se vrednosti spreminjajo počasi → nizka frekvenca.
- Če se vrednosti spreminjajo hitro → visoka frekvenca.

Primer nizkih frekvenc:
- enakomerno obarvana stena,
- površina mize (če ni senc ali močnih svetlobnih prehodov),
- območja skoraj enakega odtenka.

---

##### Kaj pomeni visoka frekvenca?

Visoke frekvence nastopijo:

- pri detajlih,
- pri drobnih strukturah,
- na prehodih med različnimi regijami.

Primer:
- prehod iz svetle stene na temno podlago,
- rob med dvema objektoma.

Takrat slikovna funkcija močno "skače" po vrednostih.

---

##### Maska nizkega sita

Nizko sito običajno vsebuje:

- masko poljubne dimenzije (npr. 3×3, 5×5, 11×11),
- vse vrednosti v maski so enake (npr. same enice),
- pred masko je utež za normalizacijo.

Primer:

Če imamo masko dimenzije 11×11:

- ima 121 elementov,
- utež pred masko je $\frac{1}{121}$

Tak filter izračuna **povprečno vrednost v okolici pixla**.

---

#### Visoko sito (High-pass filter)

Visoko sito:

- pusti visoke frekvence pri miru,
- zaduši nizke frekvence.

Deluje torej ravno obratno kot nizko sito.

Takšni filtri delujejo kot:

- detektorji robov,
- poudarjalci detajlov.

Rezultat visokega sita je pogosto večinoma temna slika, z izrazitimi svetlimi točkami ali linijami na mestih robov. Zato rezultat običajno prištejemo ali "pritisnemo" nazaj na originalno sliko, da poudarimo robove in detajle.

#### Gaussov filter

Gre za filter, ki v sliki odstranjuje **bel šum**.

- **Nizko sito** predpostavlja, da so motnje v sliki visoke frekvence.
- **Visoko sito** predpostavlja, da so problem nizke frekvence.
- Pri **gaussovem šumu** pa predpostavimo, da so vse frekvence pokvarjene z nekim deležem.

V tem primeru uporabimo **Gaussov filter**.

Gaussov filter nastane iz **Gaussove krivulje**:

$$
G(x) = \frac{1}{\sqrt{2\pi}\sigma} e^{-\frac{x^2}{2\sigma^2}}
$$

Ta krivulja ima parameter:

- $\sigma$ — standardni odklon

Krivuljo rotiramo okoli osi $y$, s čimer dobimo 2D Gaussovo "kapo". To kapo nato vzorčimo in dobimo matriko filtra.

Parameter $\sigma$ določa:

- kako položna ali strma je krivulja,
- kako močno bo filter glajenje izvajal.

> Primer dveh Gaussovih filtrov:
>
> $$
 H = \frac{1}{16}
 \begin{bmatrix}
 1 & 2 & 1 \\
 2 & 4 & 2 \\
 1 & 2 & 1
 \end{bmatrix}
 $$
>
> in
>
> $$
 H = \frac{1}{10}
 \begin{bmatrix}
 1 & 1 & 1 \\
 1 & 2 & 1 \\
 1 & 1 & 1
 \end{bmatrix}
 $$
>
> Gre za dva filtra enakih dimenzij, vendar z različnimi vrednostmi. Razlika je v vrednosti $\sigma$ (standardnega odklona).

Filtrirna moč je odvisna od $\sigma$.

- Manjša kot je $\sigma$:
  - manj šuma odstranimo,
  - upoštevamo manjšo okolico,
  - filter je ožji.

- Večja kot je $\sigma$:
  - močnejše glajenje,
  - upoštevamo širšo okolico,
  - filter postane podoben nizkemu situ.

Če je $\sigma$ zelo majhen:

- skoraj ne upoštevamo sosednjih pixlov,
- filter postane skoraj nesmiseln,
- pixel praktično množimo sam s seboj.

#### Mediani filter

Mediani filter sodi med **rank value filtre**. Gre za filtre, ki sortirajo vrednosti v okolici pixla, nato pa izberejo določeno vrednost iz urejenega seznama. Pri teh filtrih je pomembna okolica pixla, uteži (koeficienti) pa niso pomembne oziroma jih ti filtri ne uporabljajo.

Postopek uporabe **rank value filtrov**:

1. Položimo masko nad pixel, ki ga filtriramo.
2. NE izvajamo konvolucije.
3. Vzamemo vse pixle iz okolice.
4. Vrednosti sortiramo (od najmanjše do največje ali obratno).
5. Iz sortiranega seznama izberemo določeno vrednost.

Primeri rank filtrov

- **Minimalni filter**  
  → izberemo najmanjšo vrednost iz okolice.

- **Maksimalni filter**  
  → izberemo največjo vrednost iz okolice.

- **Median filter**  
  → izberemo srednji element v sortiranem seznamu (mediano).

Median filter je namenjen odstranjevanju **impulznega šuma**. Impulzni šum pomeni, da je posamezen, izoliran pixel pokvarjen, pojavi se kot nenadna motnja (impulz), pogosto kot zelo svetla ali zelo temna točka.

- Če je impulznega šuma malo → uporabimo manjši filter (npr. 3×3).
- Če je šuma več → potrebujemo večjo masko.

Problem median filtra je, da lahko izbriše tanke črte in odstrani drobne detajle v sliki.

---

### Detektorji robov

Filtre lahko uporabljamo tudi za **poudarjanje robov**. Cilj predobdelave slik je med drugim:

- popravljanje osvetlitve,
- odstranjevanje šuma,
- poudarjanje pomembnih struktur (npr. robov).

Kaj je rob v sliki?
Rob nastane, ko prehajamo iz enega območja slike v drugo, med dvema različnima regijama.

Primer:
- prehod iz ene barve stene v drugo, kjer je meja med dvema objektoma.

Kako se rob kaže v sliki?
Če gledamo slikovno funkcijo se sprehodimo po vrstici pixel po pixel in opazujemo, kako se vrednost funkcije spreminja. Robovi se pojavijo tam, kjer pride do nenadnega skoka v vrednosti slikovne funkcije. Pravi robovi so torej tam, kjer funkcija skoči oz. močno spremeni vrednost.

Slikovna funkcija je funkcija dveh prostorskih koordinat:

$$
f(x, y)
$$

Za vsak pixel lahko definiramo **lastnost roba**. Rob je opisan z **vektorsko spremenljivko**:

- ena komponenta predstavlja jakost roba,
- druga komponenta predstavlja smer roba.

Da določimo rob, nas zanima, kako hitro se funkcija spreminja. Za dosego tega izračunamo **gradient funkcije**:

$$
\nabla f(x,y) =
\begin{bmatrix}
\frac{\partial f}{\partial x} \\
\frac{\partial f}{\partial y}
\end{bmatrix}
$$

Gradient dobimo iz dveh parcialnih odvodov:

- odvod po $x$ smeri,
- odvod po $y$ smeri.

---

#### Jakost roba

Jakost roba določimo s pomočjo **jakosti (velikosti) gradienta**:

$$
|\nabla f| =
\sqrt{
\left( \frac{\partial f}{\partial x} \right)^2 +
\left( \frac{\partial f}{\partial y} \right)^2
}
$$

Večja kot je vrednost, močnejši je rob.

---

#### Smer roba

Smer roba je določena s smerjo gradienta. Gradiantni vektor kaže smer največjega in najmanjšega vektorja.

**Smer gradienta** lahko določimo z:

$$
\theta = \arctan
\left(
\frac{\partial f / \partial y}
{\partial f / \partial x}
\right)
$$

Za vsak pixel izračunamo:

- **jakost roba**
- **smer roba**

Po izračunu dobimo dve matriki:

1. matriko jakosti robov
2. matriko smeri robov

Prave robove določimo tako, da preverimo ali je jakost roba dovolj velika. Če je jakost premajhna, pixel ne obravnavamo kot rob.

---

#### Gradient za zvezno slikovno funkcijo

Za zvezno funkcijo $I(x,y)$ je gradient definiran kot:

$$
\nabla I =
\begin{bmatrix}
\frac{\partial I}{\partial x} \\
\frac{\partial I}{\partial y}
\end{bmatrix}
$$

Jakost roba:

$$
|\nabla I| =
\sqrt{
\left(\frac{\partial I}{\partial x}\right)^2 +
\left(\frac{\partial I}{\partial y}\right)^2
}
$$

Smer roba:

$$
\theta =
\arctan
\left(
\frac{\frac{\partial I}{\partial y}}
{\frac{\partial I}{\partial x}}
\right)
$$

---

#### Aproksimacija parcialnih odvodov v digitalnih slikah

Ker so digitalne slike diskretne, moramo parcialne odvode **aproksimirati z razlikami**.

##### Aproksimacija odvoda po x

Za diskretno sliko $I(i,j)$:

**Razlika nazaj:**

$$
\frac{\partial I(i,j)}{\partial x}
\approx
\frac{I(i,j) - I(i-\Delta x, j)}{\Delta x}
$$

**Razlika naprej:**

$$
\frac{\partial I(i,j)}{\partial x}
\approx
\frac{I(i+\Delta x, j) - I(i,j)}{\Delta x}
$$

**Simetrična razlika:**

$$
\frac{\partial I(i,j)}{\partial x}
\approx
\frac{I(i+\Delta x, j) - I(i-\Delta x, j)}{2\Delta x}
$$

Običajno vzamemo:

$$
\Delta x = 1
$$

Podobno velja za odvod po $y$ smeri.

---

#### Laplaceov operator

Laplaceov operator uporabimo za oceno **drugega odvoda** slikovne funkcije.

Za zvezno funkcijo $I(x,y)$ je definiran kot:

$$
\nabla^2 I =
\frac{\partial^2 I}{\partial x^2}
+
\frac{\partial^2 I}{\partial y^2}
$$

V digitalni sliki ga aproksimiramo z masko (konvolucijskim filtrom), npr.:

$$
\begin{bmatrix}
0 & -1 & 0 \\
-1 & 4 & -1 \\
0 & -1 & 0
\end{bmatrix}
$$

Rezultat je matrika, v kateri je ocenjen približek za **drugi odvod** slike.

---

#### Sobelov operator

Sobelov operator uporabljamo za oceno **prvih parcialnih odvodov** (gradienta).

Uporabimo dve maski:

**Maska $H_x$ (odvod po x)**

$$
H_x =
\begin{bmatrix}
-1 & 0 & 1 \\
-2 & 0 & 2 \\
-1 & 0 & 1
\end{bmatrix}
$$

Z njo dobimo ocenjen parcialni odvod po $x$:

$$
G_x = I * H_x
$$

**Maska $H_y$ (odvod po y)**

Masko dobimo z rotacijo za 90°:

$$
H_y =
\begin{bmatrix}
-1 & -2 & -1 \\
0 & 0 & 0 \\
1 & 2 & 1
\end{bmatrix}
$$

Z njo dobimo ocenjen parcialni odvod po $y$:

$$
G_y = I * H_y
$$

---

##### Jakost in smer gradienta

Jakost gradienta:

$$
|\nabla I| =
\sqrt{G_x^2 + G_y^2}
$$

Smer gradienta:

$$
\psi =
\arctan\left(\frac{G_y}{G_x}\right)
$$

---

Digitalne slike niso samo črno-bele, ampak imajo **sivinske vrednosti**:

- temnejši del slike → manjša vrednost
- svetlejši del slike → večja vrednost
- črna → vrednost blizu 0
- bela → največja vre

--

## Segmentacija slik

### Pragovna operacija

#### Segmentacija

Pri segmentaciji je cilj, da sliko razdelimo na **regije**:

- regija 1
- regija 2
- regija 3
- ...

Te regije tvorijo piksli, ki so si med seboj podobni glede na nek kriterij, ki ga določimo, na primer:

- sivinska vrednost
- barva
- gradient
- tekstura
- itd.

---

Regija mora biti **sklenjena**. To pomeni, da lahko znotraj regije od enega pixla do drugega pridemo brez "skakanja" izven regije.

Unija vseh regij mora pokriti vse pixle v sliki.

Vedno imamo najmanj **dve regiji**:

1. **Region of Interest (ROI)** – regija, ki nas zanima  
2. **Background** – regija, ki nas ne zanima  

Pri vsakem problemu imamo torej vsaj eno regijo, ki nas zanima, in eno, ki nas ne zanima.  
Koliko dodatnih regij imamo, je odvisno od problema, ki ga rešujemo.

> Primer
> Če bi analizirali študente po obrazu:
>
> - obraz študenta → regija, ki nas zanima  
> - vse ostalo → background  

---

Piksli v regijah imajo **labelo (oznako)**.

- Piksli v isti regiji imajo isto labelo (isto številko).
- Pikslom, ki nas ne zanimajo (background), nastavimo labelo **0**.
- Tisto, kar nas zanima, ima vrednost **večjo od 0**.

> [!WARNING]
> Labele niso nujno zaporedne! Na primer: vsi pixli neke regije imajo lahko vrednost 103.

---

Pri segmentaciji bo naš vhod **sivinska slika**, na izhodu segmentacije pa bomo dobili ven **segmentirano sliko**.

Segmentirana slika je lahko **Binarna slika**. Pri binarni sliki velja:

- vrednost 0 → background (nas ne zanima)
- vrednost ≠ 0 → objekt/regija, ki nas zanima

---

Sivinska slika pa lahko vsebuje več regij, ki nas zanimajo (npr. več objektov z določeno sivinsko vrednostjo). 

> [!IMPORTANT]
> Cilj segmentacije je, da dobimo regijo, ki čim bolje ustreza objektu, ki nas zanima.

Poznamo 2 vrsti segmentacij, **popolno segmentacijo** in **delno segmentacijo**.

> [!IMPORTANT]
> **Popolna segmentacija** pomeni, da natančno dobimo objekt, ki ga iščemo brez dodatnih ali manjkajočih delov.

> [!IMPORTANT]
> V praksi pa so pogostejše **delne segmentacije**. Pri tej vrsti segmentacij dobimo poleg objekta, ki nas zanima, tudi dodatne neželene dele in regije, kjer se pojavijo napake.

> [!WARNING]
> NI UNIVERZALNE SEGMENTACIJSKE METODE ZA REŠEVANJE VSAKEGA PROBLEMA! ENE EDINSTSTVENE METODE NI! METODO PRILAGODIMO GLEDE NA NAŠ PROBLEM, KI GA REŠUJEMO.

---

#### Segmentacijske metode

Segmentacijske metode lahko razdelimo v različne skupine. Metode delimo glede na **informacijo**, ki jo uporabljajo za segmentacijo. Ločimo 3 skupine segmentacijskih metod, in sicer glede na dominantno lastnost, ki jo uporabljajo.

Ločimo sledeče 3 skupine segmentacijskih metod:
- **segmentacija z globalnim znanjem o sliki oz. njenih delih** (npr. pragodvna operacija).
- **segmentacija na osnovi robov**
- **segmentacija na osnovi regij** 

(segmentacija na osnovi robov in osnovi regij delata isto stvar na 2 različna načina. Pomenita dualni problem: vsaka regija je namreč lahko predstavljena s sklenjeno konturo in obratno)

- **učeče metode (sodobni pristopi)**

**Učeči pristopi** postajajo v zadnjih letih popularni. Sem sodijo:

- strojno učenje
- globoko učenje
- nevronske mreže

Model se nauči segmentacije iz podatkov. Pri tem imamo nek model (npr. obliko ali strukturo)  
in se vprašamo:

> Ali ta model obstaja v sliki?

Segmentacija temelji na preverjanju ujemanja med modelom in dejansko sliko.

##### Thresholding (Pragovna operacija)

Thresholding je **najhitrejši način segmentacije**. Zaradi svoje enostavnosti in hitrosti je zelo primeren za real-time aplikacije. Imamo en prag $T$. Vsak piksel slike po vrsticah in stolpcih primerjamo s tem pragom. Za vsak piksel $I(i,j)$:

$$
g(i,j) =
\begin{cases}
1, & \text{če } I(i,j) \geq T \\
0, & \text{sicer}
\end{cases}
$$

Najenostavnejše so operacije z enim pragom in da je ta prag konstanten za celotno sliko.

Algoritem:
- na začetku določimo prag (npr. $T = 87$),
- z dvema for zankama (po vrsticah in stolpcih) pregledamo vse piksle,
- vsak piksel primerjamo s pragom,
- če je vrednost piksla večja ali enaka določenemu pragu (npr. $T = 87$), potem vrnemo vrednost 1, sicer vrnemo vrednost 0

##### Variabilni prag (lokalni thresholding)

Če je prag variabilen se prag prilagaja glede na del slike in metoda postane zahtevnejša. V praksi ne računamo popolnoma neodvisnega praga za vsak pixel, ampak prag določimo na lokalnem območju (npr. v oknu okoli pixla).

Če iščemo svetle objekte na temnem ozadju:

$$
I(i,j) \geq T
$$

Če pa iščemo temne objekte na svetlem ozadju, obrnemo neenačaj:

$$
I(i,j) \leq T
$$

---

Trashholding je danes zelo pogosto uporabljen. Uporablja se skoraj v vseh industrijskih aplikacijah, kjer:

- imamo nadzor nad osvetlitvijo,
- so pogoji zajema slike stabilni,
- je kontrast med objektom in ozadjem dovolj velik.

Če lahko nadzorujemo svetlobo, je thresholding pogosto najboljša izbira.

---

Namesto enega praga pa lahko uporabimo tudi več pragov:

$$
T_1 < T_2 < T_3 < \dots
$$

Pixel razvrstimo glede na interval, v katerega pade njegova vrednost.

Primer:

$$
g(i,j) =
\begin{cases}
0, & I < T_1 \\
1, & T_1 \leq I < T_2 \\
2, & T_2 \leq I < T_3 \\
\dots
\end{cases}
$$

Rezultat:
- več-regijska segmentacija
- ne samo binarna slika

---

##### Kako določiti prag?
Metoda je zelo preprosta. Glavni problem pa je kako pravilno določiti prag. Izbira praga je namreč ključna za uspešno segmentacijo.

Če imamo 8-bitno sivinsko sliko, imajo pixli vrednosti od:

$$
0 \text{ do } 255
$$

To pomeni, da imamo teoretično **256 možnih pragov**.

Vprašanje je:
> Kateri prag je pravi?

Odgovor ni enoznačen.

Ne obstaja univerzalno najboljša segmentacijska metoda, ki bi vedno vrnila pravi prag.  
Izbira praga je vedno odvisna od problema, ki ga rešujemo.

- En prag je lahko za en problem perfekten.
- Za drug problem pa popolnoma neuporaben.

###### 1. Eksperimentalna določitev

Prag določimo ročno. To pomeni, da si prag sami izmislimo. Kontroliramo okolje, mi zajamemo slike, primerjamo in testiramo kateri prag je najboljši in tistega uporabimo. 

---

###### 2. Polovica med minimalno in maksimalno sivino na sliki

Vzememo:
- najmanjšo sivinsko vrednost v sliki: $I_{min}$
- največjo sivinsko vrednost v sliki: $I_{max}$

Prag določimo tako, da vzamemo največjo in najmanjšo vrednost na sliki in vzamemo sredino za prag:

$$
T = \frac{I_{min} + I_{max}}{2}
$$

Metoda je preprosta, vendar pogosto ni optimalna.

---

Za naprednejše metode potrebujemo določiti nekaj pomožnih izrazov iz slike I:

1. histogram sivin
2. dve pomožni polji

Naj ima histogram $L$ elementov (pri 8-bitni sliki je $L = 256$).

Označimo:

- $h_k$ → število pikslov s sivinsko vrednostjo $k$

---

**Pomožno polje**

Polje $A$ ima enako število elementov kot histogram.

V njem hranimo kumulativno vsoto števila pikslov do nivoja $k$:

$$
A_k = \sum_{i=0}^{k} h_i
$$

To pomeni:

- $A_0 = h_0$
- $A_1 = h_0 + h_1$
- $A_2 = h_0 + h_1 + h_2$
- ...
- $A_k = \sum_{i=0}^{k} h_i$

Polje $A_k$ nam pove, koliko pixlov ima sivinsko vrednost manjšo ali enako $k$.

---

**Pomožno polje B**

Polje $B$ ima prav tako enako število elementov kot histogram.

V njem hranimo kumulativno vsoto sivinskih vrednosti:

$$
B_k = \sum_{i=0}^{k} i \cdot h_i
$$

Primeri:

- $B_0 = 0 \cdot h_0$
- $B_1 = 0 \cdot h_0 + 1 \cdot h_1$
- $B_2 = 0 \cdot h_0 + 1 \cdot h_1 + 2 \cdot h_2$

Na splošno:

Vsak element vsebuje vsoto:

> sivina × število pixlov (za vse sivine ≤ k)

- $B_k$ hrani vsoto vseh sivinskih vrednosti, ki so manjše ali enake $k$.
- Zadnji element $B_{L-1}$ predstavlja vsoto vseh sivinskih vrednosti v celotni sliki.

To sta osnovni pomožni polji, ki ju uporabljamo pri naprednejših metodah določanja praga (npr. optimizacijskih metodah).

---

###### 3.Prag kot povprečje slike

Prag postavimo na **povprečno sivinsko vrednost slike**.

Izračun:

$$
T = \frac{\text{vsota vseh sivinskih vrednosti}}{\text{število vseh pixlov}}
$$

Ker že imamo definirani pomožni polji:

- $A_Q$ → skupno število vseh pixlov
- $B_Q$ → vsota vseh sivinskih vrednosti v sliki

Lahko prag izračunamo kot:

$$
T = \frac{B_Q}{A_Q}
$$

Dobimo aritmetično sredino (povprečje) sivinskih vrednosti.

Ta metoda je preprosta, vendar:
- deluje dobro le, če je histogram približno simetričen,
- ni nujno optimalna za slike z več vrhovi v histogramu.

---

###### 4. Prag kot mediana

Prag določimo z **mediano histogramov sivin**.

Prag postavimo tako, da:

- približno polovica pixlov ima vrednost manjšo od praga,
- približno polovica pixlov ima vrednost večjo od praga.

Formalno:

Poiščemo tak $T$, da velja:

$$
A_T \approx \frac{A_Q}{2}
$$

kjer je:
- $A_T$ → kumulativno število pixlov do sivine $T$
- $A_Q$ → skupno število vseh pixlov

---

1. Izračunamo histogram.
2. Izračunamo kumulativno polje $A_k$.
3. S pomočjo zanke (npr. `for`) pregledujemo vse možne pragove.
4. Ustavimo se pri prvem $T$, kjer:

$$
A_T \geq \frac{A_Q}{2}
$$

Ta $T$ je mediana sivinskih vrednosti.

---

###### 5. Optimalni prag (iterativna metoda)

> [!WARNING]
> Kljub imenu ta metoda **ni matematično optimalna** v splošnem smislu! Deluje dobro le, če so izpolnjene določene predpostavke o porazdelitvi sivinskih vrednosti.

Pri globalnem pragu običajno predpostavimo:

- en del slike predstavlja **ozadje**,
- drugi del slike predstavlja **objekt (kar nas zanima)**.

V histogramu sivinskih vrednosti imamo torej dve porazdelitvi:

- ena pripada ozadju (npr. zelena krivulja),
- druga pripada objektu (npr. rdeča krivulja).

V praksi poznamo samo skupni histogram, ki je vsota obeh porazdelitev.

**Cilj metode je najti prag, ki najbolje loči ti dve porazdelitvi.**

---

Metoda je **iterativna**.

Potrebujemo:
- začetni približek praga $T_0$ (**Začetni prag določimo sami!**)

---

Pri pragu $T_0$:

- vse sivine manjše od $T_0$ obravnavamo kot ozadje,
- vse sivine večje ali enake $T_0$ obravnavamo kot objekt.

Izračunamo:

- povprečno vrednost ozadja → $\mu_0(T_0)$
- povprečno vrednost objekta → $\mu_1(T_0)$

---

Nov prag določimo kot sredino med obema povprečjema:

$$
T_{1} = \frac{\mu_0(T_0) + \mu_1(T_0)}{2}
$$

---

Postopek ponavljamo:

1. Razdelimo histogram glede na trenutni prag $T_k$.
2. Izračunamo:
   - $\mu_0(T_k)$
   - $\mu_1(T_k)$
3. Posodobimo prag:

$$
T_{k+1} = \frac{\mu_0(T_k) + \mu_1(T_k)}{2}
$$

---

Iteracije izvajamo, dokler se prag bistveno spreminja.

Razliko merimo z majhno konstanto $\varepsilon$:

$$
|T_{k+1} - T_k| < \varepsilon
$$

Ker delamo z realnimi števili, se prag običajno vedno nekoliko spremeni, zato potrebujemo toleranco $\varepsilon$.

---

###### 6. Globalni prag določen z entropijo (Kapurjev prag)

Ta metoda določi prag na podlagi **entropije**. Entropija je mera za količino informacije v sistemu.

Slika vsebuje malo informacij, če imajo vsi pixli enako ali zelo podobno sivinsko vrednost in je histogram močno skoncentriran okoli ene vrednosti.

Primer:
- vsi pixli imajo isto sivino → entropija je minimalna.

---

Slika vsebuje veliko informacij, če so zastopane vse sivinske vrednosti in so vrednosti približno naključno porazdeljene. Takrat je entropija visoka.

---

**Ideja Kapurjeve metode**

Imamo izbran prag $T$, ki sliko razdeli na:

- **ozadje** (sivine ≤ T)
- **ospredje** (sivine > T)

Cilj:

> Po segmentaciji želimo ohraniti čim več informacij v obeh delih slike.

Postopek:

- izračunamo entropijo ozadja,
- izračunamo entropijo ospredja,
- seštejemo obe entropiji.

Naj bo:

- $p_i$ → normaliziran histogram (verjetnost sivine $i$)

**Za izbran prag $T$**:

**Entropija ozadja**:
$$
H_0(T)
$$

**Entropija ospredja**:
$$
H_1(T)
$$

**Skupna entropija**:
$$
H(T) = H_0(T) + H_1(T)
$$

---

**Postopek**:

1. Izračunamo histogram.
2. Histogram normaliziramo (da dobimo verjetnosti).
3. Z zanko (`for`) pregledamo vse možne prage:
   - od 0 do 255 (pri 8-bitni sliki).
4. Za vsak prag izračunamo:
   - entropijo ozadja,
   - entropijo ospredja,
   - njuno vsoto.
5. Poiščemo prag, kjer je vrednost:$H(T) \text{ maksimalna}$

Naš prag je tam, kjer dobimo naksimalne vrednosti.

---

### Pragovna operacija na sliki robov

Najenostavnejši pristop:

1. Na sivinski sliki uporabimo **detektor robov**.
2. Dobimo sliko jakosti robov.
3. Na tej sliki izvedemo **thresholding (pragovanje)**.

Rezultat:

- piksli, ki predstavljajo rob → vrednost 1
- ostali piksli → vrednost 0

---

Po thresholdingu dobimo robove objekta. Te robove pa moramo med seboj povezati v smiselne konture. Samo binarna slika robov še ne pomeni, da imamo zaključene meje regij.

Algoritem sledenja meji:

- poveže robne piksle v zaprto konturo,
- ali pa iz že znane regije poišče njen rob.

Uporabimo ga lahko:
- ko še nimamo definirane regije (povezujemo robove),
- ali ko regijo že imamo (iščemo njen obris).

---

#### Notranja in zunanja meja regije

##### Notranja meja

Notranjo mejo tvorijo:

- pixli, ki še pripadajo regiji,
- in se nahajajo na njenem robu.

Ko govorimo o **obrisu regije**, mislimo na notranjo mejo.

---

##### Zunanja meja

Zunanjo mejo tvorijo:

- pixli, ki so sosedi notranje meje,
- vendar ne pripadajo regiji,
- ampak ozadju ali drugi regiji.

> [!WARNING]
> Regija ne sme biti velika samo 1 pixel. Če dobimo regijo velikosti 1 pixel, smo najverjetneje naredili napako v segmentaciji.

---

##### Kako deluje algoritem sledenja meji?

Ključno vprašanje:

> Kakšno sosedstvo uporabimo?

###### 4-sosedstvo

Pixel ima 4 sosede:
- gor
- dol
- levo
- desno

###### 8-sosedstvo

Pixel ima 8 možnih smeri gibanja:

- gor
- dol
- levo
- desno
- štiri diagonalne smeri

Pri 8-sosedstvu se lahko iz posameznega pixla premaknemo v 8 različnih smeri. To omogoča bolj naravno in neprekinjeno sledenje robov.

### Ujemanje šablon

## Zaporedje slik in sledenje gibanja

Velikokrat je koristno znanje o obdelavi zaporedij slik. Na primer: videoposnetek predstavlja zaporedje več slik iste scene, ki so urejene v časovnem zaporedju. Zaporedje slik lahko obdelujemo na preprost način – tako, da obdelujemo vsako sliko posebej.

Postopek je naslednji:
- vzamemo prvo sliko iz zaporedja,
- jo obdelamo,
- nato vzamemo naslednjo sliko,
- jo prav tako obdelamo,
- in tako nadaljujemo skozi celotno zaporedje.

### Osnovni pojmi

#### Zaporedje slik

**Zvezno zaporedje slik**-poemni, da se slika spreminja v zveznem času. Takšno sliko lahko opišemo s tremi časovnimi spremenljivkami:
- x-os (prostorska dimenzija),
- y-os (prostorska dimenzija),
- čas (t), skozi katerega se slika spreminja.

Torej gre za funkcijo treh spremenljivk:

$$
I(x, y, t)
$$

Mi bomo delali z diskretnimi slikami in zaporedjem diskretnih slik (npr. video).

> **Kaj pridobimo z zaporedjem slik?**
>
> Če vsako sliko obdelujemo posebej, ignoriramo časovno povezanost med njimi.
>
> Zaporedje slik pa nam omogoča dodatne analize.
>
> **Primer: medicinske slike**
>
> Pri medicinskih slikah lahko:
>
> - rekonstruiramo strukture v telesu,
> - izvedemo 3D rekonstrukcijo objekta.
>
> **Primer: videoposnetek**
>
> Pri videoposnetkih lahko izvajamo:
>
> - zaznavanje gibanja
> - razpoznavanje kje v sceni se izvaja neko gibanje
> - analizo parametrov gibanja teh objektov
>
> Analizo lahko izvajamo neposredno v slikovni matriki (2D), ali v rekonstruirani 3D sceni.

### Slike razlik

Najenostavnejši pristop pri obdelavi zaporedij slik so **slike razlik**. Gre za približek **odvoda po času**.

Vzamemo dve sliki in odštejemo istoležne pixle:

$$
D(x,y) = I_t(x,y) - I_{t-1}(x,y)
$$

kjer:
- $I_t$ predstavlja trenutno sliko,
- $I_{t-1}$ predstavlja prejšnjo sliko,
- $D(x,y)$ je slika razlik.

---

Če je scena statična (nič se ne premika) bodo razlike med zaporednima slikama enake 0, oziroma zelo blizu 0 (zaradi šuma).

Torej:

$$
D(x,y) \approx 0
$$

---

Če se v sceni pojavi gibanje pa bodo na mestih, kjer se objekt premika, vrednosti različne od 0. Tam zaznamo spremembo. Pri tem pa ni nujno, da odštevamo samo dve zaporedni sliki. Lahko odštejemo dve zaporedni sliki, lahko pa odštejemo sliko, ki je npr. 10 framov nazaj. Ključno je samo, da odštejemo dve sliki in na tak način dobimo sliko razlik.

Primer:

$$
D(x,y) = I_t(x,y) - I_{t-k}(x,y)
$$

kjer je $k$ poljubno število framov.

Ključno je:

> Vedno odštevamo dve sliki in dobimo sliko razlik.

FPS določa kako pogosto zajemamo slike, koliko slik na sekundo dobimo. Večji FPS pomeni manjšo časovno razliko med slikami.

---

Sliko razlik lahko obdelamo enako kot navadne slike z uporabo segmentacije. Najenostavnejši pristop je:

**Thresholding (pragovanje)**

1. Izberemo poljuben prag $T$.
2. Na podlagi izbranega praga analiziramo sliko.

Ker lahko pri odštevanju dobimo tudi negativne vrednosti, uporabimo absolutno vrednost:

$$
D'(x,y) = |I_t(x,y) - I_{t-k}(x,y)|
$$

Nato izvedemo pragovanje:

$$
g(x,y) =
\begin{cases}
gibajoči se, & \text{če } D'(x,y) \geq T \\
0, & \text{sicer}
\end{cases}
$$

### Statično ozadje

Pri uporabi slike razlik je problem, da ni nujno, da bomo uspešno izsegmentirali gibajoči se objekt.

Uspešnost metode je močno odvisna od:

- hitrosti objekta v slikovni ravnini,
- frekvence zajema slik (FPS),
- količine šuma v sliki.

Če je objekt zelo počasen ali se premika zelo malo, so razlike med slikami lahko zelo majhne. Ravno za te primere, ki so bolj enostavni, da so scene z majhnimi spremembami, pa je metoda slike razlik ravno najbolj primerna. Gre za preprost postopek, kjer aproksimiramo **odvod po času**.

---

Metodo lahko posplošimo. Namesto da odštevamo dve zaporedni sliki, lahko:

- prvo zajamemo sceno (ozadje)
- vzamemo trenutno sliko,
- od nje odštejemo sliko statičnega ozadja.

$$
D(x,y) = |I_t(x,y) - B(x,y)|
$$

kjer je:
- $I_t(x,y)$ trenutna slika,
- $B(x,y)$ slika ozadja.

Na mestih, kjer dobimo vrednosti precej različne od 0:

- je prišlo do spremembe,
- tam se je verjetno pojavil ali premaknil objekt.

Na mestih, kjer je rezultat blizu 0:

- se scena ni spremenila,
- tam imamo ozadje.

---

**Kako pa dobimo sliko ozadja?**

Če imamo nadzor nad okoljem (npr. nadzorovan prostor) zajamemo sceno brez gibanja,
- zajamemo sceno brez gibanja,
- nekaj minut opazujemo prostor,
- sistem si zapomni statično ozadje.

Na primer:
- 2–3 minute snemamo prazen prostor,
- sistem iz teh slik izračuna model ozadja,
- kasneje vsako novo sliko primerjamo s tem ozadjem.

Tak pristop je zelo pogost pri nadzornih sistemih.

---

#### Postopki tvorjenja statičnega ozadja

Obstajajo postopki, kjer iz zaporedja slik poskušamo rekonstruirati **sliko ozadja**, tudi kadar je scena dinamična in vsebuje gibanje. Iz več zaporednih slik poskušamo oceniti, kaj predstavlja statično ozadje.

##### 1. Metoda - Povprečenje celotnega zaporedja slik

**Postopek**
Za vsak pixel $(i,j)$ spremljamo njegovo vrednost skozi vse slike v zaporedju in izračunamo zanj povprečno vrednost. Ta postopek naredimo za vse pixle slike.

Matematično:

$$
B(i,j) = \frac{1}{N} \sum_{t=1}^{N} I_t(i,j)
$$

kjer je:
- $N$ število slik,
- $I_t(i,j)$ vrednost pixla v času $t$.

Gre za enostaven postopek. Deluje dobro, če se objekti **relativno hitro premikajo**. Če je gibanje zelo počasno, pa se lahko objekt “skrije” v ozadje (postane del povprečja).

---

##### 2. Metoda - Iskanje skokov (robov) v časovni funkciji pixla

**Postopek**

Izberemo en pixel $(i,j)$ na prvi sliki. Nato spremljamo njegovo vrednost skozi celotno zaporedje slik in opazujemo, kako se njegova vrednost spreminja skozi čas. Iščemo **skoke (robove)** v časovni funkciji.

Primer:
Če se objekt premakne čez pixel, pride do nenadne spremembe vrednosti (skoka).

Pri slikah, kjer zaznamo pri izbranem pikslu skok, sklepamo, da gre za gibajoči se objekt. Te dele izločimo in ne upoštevamo. Seštejemo del pred skokom in po skoku in izračunamo povprečje. Povprečje izračunamo samo iz stabilnih delov (brez skokov). Na ta način poskušamo dobiti boljšo oceno statičnega ozadja.

---

##### 3. Metoda - Z drsečim oknom skozi čas

Pri tej metodi ne opazujemo pixla skozi celotno zaporedje, ampak samo skozi **omejeno določeno število zaporednih slik**.

**Drseče okno**
Za drseče okno lahko vzamemo npr. okno vleikosti 5. To pomeni, da bomo piksel opazovali na petih zaporednih slikah. V tem oknu bomo opazovali kako bo vrednost funkcije nihala.

**Postopek**

V izbranem oknu opazujemo nihanje vrednosti pixla. Preverimo, če ta vrednost niha v nekem dovoljenem območju. Npr. da med maksimumom in minimumom ni razlika večja od 10 nivojev.

Če velja:

$$
\max - \min \leq \text{dovoljena meja} \quad (\text{npr. 10 nivojev})
$$

Potem izračunamo povprečje v tem oknu in to povprečje prištejemo k skupnemu povprečju. Nato povečamo števec veljavnih oken za 1. Nato okno premaknemo za eno sliko naprej in opazujemo naslednjih 5 slik. Tak postopek nato ponavljamo. Če vrednosti v oknu preveč nihajo od dovoljenega območja npr. da min in max vrednost je večja od 10 nivojev, tega okna ne upoštevamo. Na koncu povprečje vseh oken delimo z vsemi okni in dobimo rezultat.

$$
B(i,j) = \frac{\text{vsota povprečij veljavnih oken}}{\text{število veljavnih oken}}
$$

Dobimo oceno ozadja, ki je bolj robustna na gibanje.

---

Sliko razlik pogosto uporabljamo kot preprost alarmni sistem. Če zaznamo dovolj veliko spremembo (veliko gibajočih se pixlov) sprožimo alarm in aktiviramo zahtevnejše algoritme. To je smiselno, ker ni učinkovito, da bi kompleksne algoritme izvajali ves čas, ampak jih uporabimo le takrat, ko so res potrebne (npr. ko zaznamo gibanje).

> [!WARNING]
> Pomembno je omenit, da je model ozadja potrebno tudi posodabljati, ker se svetloba in vremenski pogoji skozi dan spreminjajo. Zato mora biti model ozadja prilagodljiv (adaptiven).

Za samo segmentacijo te zgoraj opisane 3 metode ne najboljše. Za take primere imamo boljše metode.

### Optični pretok

Gre za metodo, ki ocenjuje **polje gibanja** med dvema zaporednima slikama.

Vzememo $ij$-ti piksel na sliki. Predpostavimo, da zajemamo premikanje objekta (npr. pilota). Med premikanjem se piksel premakne za vektor $\mathbf{u}$:

- premik v smeri $x$: $u_x$
- premik v smeri $y$: $u_y$

Temu pravimo **vektor gibanja** iz slike 1 v sliko 2.

**Matrika gibanja** $\mathbf{U}$ pa hrani vektorje gibanja za vse piksle slike. Če ima slika dimenzijo $M \times N$, ima tudi matrika $\mathbf{U}$ dimenzijo $M \times N$, saj vsebuje toliko elelmentov kot je pikslov na sliki.

**Postopek implementacije:**
- ena matrika vsebuje vrednosti premikov po $x$
- druga matrika vsebuje vrednosti premikov po $y$
- matrika U pa je sestavljena iz dveh matrik, matrike po $x$ in matrike po $y$

Torej:

$$
\mathbf{U} = (U_x, U_y)
$$

kjer:
- $U_x$ vsebuje vse vrednosti $u_x$
- $U_y$ vsebuje vse vrednosti $u_y$

Tam kjer ni gibanja bo vektor 0:

$$
\mathbf{u} = (0,0)
$$

Med:
- sliko 0 in 1 dobimo matriko gibanja $\mathbf{U}_1$
- sliko 1 in 2 dobimo novo matriko gibanja $\mathbf{U}_2$
- itd.

---

V praksi pa mi nimamo matrike gibanja — imamo le zaporedje slik. Matriko gibanja ocenimo s pomočjo **optičnega toka**, na podlagi zaporedja slik. Optični tok je tehnika, ki temelji na predpostavki, da svetlost gibajočega se objekta ostane konstantna skozi čas. 

Svetlost gibajočega se objekta ostane konstantna skozi čas:

$$
I(x,y,t) = I(x + u_x, y + u_y, t+1)
$$

Iz tega sledi, da je popolni odvod po času enak 0:

$$
\frac{dI}{dt} = 0
$$

Imamo tri parcialne odvode:

- po $x$
- po $y$
- po času $t$

---

Končna enačba optičnega toka je:

$$
I_x u_x + I_y u_y + I_t = 0
$$

kjer:

- $I_x = \frac{\partial I}{\partial x}$
- $I_y = \frac{\partial I}{\partial y}$
- $I_t = \frac{\partial I}{\partial t}$

Parcialna odvoda $I_x$ in $I_y$ predstavljata robove slike.

---

Imamo skupaj:

- 1 enačbo
- 2 neznanki ($u_x$, $u_y$)

Problem tega je, da rešitve ne moremo določiti enolično. Dobimo premico rešitev, zato moramo dodati dodatno predpostavko za enolično rešitev. Za namene tega uporabimo metodo Lucas–Kanade.

---

Metoda **Lucas–Kanade** temelji na predpostavki optičnega toka, da se svetlost piksla skozi čas ne spreminja. Doda pa še eno pomembno predpostavko:

> Piksel in njegova majhna okolica se gibajo z enako hitrostjo (imajo enak vektor gibanja).

To pomeni, da imajo vsi piksli v izbrani okolici enak vektor gibanja:
$$
\mathbf{u} = (u_x, u_y)
$$

Zaradi tega dobimo več enačb za isti dve neznanki.

---

#### Oblikovanje sistema enačb

##### Korak 1: Izberemo okolico

Določimo okolico okoli opazovanega piksla (npr. 3×3 ali 5×5). Če imamo okolico 3×3, imamo 9 pikslov → dobimo 9 enačb.

---

##### Korak 2: Izračun parcialnih odvodov

Za vsak piksel v okolici izračunamo:

- parcialni odvod po $x$
- parcialni odvod po $y$
- parcialni odvod po času $t$

---

##### Korak 3: Matrika A

Parcialne odvode nato zložimo v matriko:

$$
A =
\begin{bmatrix}
I_{x1} & I_{y1} \\
I_{x2} & I_{y2} \\
\vdots & \vdots \\
I_{xq} & I_{yq}
\end{bmatrix}
$$

Če imamo okolico 3×3:

- $q = 9$
- dimenzija matrike je $9 \times 2$

Prvi stolpec vsebuje odvode po $x$, drugi po $y$.

---

##### Korak 4: Stolpec b

Nato pa formiramo stolpec b. Za vsak piksel iz okolice določimo parcialni odvod po času:

$$
b =
\begin{bmatrix}
I_{t1} \\
I_{t2} \\
\vdots \\
I_{tq}
\end{bmatrix}
$$

Od trenutnega piksla odštejemo istoležni piksel na prejšnji sliki — to je ocena parcialnega odvoda za naš piksel.

---

##### Korak 5: Reševanje sistema

Dobimo sistem:

$$
A \mathbf{u} + b = 0
$$

kjer je:

$$
\mathbf{u} =
\begin{bmatrix}
u_x \\
u_y
\end{bmatrix}
$$

Tu imamo problem da imamo inverz matrike, ki obstaja samo za kvadratne matrike. Matrika $A$ ni kvadratna (npr. 9×2), zato ne moremo izračunati klasičnega inverza. Zato uporabimo **psevdoinverz**:

$$
\mathbf{u} = (A^T A)^{-1} A^T (-b)
$$

To je rešitev v smislu najmanjših kvadratov.

Za vsak piksel posebej moramo:

- določiti matriko $A$
- določiti stolpec $b$
- izračunati $\mathbf{u}$

Računsko je ta metoda precej zahtevna.

---

#### Psevdokod algoritma

##### Izbira okolice

Okolico določimo sami (npr. 5×5).

---

##### Opcijska koraka (predobdelava)

1. Filtriranje slike z Gaussovim filtrom → odstranimo bel šum

2. Časovno glajenje z enodimenzionalnim Gaussovim filtrom → stabilizacija skozi čas

Ta dva koraka nista nujna, povečata pa stabilnost.

---

##### Ključni koraki

###### Ocenitev optičnega toka

Gremo skozi zaporedje slik:
- od druge do zadnje slike
ali  
- od prve do predzadnje

Ključno je, da vedno imamo eno sliko manj kot je vseh slik.

Za vsak piksel izračunamo:

1. Izračunamo parcialne odvode
2. Sestavimo matriko $A$
3. Sestavimo stolpec $b$
4. Izračunamo psevdoinverz
5. Shranimo rezultat v matriko gibanja

Računsko je to kar pasje.

---

##### Kaj dobimo z optičnim tokom?

Med vsako zaporedno sliko dobimo ocenjeno matriko gibanja.

Opazujemo lahko:

$$
|\mathbf{u}| = \sqrt{u_x^2 + u_y^2}
$$

- če je dolžina majhna → ni gibanja (ali je pod pragom)
- če je dolžina velika → zaznamo gibanje

Vektor gibanja pove:

- smer gibanja iz slike v sliko
- hitrost gibanja v slikovni ravnini

---

##### Primer – Optični pretok

Imamo pravokotnik, ki se premika.

Med vsako sliko se premakne:

- 3 vrstice navzdol
- 4 stolpce desno

To informacijo poznamo mi, algoritem pa je ne.

Po prvem koraku (Gauss filtriranje) dobimo zglajeno sliko.

Nadaljnji izračun temelji na:

- seštevanju
- odštevanju
- računanju parcialnih odvodov
- reševanju sistema najmanjših kvadratov

### Sledenje objektom

Ta pristop je zelo naraven. Pri sledenju objektov **ne obdelujemo vsake slike posebej**, temveč si pomagamo z zgodovino:

- Kje je bil objekt na prejšnji sliki?
- Kako se je gibal?

Na podlagi zgodovine **predvidimo nov položaj objekta**.

---

Postopek poteka v dveh fazah:

1. **Predikcija** – ocenimo, kje naj bi bil objekt na novi sliki.
2. **Korekcija** – preverimo in popravimo napako predikcije.

Predikcija je lahko:

- pravilna  
- napačna  

V obeh primerih moramo rezultat preveriti in po potrebi popraviti.

---

> **Primer**
>
> - Nogometaš teče naprej → predikcija, da bo nadaljeval naprej, je lahko pravilna.
> - Nogometaš naredi finto in se obrne → predikcija je napačna.
>
> V obeh primerih moramo predvideni položaj **korigirati**.

---

Na začetni sliki moramo:

1. Z nekim algoritmom določiti začetno pozicijo (npr. težišče objekta).
2. Objekt moramo najprej **segmentirati** (z enim izmed segmentacijskih postopkov).

Če želimo slediti nogometašu, ga moramo najprej izločiti iz ozadja (s enim od postopkov segmentacije).

---

Nato gremo skozi zaporedje slik:

1. Na podlagi zgodovine predvidimo položaj.
2. Na novi sliki poiščemo objekt v okolici predvidenega položaja.

Primer:

- Na pretekli sliki je bil nogometaš na določeni poziciji.
- Predvidevamo, da bo na naslednji sliki nekoliko naprej.

---

V oknu okoli predvidene lokacije:

- preverimo dejanski položaj objekta
- popravimo napako predikcije

Če:

- je objekt blizu predvidenega mesta → popravimo položaj
- objekt ni tam (npr. zaradi nenadne spremembe gibanja) → moramo ponovno pregledati širše območje ali celo celotno sliko

---

> **Primer**
>
> Če nogometaš naredi finto in ostane na istem mestu ali spremeni smer:
>
> - predikcijsko okno je lahko prazno
> - potrebno je ponovno iskanje objekta po sliki
> - nato nadaljujemo s ciklom:
>  
>  **predikcija → korekcija → predikcija → korekcija**

## Geometrija več pogledov

### Dva pogleda (splošno)

Do zdaj smo obravnavali eno sliko ali zaporedje slik skozi čas (premikanje kamere ali objektov)

Sedaj imamo drugačen primer:

> Dve kameri gledata isto sceno oziroma objekt iz različnih položajev.

Do zdaj smo matematično modelirali projekcijo:

Točka v prostoru $P = (X,Y,Z)$ se preslika v piksel $(x,y)$ na sliki.

To je bila **projekcija iz 3D v 2D**.

Sedaj želimo obratni postopek:

> Imamo piksel na sliki.  
> Zanima pa nas iz katere točke v prostoru je prišel?

---

Problem pri tem je, da iz ene slike ne moremo enolično rekonstruirati piksle v 3D točke.

Razlog:

- Vsaka točka na projekcijskem žarku se preslika v isti piksel.
- Imamo neskončno mnogo možnih 3D točk na istem žarku.

Zato:

> Potrebujemo več pogledov (minimalno 2 pogleda).

---

#### Geometrija dveh kamer

Imamo:

- točko v prostoru $P$
- dve kameri
- projekciji točke na obeh slikah: $p$ in $p'$

---

**Osnovnica** je daljica med optičnima centroma obeh kamer. Tam, kjer osnovnica prebije slikovni ravnini, dobimo:

- epipol $e$ (na levi sliki)
- epipol $e'$ (na desni sliki)

- **Epipol $e$**: projekcija optičnega centra desne kamere na levo sliko.
- **Epipol $e'$**: projekcija optičnega centra leve kamere na desno sliko.

---

**Epipolarna ravnina** je ravnina, ki jo določajo:

- optični center prve kamere
- optični center druge kamere
- točka $P$ v prostoru

To ravnino imenujemo **epipolarna ravnina**.

Na tej ravnini ležijo:

- osnovnica
- točka $P$
- oba projekcijska žarka

---

Presek epipolarne ravnine s slikovno ravnino da:

- **epipolarno premico $l$** na levi sliki
- **epipolarno premico $l'$** na desni sliki

Velja:

- $l$ je daljica od $e$ do $p$
- $l'$ je daljica od $e'$ do $p'$

---

Za rekonstrukcijo 3D točke moramo vedeti:

> Katera točka $p'$ na drugi sliki ustreza točki $p$ na prvi sliki?

Če imamo piksel $p$ na sliki leve kamere, potrebujemo pripadajoči piksel $p'$ na sliki desne kamere. Preden lahko rekonstruiramo 3D točko $P$, moramo torej najti ustrezno točko $p'$.

Če bi iskali pripadajoči piksel po celotni sliki bi morali pregledati vse piksle in časovna zahtevnost bi bila približno $O(n^2)$, kar bi pomenilo, da bi postopek bil zelo počasen. To je brute force pristop.

---

Namesto pregledovanja celotne slike uporabimo **epipolarno premico**. Točka $p'$ mora ležati na epipolarni premici $l'$. Zato ne iščemo in pregledujemo celotne slike, ampak se sprehajamo samo po epipolarni premici in pregledujemo točke samo tam. S tem močno pohitrimo iskanje korespondenc in zmanjšamo časovno zahtevnost:

$$
O(n^2) \rightarrow O(n)
$$

Iz točke $p$ na levi sliki lahko izračunamo epipolarno premico $l'$ na desni sliki. Vedno računamo epipolarno premico za drugo sliko.
Ko najdemo ustrezno točko $p'$, lahko rekonstruiramo 3D točko $P$.

---

**Kako pa določimo epipolarno premico $l'$?**

Da lahko izračunamo **epipolarno premico $l'$**, moramo poznati transformacijo med obema pogledoma. Če poznamo transformacijo med kamerama znamo izračunati epipolarno premico, na njej pa lahko poiščemp ustrezno točko in nato izvedemo 3D rekonstrukcijo.

##### PRVA VARIANTA – Kalibrirane razmere

Če imamo **kalibrirane razmere**, pomeni, da poznamo kalibracijski matriki obeh kamer in notranji parametri kamer so znani. V tem primeru je transformacija med obema pogledoma podana z **osnovno (esencialno) matriko** $E$.

Povezava med pogledoma (točkama na obeh slikah) je podana z enačbo:

$$
p^T E p' = 0
$$

kjer:

- $p$ – piksel na levi sliki (v homogenih koordinatah)
- $p'$ – piksel na desni sliki (v homogenih koordinatah)

---

Matrika $E$ je osnovna matrika v kalibriranih enotah.

Sestavljena je iz:

- rotacije $R$
- translacije $t$

Velja:

$$
E = [t]_\times R
$$

kjer je:

- $R$ – rotacijska matrika
- $[t]_\times$ – matrika, ki predstavlja translacijo v obliki navzkrižnega produkta

---

Če je:

$$
t = 
\begin{bmatrix}
t_x \\
t_y \\
t_z
\end{bmatrix}
$$

potem je pripadajoča matrika:

$$
[t]_\times =
\begin{bmatrix}
0 & -t_z & t_y \\
t_z & 0 & -t_x \\
-t_y & t_x & 0
\end{bmatrix}
$$

Translacijski vektor je torej zapisan v matrični obliki.

---

Če imamo točko $p'$ na desni sliki (v homogenih koordinatah), dobimo epipolarno premico na levi sliki z:

$$
l = E p'
$$

Rezultat je stolpec treh vrednosti:

$$
l =
\begin{bmatrix}
a \\
b \\
c
\end{bmatrix}
$$

Te tri vrednosti predstavljajo parametre premice.

---

Če ima piksel na sliki koordinate vektorjev $(u, v)$, potem je epipolarna premica podana z:

$$
a u + b v + c = 0
$$

---

V praksi je pogostejši primer, ko nimamo kalibriranih razmer. Takrat uporabljamo **fundamentalno matriko** namesto esencialne matrike.

##### DRUGA VARIANTA – Neurejene oz. nekalibrirane razmere

V tem primeru transformacijo med obema pogledoma podaja **temeljna matrika** $F$.

---

Povezava med pripadajočima piksloma $p$ in $p'$ je podana z enačbo:

$$
p^T F p' = 0
$$

Enačba je po obliki zelo podobna tisti pri esencialni matriki. Če poznamo temeljno matriko $F$, lahko delamo po isti relaciji kot prej.

---

**Kako pridemo do temeljne matrike $F$?**

Ne poznamo kalibracijskih matrik $K$. Teoretična povezava med kalibracijska in temeljno matriko je:

$$
F = K^{-T} E K^{-1}
$$

Vendar v praksi te enačbe ne moremo uporabiti, ker matrik $K$ ne poznamo. Zato do temeljne matrike pridemo preko **kalibracije sistema kamer**. Uporabimo kalibracijo in računamo kalibracijsko matriko!

---

###### Kalibracija sistema kamer

**Korespondenčni pari**

Potrebujemo pare pripadajočih točk:

- piksel na sliki leve kamere
- pripadajoči piksel na sliki desne kamere

> [!WARNING]
> Korespondenčne točke morajo biti čim bolj natančno določene in čim bolj razpršene po celotni sliki (da ne ležijo preveč skupaj!), sicer postane usmerjanje nestabilno!

Lahko jih določimo:

1. ročno (ročno določimo položaje točk na slikah),
2. avtomatsko (iskanje značilnic in karakteristik v sliki npr. ogljišča objektov).

---

###### Algoritem osmih točk

Matrika $F$ je velikosti $3 \times 3$:

$$
F =
\begin{bmatrix}
F_{11} & F_{12} & F_{13} \\
F_{21} & F_{22} & F_{23} \\
F_{31} & F_{32} & F_{33}
\end{bmatrix}
$$

To pomeni, da ima 9 neznank. Kako jih določimo potem z 8 pari točk?
Uporabimo trik.

Postavimo:

$$
F_{33} = 1
$$

S tem zmanjšamo število neznank na 8. Naredimo stolpec 8 neznank. Imamo našo matriko, ki ima 8 stolpcev in toliko vrstic, kolikor je korespondenčnih parov. Prva vrstica za prvi korespondenčni par, druga vrstica za drug korespondenčni par itd.

Oblikujemo sistem linearnih enačb:

- vsaka korespondenčna točka da eno enačbo
- dobimo sistem z 8 neznankami

Rešimo ga z uporabo **psevdoinverza** (metoda najmanjših kvadratov).

---

Algoritem osmih točk ima problem, da je občutljiv na napake. Raziskave kažejo, da je možno dobiti boljše rezultate, če uporabimo **normalizacijo točk**.

---

**1. Centriranje podatkov (točk)**

Pomeni, da izračunamo povprečni piksel (povprečje) in ga odštejemo od vsake točke-potem bo povprečje v točki 0,0 oz. koordinatnem izhodišču:

$$
(0,0)
$$

To naredimo za piksle leve in desne kamere.

---

**2. Skaliranje**

Po centriranju:

- izračunamo povprečno razdaljo točk od izhodišča
- skaliramo točke tako, da je ta razdalja enaka:

$$
\sqrt{2}
$$

To naredimo za vsako točko.

---

> [!WARNING]
> Dobimo temeljno matriko $F$ za normalizirane (skalirane) točke. V praksi je algoritem osmih točk občutljiv na napake, zato se pogosto uporabljajo robustnejše metode.

---

### Trije pogledi

Če imamo **3 poglede**, obstajajo postopki, ki lahko problem napadejo direktno.

V praksi pa raje rešujemo problem **3× za 2 kameri**:

- (1. in 2. kamera)
- (1. in 3. kamera)
- (2. in 3. kamera)

---

Pojavi se vprašanje:

> Ali je bolje imeti 2 kameri, 3 kamere, 5 kamer …?

Ne obstaja enostavna enačba, ki bi točno povedala optimalno število kamer. Raziskave pa kažejo, da če imamo manjši prostor (npr. učilnico), prehod iz **2 na 3 kamere** opazno izboljša natančnost. Prehod iz **3 na 4 ali več kamer** pa prinese zelo majhno izboljšanje (npr. le nekaj odstotkov). Glede na čas in kompleksnost sistema je za omejeno območje **sistem treh kamer običajno povsem dovolj.**

---

Ko govorimo o pogledih to pomeni, da kamere morajo gledati **isti del prostora** in zaznavati **iste prostorske točke**.

---

### Določanje položaja točk v 3D

Imamo:

- pripadajoča piksla na levi kameri
- pripadajoča piksla na desni kameri

Iz pikslov na levi in desni kameri bi želeli priti nazaj do točke v prostoru:

$$
\text{prostorsko točko } P
$$

Poznamo torej projekciji točke na slikah (piksla na sliki).

---

> Teoretični primer – 2 pogleda
>
> Imamo:
>
> - optični center leve kamere $O$
> - optični center desne kamere $O'$
>
> Pošljemo:
>
> - žarek skozi $O$
> - žarek skozi $O'$
>
> Teoretično velja:
>
> **Kjer se žarka sekata, tam leži rekonstruirana točka $P$.** Problem je, da v praksi temu dosti krat ni tako.

V realnosti se žarka skoraj nikoli ne sekata natančno in zaradi šuma in napak sta **mimobežna**. V primeru treh pogledov imamo v prostoru 3 žarke. V splošnem se ti trije žarki ne sekajo v eni točki. Nimajo skupnega presečišča. 

Kaj naredimo?
Poiščemo točko, ki je:

$$
\text{najbližja vsem trem premicam}
$$

Torej iščemo točko, ki minimizira razdaljo do vseh treh žarkov.

---

#### Postopek za 2 pogleda?

Imamo dve mimobežni premici.

Postopek:

1. Poiščemo daljico, ki je pravokotna na obe premici.
2. Ta daljica predstavlja najkrajšo razdaljo med premicama.
3. Točko postavimo na sredino te daljice.

Geometrijsko:

$$
P = \text{središče najkrajše povezovalne daljice}
$$

Ali je to dobro ali slabo?

Težko podamo absolutno oceno. Lahko pa rešitev dobro interpretiramo geometrijsko:
- minimiziramo napako med žarkoma.

---

#### Postopek za 3 poglede

Problem rešimo **3× po 2 kameri**:

1. Rekonstrukcija iz (1, 2) → dobimo točko $P_{12}$
2. Rekonstrukcija iz (1, 3) → dobimo točko $P_{13}$
3. Rekonstrukcija iz (2, 3) → dobimo točko $P_{23}$

Dobimo tri približne točke v prostoru.

Vzamemo povprečje:

$$
P = \frac{P_{12} + P_{13} + P_{23}}{3}
$$

To je končna ocena prostorske točke.

---

### Stereo vid

#### Rekonstrukcija

Matematični pristop nima neposredne geometrijske razlage. Točke, ki jo dobimo, geometrijsko ne znamo enostavno interpretirati in ne znamo povedati, zakaj je točno tam v prostoru.

Izhaja iz osnovne projekcijske enačbe:

$$
p = \frac{1}{z} M P
$$

kjer je:

- $P$ — prostorska točka,
- $M$ — projekcijska matrika kamere,
- $p$ — projekcija na sliki,
- $z$ — globinska komponenta.

Imamo dve kameri:

- leva kamera: $M$
- desna kamera: $M'$

Poznamo:

- $p$ (leva slika),
- $p'$ (desna slika).

---

Enačbo preuredimo:

$$
p \times (M P) = 0
$$

Dobimo:

- eno enačbo za levo kamero,
- eno enačbo za desno kamero.

S tem dobimo sistem linearnih enačb za neznano točko $P$.

---

Če je prava točka:

$$
P = [100, 200, 300]^T
$$

bi pričakovali, da bo rekonstrukcija enaka. Te vrednosti bodo pa v praksi žal drugačne.

V praksi:

- dobimo drugačne vrednosti,
- oblika prostora je lahko deformirana,
- namesto kvadrov dobimo rombe,
- pojavljajo se rotacije in translacije.

To pomeni, da je rekonstrukcija določena le do projektivne (ali afine) transformacije.

---

#### Primer paralelnih kamer

Imamo poseben primer dveh pogledov, kjer ima konfiguracija 2 poljubni kameri. **Stereo vid s paralelnimi kamerami** pomeni, da predpostavljamo da imamo dve enaki kameri z enakim goriščem. Stereo pomeni **2 kameri**.

Predpostavke:

- dve enaki kameri,
- enako gorišče,
- razdalja med kamerama $b$ (baseline),
- optični osi sta vzporedni,
- slikovni ravnini sta poravnani.

Običajno:

$$
b \in [8 \text{ cm}, 16 \text{ cm}]
$$

(razmik med očmi).

---

Epipolarne premice so:

> kar vrstice slike.

Če se točka $P$ preslika v piksel na levi sliki, potem:

- pripadajoči piksel na desni sliki leži v isti vrstici,
- razlikuje se mogoče samo stolpec.

To pomeni:

> iščemo samo po eni vrstici.

To je prednost stereo vida s paralelnima paroma. Sprehodimo se po isti vrstici, pa najdemo v enem stolpcu iskan piksel!

---

**Globina točke** določa kako je točka oddaljena od osi. Odvisna je od razlike položajev na levi in desni sliki.

Naj bo:

- $f$ — gorišče,
- $b$ — razdalja med kamerama,
- $d$ — disparity (v merskih enotah).

Potem:

$$
Z = \frac{f b}{d}
$$

> [!WARNING]
> $d$ mora biti v merskih enotah (ne v piklih), zato potrebujemo velikost pixla.

---

Ampak ta stvar ni v realnosti tako lepa! Popolnoma paralelnih kamer praktično ne moremo izdelati.

Razlogi:

- kameri nista identični,
- rahlo različni goriščni razdalji,
- mehanske napake,
- optični osi nista popolnoma vzporedni.

Tak sistem je nemogoče popolnoma realizirati, lahko se mu samo približamo. Če bi kupili 2 identični kameri bo zagotovo vsaka imela malo drugačno goriščno razdaljo. Ne mogoče je stvari tako pritrditi, da bomo imeli vzporedne optične osi.

---

#### Rektifikacija oz. izravnavanje slik

Ta problem pa se na srečo da rešiti matematično s postopkom **izravnavanja slik**. To pomeni, da slike, ki jih zajamemo (naredimo stereo sistem) transformiramo, jih zravnamo, kot da bi bile zajete s sistemom stereo vida. Na teh popravljenih slikah pa se lahko uporabi zgoraj opisano teorijo. Temu postopku rečemo **rektifikacija**

> [!IMPORTANT]
> **Rektifikacija** je postopek s katerim sliko leve in desne kamere transformiramo v novo slikovno ravnino, tako da epipolarne premice postanejo vodoravne.

Rektifikacija ima 2 prosta parametra:

1. Razdalja nove ravnine od osnovnice.
2. Normala ravnine (vektor pravokoten na ravnino).

S tema parametroma določimo geometrijsko transformacijo.

---

#### Ujemanje stereo slik (paralelne kamere)

Imamo pa še problem **ujemanja stereo slik**. Če želimo globino in imamo piksel na levi sliki, moramo najti pripadajoči piksel na desni sliki. Temu pravimo stereo matching (ujemanje stereo slik). Za dosego tega imamo 2 skupini metod:

- ena skupina je na nivoju sivin
- druga skupina je na osnovi značilnic

---

##### 1. Metode na osnovi sivin

Postopek:

- opazujemo vrednost slikovne funkcije v obravnavani vrstici leve in desne slike
- izberemo okno v levi sliki in ga ne premikamo,
- v desni sliki pa imamo isto okno, ki ga pa premikamo (po izbrani vrstici),
- izračunamo podobnost med obema oknoma,
- poiščemo okno, kjer je bila razlika najmanjša
- izračunamo koliko premikov je bilo potrebnih, da smo našli pripadajoč piksel
- na koncu dobimo disparity value

Število premikov = disparity.

To so prva skupina metod, kjer opazujemo okno oz. profil v vrstici leve in desne kamere in kateri se najbolj ujema. To je t. i. **block matching metode**.

---

##### 2. Metode na osnovi značilnic

Postopek:

1. Poiščemo značilne točke (oglišče, markerji, robovi).
2. Poiščemo ujemanje med značilnicami leve in desne slike.

Ta postopek pa ne delamo za vse piksle, ampak samo za ključne točke.

Problem je težaven in daleč od trivialnega.

---

##### Omejitve pri ujemanju

Pri iskanju ujemanja upoštevamo razne omejitve:

###### 1. Podobnost

Značilnici morata imeti podobne lastnosti:

- gradient,
- sivino,
- lokalna struktura

Težava:
- npr. gladka stena → vse točke na zidu so si podobne, skoraj da enake.

---

###### 2. Enoličnost

Vsaka značilnica na eni sliki se mora ujemati natanko z eno značilnico na drugi sliki.

Težava:
- ponavljajoči se vzorci (ograja, znaki).

---

###### 3. Zveznost (Smoothness)

Predpostavimo, da se disparity med sosednjimi piksli malo spreminja.

---

###### 4. Urejanje (Ordering constraint)

Relativni vrstni red točk se med slikama ohranja. Če sta ujemajoča se para (m, m') in (n,n') potem, če je m levo od n, potem bo tudi m' levo od n' (in obratno).

---

##### 5. Epipolarna omejitev

Ujemajoča se točka lahko leži le na pripadajoči epipolarni premici. **Ta omejitev je najbolj zanesljiva!**

---

## Uvod v razpoznavanje vzorcev

naši vzorci so iz dveh značilnic. Imamo množico m-tih takih vzorcev in zdaj probamo vzorce grupirat v roje na osnovi merjenja razdalje.

### Definicije in osnovni pojmi

V roje (skupine) združimo vzorce, ki so si po razdalji med seboj blizu. Ko dobimo roje jih pregleda ekspert in vsakemu roju dodeli oznako (labelo).

> Primer
> - razred 1 → jabolka  
> - razred 2 → hruške  
> - itd.

Na koncu dobimo **Učno množico**. To je množica parov:

$$
(\text{vzorec}, \text{labela})
$$

To je izhod faze **spoznavanja področja uporabe**.

Rojanje temelji na:

- merjenju razdalje med vzorci,
- nivoju podobnosti med vzorci.

Podobnost definiramo kot:

$$
\text{podobnost} = \frac{1}{\text{razdalja}}
$$

Manjša razdalja → večja podobnost.

Med vzorci lahko definiramo neskončno mnogo razdalj.

Potrebujemo **mero razdalje**, ki je smiselna za naš problem. Pred rojenjem je priporočljivo tudi izvesti **preobdelavo podatkov** in da preverimo kakovost množice vzorcev.

---

#### Koraki preobdelave

##### 1. Manjkajoče vrednosti

Ali kateri značilnosti manjka vrednost?

> **Primer**
> Senzor na neki točki pride v nasičenje in nimamo izmerjene neke meritve

Možni rešitvi:

1. Vzorec odstranimo (če si to lahko privoščimo).
2. Nadomestimo manjkajočo vrednost s povprečjem:

$$
x_i = \bar{x}
$$

S tem minimiziramo napako.

---

##### 2. Odstopanja (outlierji)

Preverimo, ali katera značilnost močno odstopa od povprečja.

Če si lahko privoščimo → vzorec odstranimo.  
Če ne → ga moramo ustrezno obravnavati.

Kako preverimo odstopanje?
Za vsako značilnost izračunamo:

**Povprečje:**

$$
\bar{x} = \frac{1}{N} \sum_{i=1}^{N} x_i
$$

**Standardni odklon:**

$$
\sigma = \sqrt{\frac{1}{N} \sum_{i=1}^{N} (x_i - \bar{x})^2}
$$

**Koeficient poševnosti (skewness):**

Merimo asimetričnost porazdelitve.

Interpretacija:

- če je koeficient poševnosti < 0.5 → približno simetrična porazdelitev,
- če je ≥ 3 → močno asimetrična (možna problematična značilnost).

Te tri statistike izračunamo za **vsako značilnost**.

---

Po rojenju preverimo:

> Kako se vzorci porazdeljujejo v prostoru značilnic?

Možni primeri:

- Naključna porazdelitev → ni dobra
- Močna zakonitost (linearni trend) → prav tako ni zaželena
- Jasno ločeni roji (npr. dva roja) → to je zaželjeno

---

Če rezultat ni ustrezen se vrnemo nazaj:

- v blok določanja značilnic
- ali v sistem meritev

in izboljšamo:

- izbor značilnic
- merilni postopek
- kvaliteto podatkov

---

### Model razvrščevalnika vzorcev

### Zapisi vzorcev

### Spoznavanje področja uporabe

### Razvrščanje vzorcev

### Preizkušanje razvrščevalnika vzorcev