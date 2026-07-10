+++
title = "Sistemska administracija"
date = 2026-02-03T07:07:07+01:00
draft = false
math = true

summary = "Zapiski za predmet Sistemska administracija za poletni semester drugega letnika FERI RIT UNI."
summary_enable = true
summary_style = "subtitle"
+++

## Uvod

### Kaj je sistemska administracija

**Sistem** - skupina interaktivnih, povezanih in med seboj odvisnih elementov, ki sestavljajo celoto. Sistemi, kot so človek-računalnik sestojijo iz sledečih elementov: računalniki, omrežja, uporabniki ter organizacijski cilji in politike.

**Administracija** - proces postavljanja, konfiguriranja, izboljševanja in vzdrževanja celotne informacijske tehnologije (IT) v podjetju ali organizaciji. To vključuje sistemsko načrtovanje, upravljanje z viri, diagnosticiranje sistemskih napak in vse, kar je povezano z razvojem programske opreme, programiranjem, pisanjem skriptnih programov in drugo.

**Sistemski administrator** (poznan tudi pod imeni, kot so sistemski skrbnik, operater, omrežni administrator, sistemski programer, sistemski upravljalec, tehnična podpora in drugo) je oseba, ki administrira nad nekimi sistemi, običajno odznotraj neke organizacije/institucije. Sistemski skrbnik je odgovoren za upravljanje, nadzor in vzdrževanje računalniškega okolja za več uporabnikov (npr. v lokalnem omrežju - LAN). Njegove odgovornosti in opravila so različne in običajno niso natančno definirane, odvisno od zahtev organizacije. Sistemski administratorji morajo imeti močno tehnično znanje in spretnosti ter strokovno znanje na področju upravljanja osebja. Majhna organizacija ima lahko samo eno osebo na delovnem mestu, medtem ko ima podjetje ponavadi celotno skupino sistemskih administratorjev. 

To so lahko:
- administratorji za podatkovne baze
- administratorji za omrežja
- administratorji za splet
- administratorji za pošto
- administratorji za hrambo podatkov
- operater računalniških sistemov

Ideja administratorja je, da poskuša pomagat oz. servirat potrebne zadeve. Je nekdo, ki je pogosto priučen iz izkušenj in skrbi za opremo, da je delujoča. Npr. da se oprema pregreje in odpove, je naloga administratorja, da jo ponovno usposobi oz. najde neko rešitev, da do tega ne bo več prišlo.

Običajna opravila sistemskega administratorja v vsakdanjem življenju:
1. Opazuje/spremlja rezervne kopije,
2. Upošteva dejstva, ki vplivajo na rezervne kopije, kot so:
    - velikost datotečnega sistema,
    - ostale aktivnosti med izdelavo rezervne kopije,
    - hitrost omrežja,
    - hitrost diskov in njihove velikosti;
3. Določa faktorje, s katerimi lahko povečamo učinkovitost,
4. Zadevo preizkusi — jo požene,
5. Postopek ponovi (če je to potrebno)

Preberi več:
https://en.wikipedia.org/wiki/System_administrator

**Računalništvu v oblaku** - pomeni, da dostopamo do nekega oddaljenega računalnika oz. naprave, od katere lahko potem izkoriščamo vire (programska in strojna oprema, ter storitve). 
 
**Spam** - vsaka nezaželena in nenaročena digitalna vsebina, ki je množično poslana z namenom vsiljevanja oglasov, prevar ali škodljivih povezav.

Pri delu z računalniškimi sistemi je poleg kibernetske varnosti eden izmed ključnih vidikov tudi nadzor in način kako sisteme zavarovati pred zunanjimi vplivi. Problem so lahko vremenske razmere, kot so nevihte, požari, poplave in višje temperature. Problem so lahko tudi olitični razlogi kot so vojne. Vsi ti dejavniki namreč lahko računalniško opremo poškodujejo ali celo uničijo, zaradi česar je pomembno znati sistem nadzorovati ter najti tudi načine kako ga zaščititi.

---

### Operacijski sistemi

Poznamo vrsto različnih operacijskih sistemov in njihovih distribucij:
- HP-UX
- FreeBSD
- Windows OS
- Linux
- Temple OS
- ...

Kateri operacijski sistem pa je sedaj njaboljši? Katerega je najbolj priporočljivo uporabljati v podjetju?
Ni univerzalno najboljšega operacijskega sistema. Najprimernejši OS je odvisen od namena uporabe.

#### Osnove sistema UNIX (tudi Linux)

Operacijski sistem delimo na:
- jedro
- ukazno lupino
- orodja in aplikacije

UNIX sistemi imajo sledeče lastnosti:
- večplastnost
- večuporabniški sistem
- prenosljivost
- omrežje

>
> **Za razmislek...**
>
> Kdaj je nastal posamezni operacijski sistem?
>
> - **Microsoft Windows** – prva različica (**Windows 1.0**) je izšla leta **1985**.
> - **UNIX** – razvit je bil leta **1969** v podjetju Bell Labs.
> - **GNU/Linux** – jedro Linux je ustvaril Linus Torvalds leta **1991**, skupaj s projektom GNU pa predstavlja operacijski sistem GNU/Linux.
>
> Kakšni so trendi pri operacijskih sistemih?
>
> Med pomembnejše trende sodijo:
> 
> - večja osredotočenost na **varnost**,
> - redne in avtomatske **posodobitve**,
> - podpora za **virtualizacijo** in **kontejnerje** (Docker, Kubernetes),
> - razvoj **oblačnih (cloud) storitev**,
> - boljša podpora večjedrnim procesorjem,
> - večja energetska učinkovitost,
> - večja avtomatizacija administracije,
> - poudarek na odprtokodnih rešitvah (predvsem Linux v strežniških okoljih).
> 

#### Osnovne lastnosti sistema UNIX (in večine sodobnih operacijskih sistemov)

Temeljne lastnosti sistema UNIX se odražajo v naslednjih konceptih:

- **Večuporabniški sistem** – omogoča hkratno delo več uporabnikov.
- **Uporabniške pravice (privilegiji)** – vsak uporabnik ima določene pravice dostopa do sistema in virov.
- **Zaščita datotek** – datoteke imajo nastavljene pravice za branje, pisanje in izvajanje.
- **Lastništvo procesov in prioritete** – vsak proces ima lastnika in določeno prioriteto izvajanja.
- **Komunikacija z uporabniki** – sistem omogoča komunikacijo med uporabniki in procesi.
- **Razdelitev diskovnega prostora** – podatki so organizirani v datotečnem sistemu z imeniki (direktoriji) in datotekami.

Poleg že omenjenih lastnosti so pomembni tudi naslednji koncepti:

- Račun superuporabnika (root)
    - Superuporabnik (**root**) ima popoln oziroma neomejen dostop do sistema.
    - Lahko spreminja vse sistemske nastavitve, upravlja uporabnike in dostopa do vseh datotek.
    - V sodobnih operacijskih sistemih je uporaba računa **root** oziroma administratorskih pravic dodatno zaščitena (npr. z avtentikacijo ali uporabo ukaza `sudo`).

- Varnostne zahteve
    Pomembni vidiki varnosti vključujejo:
    - **Varovanje uporabniških podatkov** – zaščita osebnih in poslovnih podatkov pred nepooblaščenim dostopom.
    - **Varovanje komunikacij** – uporaba šifriranih povezav (npr. SSH, HTTPS, VPN).
    - **Varovanje računa superuporabnika** – uporaba močnih gesel, večfaktorske avtentikacije in omejevanje dostopa le pooblaščenim uporabnikom.

>
> **Za razmislek...**
>
> Katere operacijske sisteme uporabljamo na mobilnih napravah?
>
> Najpogosteje uporabljeni mobilni operacijski sistemi so:
>
> - **Android** (Google)
> - **iOS** (Apple)
>
> Njune glavne lastnosti
>
> **Android**
> - odprtokoden (AOSP), proizvajalci ga lahko prilagajajo,
> - deluje na širokem naboru naprav,
> - omogoča veliko prilagodljivost uporabniškega vmesnika,
> - podpira veliko število aplikacij.
>
> **iOS**
> - zaprt operacijski sistem podjetja Apple,
> - optimiziran za Applove naprave,
> - poudarek na varnosti in zasebnosti,
> - redne posodobitve za vse podprte naprave,
> - dobro povezan z Applovim ekosistemom.
>

>
> **Dodatno branje**
>
> - Wikipedia – *History of Unix*  
>  https://en.wikipedia.org/wiki/History_of_Unix
>
> - UNIX History Diagram  
>  http://www.levenez.com/unix/
>
> - Wikipedia – *Operating System*  
>  https://en.wikipedia.org/wiki/Operating_system
>

## Disk, datotečni sistem

### Osnovni ukazi

Ko imamo v podjetju **300, 500 ali več računalnikov**, se administracije ne lotevamo ročno na vsakem računalniku posebej. Običajno uporabljamo:

- skripte (Shell, Bash, PowerShell),
- avtomatizacijo,
- orodja za centralno upravljanje.

Na ta način lahko hkrati upravljamo in vzdržujemo večje število računalnikov.

> [!INFO]
> **Opomba:** Skoraj vsi UNIX/Linux ukazi podpirajo različne **zastavice (flags oziroma options)**, ki razširijo njihovo funkcionalnost. Zastavice niso obvezne, vendar omogočajo dodatne možnosti izvajanja ukaza.

---

#### Delo z datotekami

Ukazi:

```
ls, cp, mv, rm, find, more, tail, wc, grep
```

##### `ls` (list)

Izpiše seznam datotek in map v trenutnem direktoriju.

```bash
ls
ls -l
ls -a
```

---

##### `cp` (copy)

Kopira datoteko ali direktorij.

```bash
cp datoteka.txt kopija.txt
cp -r mapa nova_mapa
```

---

##### `mv` (move)

Premakne ali preimenuje datoteko oziroma direktorij.

```bash
mv datoteka.txt Dokumenti/
mv staro.txt novo.txt
```

---

##### `rm` (remove)

Izbriše datoteko ali direktorij.

```bash
rm datoteka.txt
rm -r mapa
```

---

##### `find`

Išče datoteke v direktorijski hierarhiji.

```bash
find . -name "*.txt"
```

---

##### `more`

Omogoča pregledovanje besedilnih datotek stran po stran.

```bash
more datoteka.txt
```

---

##### `tail`

Izpiše zadnji del datoteke.

Privzeto prikaže zadnjih **10 vrstic**.

```bash
tail dnevnik.log
tail -f dnevnik.log
```

---

##### `wc` (word count)

Izpiše:

- število vrstic,
- število besed,
- število bajtov.

```bash
wc datoteka.txt
```

---

##### `grep`

Poišče vrstice, ki ustrezajo podanemu vzorcu (pattern).

```bash
grep "napaka" dnevnik.log
```

Obstajata tudi različici:

- `egrep`
- `fgrep`

---

#### Dovoljenja in lastništvo

Ukazi:

```
chmod, chown, sudo
```

##### `chmod` (change mode)

Spreminjanje dovoljenj datotek in map.

Dovoljenja:

- `r` – read
- `w` – write
- `x` – execute

```bash
chmod 755 skripta.sh
chmod +x skripta.sh
```

---

##### `chown` (change owner)

Spremeni lastnika oziroma skupino datoteke.

```bash
chown marko datoteka.txt
chown marko:studenti datoteka.txt
```

---

##### `sudo`

Omogoča izvajanje ukazov z administratorskimi (root) pravicami.

```bash
sudo apt update
```

---

#### Delo z uporabniki

Ukazi:

```
useradd, usermod, userdel, passwd
```

##### `useradd`

Ustvari novega uporabnika.

```bash
useradd janez
```

---

##### `usermod`

Spremeni nastavitve obstoječega uporabnika.

```bash
usermod -aG sudo janez
```

---

##### `userdel`

Izbriše uporabniški račun.

```bash
userdel janez
```

---

##### `passwd`

Spremeni uporabniško geslo.

```bash
passwd janez
```

---

#### Delo s procesi

Ukazi:

```
ps, top, kill, nice
```

> **Proces** je program, ki se trenutno izvaja.

##### `ps`

Prikaže procese, ki so bili aktivni v trenutku izvajanja ukaza.

```bash
ps
ps aux
```

---

##### `top`

Prikazuje aktivne procese v realnem času.

- osvežuje prikaz,
- prikazuje porabo procesorja,
- prikazuje porabo pomnilnika.

Program deluje, dokler ga sami ne ustavimo (`q` ali `Ctrl+C`).

---

##### `kill`

Konča (prekine) izvajanje procesa.

```bash
kill PID
```

---

##### `nice`

Zažene program z drugačno prioriteto.

Prioritete:

- **-20** → najvišja prioriteta
- **19** → najnižja prioriteta

Negativne vrednosti lahko nastavlja le administrator (`sudo`).

```bash
nice -n 10 program
```

---

#### Delo z diski

Ukazi:

```
df, fdisk, du, mount, umount
```

##### `df`

Prikaže zasedenost diskov in particij.

```bash
df -h
```

---

##### `fdisk`

Orodje za ustvarjanje in upravljanje particij.

---

##### `du`

Prikaže porabo prostora posameznih map ali datotek.

```bash
du -sh Dokumenti
```

---

##### `mount`

Priklop datotečnega sistema ali naprave.

```bash
mount /dev/sdb1 /mnt
```

---

##### `umount`

Odklopi datotečni sistem.

```bash
umount /mnt
```

---

#### Tiskanje

Ukazi:

```
lpr, lpq, lprm
```

##### `lpr`

Pošlje datoteko v tiskanje.

---

##### `lpq`

Prikaže stanje čakalne vrste tiskalnika.

---

##### `lprm`

Prekliče opravila tiskanja (print jobs).

---

#### Ostali pomembni ukazi

Ukazi:

```
man, date, who, telnet, rlogin, ssh, gedit, nano, gvim, ...
```

##### `man`

Prikaže priročnik (manual) za izbran ukaz.

```bash
man ls
```

---

##### `date`

Prikaže ali nastavi sistemski datum in čas.

```bash
date
```

---

##### `who`

Prikaže trenutno prijavljene uporabnike.

```bash
who
```

---

##### `telnet`

Omogoča oddaljeno prijavo preko protokola **TELNET**.

Danes se uporablja redko, saj komunikacija ni šifrirana.

---

##### `rlogin`

Starejši program za oddaljeno prijavo na drug računalnik.

Danes ga skoraj povsem nadomešča SSH.

---

##### `ssh` (Secure Shell)

Najpogosteje uporabljen program za oddaljeno prijavo.

Omogoča:

- varno (šifrirano) komunikacijo,
- izvajanje ukazov na oddaljenem računalniku,
- varen prenos podatkov,
- posredovanje TCP vrat,
- posredovanje X11 povezav.

SSH predstavlja varno zamenjavo za:

- `telnet`
- `rlogin`
- `rsh`

Primer:

```bash
ssh uporabnik@192.168.1.10
```

---

#### Urejevalniki besedilnih datotek

Najpogosteje uporabljeni:

- `nano`
- `gedit`
- `vi`
- `vim`
- `gvim`

Uporabljajo se za urejanje konfiguracijskih in drugih tekstovnih datotek.

---

### Superuporabnik (Superuser)

V operacijskih sistemih **UNIX/Linux** obstaja poseben uporabniški račun z najvišjimi privilegiji, imenovan **superuporabnik** oziroma **root**.

Sinonimi:

- **root**
- **superuporabnik**
- **superuser**
- **administrator**

Superuporabnik ima popoln dostop do sistema in lahko:

- ustvarja in briše uporabnike,
- spreminja sistemske nastavitve,
- namešča in odstranjuje programsko opremo,
- dostopa do vseh datotek in direktorijev,
- spreminja dovoljenja in lastništvo datotek.

> [!INFO]
> **Opomba:** Tudi operacijski sistem Windows pozna administratorski račun. Filozofija je podobna kot pri Linuxu – administrator ima najvišje pravice nad sistemom.

#### Root

V preteklosti se je administrator običajno prijavil neposredno kot uporabnik **root**.

Ker je neposredna prijava v račun root predstavljala varnostno tveganje, se danes priporoča uporaba ukaza **sudo**, ki navadnemu uporabniku začasno omogoči izvajanje ukazov z administratorskimi pravicami.

#### `sudo`

Ukaz `sudo` (*SuperUser DO*) omogoča izvajanje posameznega ukaza z administratorskimi privilegiji.

Primer:

```bash
sudo apt update
sudo apt upgrade
```

Najpogosteje se uporablja za:

- posodobitev sistema,
- nameščanje programov,
- spreminjanje sistemskih nastavitev,
- izvajanje administrativnih opravil.

Če želimo odpreti terminal kot superuporabnik, uporabimo:

```bash
sudo -i
```

ali

```bash
sudo su
```

#### `su` (Switch User)

Ukaz `su` omogoča preklop na drugega uporabnika.

Primer:

```bash
su peter
```

S tem postanemo uporabnik **peter**, vendar obdržimo trenutno uporabniško okolje (environment).

Če želimo prevzeti tudi njegovo okolje (domači direktorij, spremenljivke okolja itd.), uporabimo:

```bash
su - peter
```

Minus (`-`) pomeni, da se naloži celotno prijavno okolje izbranega uporabnika.

Če želimo preiti na račun **root**, uporabimo:

```bash
su -
```

#### Poziv ukazne vrstice

Po pozivu terminala lahko hitro ugotovimo, pod katerim uporabnikom smo prijavljeni.

Običajno velja:

- navaden uporabnik → `$`
- superuporabnik (root) → `#`

Primer:

```bash
marko@pc:~$
```

```bash
root@pc:~#
```

#### Varnost superuporabniškega računa

Superuporabniški račun je najpogostejša tarča napadalcev, saj omogoča popoln nadzor nad sistemom.

Zato se priporoča:

- ne prijavljati se neposredno kot **root**,
- uporabljati ukaz `sudo`,
- uporabljati močna gesla,
- dovoliti administratorske pravice le zaupanja vrednim uporabnikom.

---

#### Identifikacija uporabnikov (UID)

Operacijski sistem uporabnikov ne razlikuje po imenu, ampak po **identifikacijski številki**.

Ta številka se imenuje:

- **UID (User ID)** – identifikacijska številka uporabnika.

Sistem tako dejansko prepozna uporabnika po njegovi številki UID.

Primer:

- **UID 0** - uporabnik **root**
- ostali uporabniki imajo praviloma UID **1000** ali več (odvisno od distribucije Linuxa).

Primer preverjanja UID:

```bash
id
```

Primer izpisa:

```text
uid=1000(marko) gid=1000(marko) groups=1000(marko)
```

#### Povzetek

| Ukaz | Namen |
|------|-------|
| `sudo` | Izvede posamezen ukaz z administratorskimi pravicami. |
| `sudo -i` | Odpre terminal kot superuporabnik (root). |
| `su` | Preklopi na drugega uporabnika. |
| `su -` | Preklopi na drugega uporabnika in naloži njegovo prijavno okolje. |
| `su - peter` | Preklopi na uporabnika **peter** in uporabi njegovo okolje. |
| `id` | Prikaže UID, GID in skupine trenutnega uporabnika. |

---

#### O sistemu — nekaj uporabnih ukazov

##### Preklop uporabnika (`su`)

Primer preklopa uporabnika:

```bash
janez@marko:/work/pd$ su - labraj
```

Po preklopu se prijavimo kot uporabnik `labraj`:

```bash
labraj@marko:~$
```

---

##### Ukaz `id`

Ukaz `id` prikaže informacije o trenutnem uporabniku:

- uporabniški ID (`uid`)
- ID skupine (`gid`)
- skupine, v katere je uporabnik vključen

Primer:

```bash
labraj@marko$ id
```

Rezultat:

```text
uid=1002(labraj) gid=1002(labraj)
```

---

##### Ukaz `uname`

Ukaz `uname` izpiše informacije o operacijskem sistemu.

Osnovni ukaz:

```bash
labraj@marko$ uname
```

Primer rezultata:

```text
Linux
```

Ukaz:

```bash
labraj@marko$ uname -a
```

izpiše celotne informacije o sistemu:

- ime operacijskega sistema,
- različico jedra,
- ime računalnika,
- različico sistema,
- arhitekturo sistema.

Primer:

```text
Linux marko SMP Wed Jan 16 ...
```

##### Razlika med `uname` in `uname -a`

- `uname` vrne samo osnovno ime sistema (npr. `Linux`).
- `uname -a` vrne celotne informacije o sistemu.

---

##### Ukaz `pwd`

Ukaz `pwd` (*print working directory*) izpiše trenutno lokacijo uporabnika v datotečnem sistemu.

Primer:

```bash
labraj@marko$ pwd
```

Rezultat:

```text
/home/labraj
```

---

#### Osnovni koncepti sistema

Operacijski sistemi omogočajo upravljanje preko **ukazne vrstice (CLI – Command Line Interface)**, kjer lahko uporabnik ali administrator izvaja ukaze za pregled in upravljanje sistema, uporabnikov ter datotek.

Pri administraciji sistema se pogosto uporabljajo osnovni sistemski ukazi, s katerimi lahko:

- pregledujemo informacije o sistemu,
- upravljamo uporabnike,
- pregledujemo datoteke in direktorije,
- dostopamo do dokumentacije posameznih ukazov.

---

##### Datoteke in direktoriji

Podatki so v operacijskih sistemih **Unix/Linux** in **Windows** organizirani v **datoteke** (*files*) in **direktorije** (*directories*).

V sistemu Windows se pogosto uporablja izraz **mapa** (*folder*), medtem ko Unix/Linux uporablja izraz **direktorij**. V praksi oba izraza pomenita isto.

> [!INFO]
> Izraza **mapa** in **direktorij** sta sopomenki. V teh zapiskih se uporablja izraz **direktorij**, saj je pogostejši v Unix/Linux okolju.

---

##### Pregled osnovnih ukazov

V nadaljevanju poglavja bodo predstavljeni najpogosteje uporabljeni sistemski ukazi.

| Ukaz | Namen |
|------|------|
| `su` | Preklop na drugega uporabnika |
| `id` | Prikaže podatke o uporabniku |
| `uname` | Prikaže ime operacijskega sistema |
| `uname -a` | Prikaže podrobne informacije o sistemu |
| `pwd` | Prikaže trenutno lokacijo |
| `who` | Prikaže trenutno prijavljene uporabnike |
| `exit` | Odjava uporabnika oziroma zapiranje terminala |
| `which` | Prikaže lokacijo programa |
| `man` | Prikaže dokumentacijo ukaza |

---

### Ukazi za delo s sistemom

#### Ukaz `who`

Ukaz `who` prikaže uporabnike, ki so trenutno prijavljeni v sistem.

Izpiše:

- uporabniško ime,
- terminal, preko katerega je uporabnik prijavljen,
- čas prijave,
- naslov oddaljenega računalnika (če obstaja).

Primer:

```bash
who
```

Primer rezultata:

```text
janez pts/0  2019-03-10 17:00 (93.103.168.185)
janez tty8   2019-03-11 07:06 (:0)
```

---

#### Odjava uporabnika (`exit`)

Terminal ali trenutno uporabniško sejo zaključimo z ukazom:

```bash
exit
```

Enak učinek dosežemo tudi s kombinacijo tipk:

```text
CTRL + D
```

Kombinacija `CTRL + D` terminalu pošlje znak **EOF (End Of File)**, kar pomeni konec vnosa. Če je ukazna vrstica prazna, se trenutna seja zaključi oziroma se uporabnik odjavi.

---

#### Ukaz `which`

Ukaz `which` prikaže lokacijo izvršljivega programa, ki se izvede ob uporabi določenega ukaza.

Primer:

```bash
which ls
```

Rezultat:

```text
/bin/ls
```

To pomeni, da se program `ls` nahaja v direktoriju:

```text
/bin/
```

---

#### Ukaz `man`

Ukaz `man` (*manual*) prikaže uporabniško dokumentacijo za izbran ukaz.

Splošna oblika:

```bash
man <ukaz>
```

Primer:

```bash
man ls
```

Odpre priročnik za ukaz `ls`, kjer so opisani njegov namen, sintaksa, možnosti in primeri uporabe.

> [!TIP]
> Za izhod iz priročnika `man` pritisnemo tipko **q**.

---

### Signali v sistemu

Signal v operacijskem sistemu predstavlja način komunikacije med procesi.

Procesi med seboj komunicirajo tako, da si pošiljajo različne signale.

Signali omogočajo:

- prekinitev procesa,
- obveščanje procesa o dogodkih,
- nadzor izvajanja programov.

---

#### Ukaz `ls`

Ukaz `ls` izpiše vsebino trenutnega direktorija.

Primer:

```bash
ls
```

---

##### Možnosti ukaza `ls`

###### Dolg izpis (`ls -l`)

Parameter `-l` omogoča podrobnejši izpis datotek.

Primer:

```bash
ls -l
```

Izpis vsebuje:

- pravice dostopa,
- lastnika datoteke,
- velikost,
- datum spremembe,
- ime datoteke.

---

###### Izpis po času spremembe (`ls -lt`)

Ukaz:

```bash
ls -lt
```

izpiše datoteke razvrščene po času spremembe.

Datoteke, ki so bile nazadnje spremenjene, se prikažejo na vrhu.

---

###### Rekurzivni izpis (`ls -r`)

Ukaz:

```bash
ls -r
```

izpiše tudi poddirektorije direktorijev, ki se nahajajo v trenutnem direktoriju.

---

#### Ukaz `which`

Ukaz `which` pokaže lokacijo programa, ki se uporablja ob izvajanju določenega ukaza.

Primer:

```bash
which ls
```

Rezultat:

```text
/bin/ls
```

To pomeni, da se program `ls` nahaja v direktoriju:

```text
/bin/
```

---

#### Ukaz `man`

Ukaz `man` (*manual*) prikaže navodila in uporabo določenega ukaza.

Primer:

```bash
man ls
```

Odpre priročnik za uporabo ukaza `ls`.

Splošna uporaba:

```bash
man <ukaz>
```

---

### Datoteke uporabnikov in gesel

#### Datoteka `/etc/passwd`

V Unix/Linux sistemih se informacije o uporabnikih nahajajo v datoteki:

```text
/etc/passwd
```

Primer vsebine:

```text
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
janez:x:1009:1000:Janez,,,:/home/janez:/bin/bash
```

Datoteka vsebuje:

- uporabniško ime,
- identifikacijo uporabnika (`UID`),
- identifikacijo skupine (`GID`),
- domači direktorij,
- privzeto ukazno lupino.

---

#### Datotečna struktura sistema Linux

Linux uporablja drevesno strukturo direktorijev.

Primer:

```text
/
├── etc
│   ├── passwd
│   └── shadow
```

Do datotek pridemo preko korenskega direktorija:

```text
/
```

nato sledimo poti:

```text
/etc/
```

---

### Ukazni interpreter in ukazne lupine

Naloga ukaznega interpreterja je:

- sprejemanje ukazov, ki jih vnese uporabnik,
- izvajanje ukazov,
- omogočanje interaktivnega dela z uporabnikom.

Ukazna lupina (*shell*) predstavlja povezavo med uporabnikom in operacijskim sistemom.

---

#### C Shell (`csh`)

`C Shell` je bila ukazna lupina, namenjena predvsem uporabnikom programskega jezika C.

---

#### Shell v sistemu Windows

Windows ima tudi svoje ukazne lupine.

Primer:

```text
cmd
```

Windows je večino funkcionalnosti prenesel v grafični uporabniški vmesnik.

---

### Datoteke za shranjevanje gesel

#### Datoteka `/etc/passwd`

Datoteko `/etc/passwd` si lahko uporabniki ogledajo:

```bash
cat /etc/passwd
```

Gesla v tej datoteki niso več shranjena neposredno.

Zaradi varnosti so bila gesla odstranjena in nadomeščena z znakom:

```text
x
```

Prava šifrirana gesla se nahajajo v datoteki:

```text
/etc/shadow
```

Do te datoteke ima dostop samo super uporabnik (`root`).

---

#### Datoteka `/etc/shadow`

Datoteka:

```text
/etc/shadow
```

vsebuje šifrirane podatke o geslih uporabnikov.

Za ogled potrebujemo administratorske pravice:

```bash
sudo cat /etc/shadow
```

Primer:

```bash
sudo cat /etc/shadow | grep janez
```

Primer rezultata:

```text
janez:$6$syEDQYOg$790askdjgakquBIAQz6G5xn1Js...
```

Opomba:

- zapis gesla je shranjen v eni vrstici,
- prikazan zapis je samo primer.

---

#### Ukaz `sudo`

Ukaz `sudo` omogoča izvajanje ukazov z administratorskimi pravicami.

Primer:

```bash
sudo cat /etc/shadow
```

---

#### Ukaz `passwd`

Ukaz:

```bash
passwd
```

omogoča spremembo gesla uporabnika.

---

### Identifikacija uporabnikov in skupin

#### UID

`UID` (*User ID*) predstavlja identifikacijo uporabnika.

Primer:

```text
uid=1002(labraj)
```

---

#### GID

`GID` (*Group ID*) predstavlja identifikacijo skupine, kateri uporabnik pripada.

Primer:

```text
gid=1002(labraj)
```

---

#### Kako je kriptirano geslo?

Ob prijavi uporabnik vnese svoje geslo.

Sistem preveri pravilnost tako, da primerja:

1. vneseno geslo,
2. kriptirano vrednost, shranjeno v `/etc/shadow`.

Če se vrednosti ujemata, je uporabnik prijavljen.

---

#### Hash algoritmi za gesla

Moderni Unix sistemi uporabljajo različne algoritme za zaščito gesel.

Primeri:

- Blowfish,
- MD5,
- SHA-256,
- SHA-512.

---

#### Sekljalni algoritmi (*Hash*)

Hash algoritmi pretvorijo vhodne podatke v enoličen zapis.

Primer:

```text
geslo → hash vrednost
```

Za večjo varnost se uporablja tudi:

- **salt** (naključni dodatni podatek),
- večkratno izvajanje algoritma.

---

#### Kode algoritmov za gesla

| Koda | Algoritem |
|---|---|
| `$1` | MD5 hashing algorithm |
| `$2` | Blowfish algorithm |
| `$3` | Eksblowfish algorithm |
| `$4` | NT hashing algorithm |
| `$5` | SHA-256 algorithm |
| `$6` | SHA-512 algorithm |

---

### Upravljanje diskov in particij

#### Ukaz `fdisk`

Ukaz `fdisk` se uporablja za upravljanje diskov in particij.

Primer:

```bash
fdisk
```

Ukazi, povezani z diski, se uporabljajo predvsem ob nalaganju sistema in pri upravljanju pomnilniških naprav.

---

Računalnik lahko vsebuje:

- en disk,
- več diskov.

Vsak disk lahko razdelimo na več particij.

Primer oznake diska:

```text
/dev/hdb
```

V sistemu Linux so diski in particije predstavljeni kot datoteke v direktoriju:

```text
/dev/
```

---

#### Ukaz `fdisk -l`

Ukaz:

```bash
fdisk -l
```

izpiše informacije o diskih in particijah.

Za podrobnejši izpis določene particije lahko podamo tudi ime particije.

Primer:

```bash
fdisk -l /dev/hdb
```

---

#### Ukaz `df`

Ukaz `df` (*disk free*) prikazuje informacije o uporabi prostora na particijah.

Primer:

```bash
df -H
```

Parameter `-H` omogoča bolj berljiv izpis velikosti.

Ukaz prikaže:

- particije,
- velikost prostora,
- koliko prostora je uporabljenega,
- koliko prostora je še prostega.

Primer:

```text
Filesystem      Size   Used   Available
/dev/hda1       100G    40G       60G
```

---

#### Priklopne točke (*Mount points*)

V Unix/Linux sistemih so diski priključeni preko priklopnih točk (*mount points*).

To pomeni, da se dodatni disk ali particija priključi v določeno mapo znotraj datotečnega sistema.

Primer:

```text
/mnt/disk
```

Unix omogoča tudi priklop diskov iz oddaljenih sistemov.

Primer:

- dostop do diska na oddaljenem računalniku,
- priklop podatkov iz druge lokacije.

Danes se za dostop do oddaljenih podatkov pogosto uporabljajo spletne storitve in oblačne rešitve.

---

#### Premikanje datotek (`move`)

Ukaz `move` oziroma `mv` se uporablja za:

- premikanje datotek,
- spreminjanje imen datotek.

Primer:

```bash
mv datoteka.txt nova_datoteka.txt
```

---

#### Premik datoteke znotraj iste particije

Če premikamo datoteko znotraj iste particije, gre običajno samo za spremembo lokacije oziroma imena.

Primer:

```text
/home/uporabnik/datoteka.txt
```

v:

```text
/home/uporabnik/dokumenti/datoteka.txt
```

Operacija je hitra, ker se podatki dejansko ne kopirajo.

---

#### Premik datoteke med različnimi particijami

Če premikamo datoteko iz ene particije na drugo, mora sistem v ozadju izvesti več korakov:

1. kopiranje datoteke na novo particijo,
2. brisanje originalne datoteke.

Postopek je v ozadju podoben:

```text
COPY → DELETE
```

Primer:

```text
Particija A
     |
     | kopiranje
     ↓
Particija B
     |
     | brisanje originala
```

---

### Delo z oddaljenimi računalniki

#### Ukaz `ssh`

Ukaz `ssh` (*Secure Shell*) omogoča povezavo z oddaljenim računalnikom.

Primer:

```bash
ssh uporabnik@racunalnik
```

Preko povezave SSH lahko:

- dostopamo do oddaljenega računalnika,
- izvajamo ukaze,
- upravljamo datoteke,
- uporabljamo oddaljene storitve.

---

#### Odjava iz oddaljenega računalnika

Za prekinitev povezave uporabimo:

```text
CTRL + C
```

ali:

```bash
exit
```

---

#### Primer: povezava na oddaljeni računalnik

Postopek:

1. prijava na oddaljeni računalnik,
2. pregled sistema,
3. delo z ukazi.

Primer preverjanja sistema:

```bash
uname
```

Pregled prostora:

```bash
df
```

---

#### Primer: prijava na HPC-RIVR

Pri delu z visoko zmogljivimi računalniki (*High Performance Computing - HPC*) se pogosto uporabljajo oddaljene povezave.

Po prijavi lahko preverjamo:

- čakajoče posle (*Jobs*),
- izvajanje procesov,
- obremenitev sistema.

---

### Pregled procesov

#### Ukaz `ps`

Ukaz:

```bash
ps
```

prikaže trenutno izvajajoče procese.

---

#### Ukaz `top`

Ukaz:

```bash
top
```

prikaže trenutno stanje procesov in obremenitev sistema.

Prikaže:

- aktivne procese,
- porabo procesorja,
- porabo pomnilnika.

---

#### Ukaz `htop`

Ukaz:

```bash
htop
```

je izboljšana različica ukaza `top`.

Omogoča bolj pregleden prikaz:

- procesov,
- porabe CPU,
- porabe pomnilnika,
- uporabnikov.

---

#### Oddaljeni dostop v sistemu Windows

Tudi Windows omogoča povezovanje z oddaljenimi računalniki.

Primeri:

- ukazna vrstica (`cmd`),
- PowerShell,
- SSH odjemalci,
- Remote Desktop Protocol (RDP).

Windows ima danes tudi podporo za SSH povezave, zato se lahko povezuje na Unix/Linux sisteme.

---

### Tipi datotek (datotečni sistem)

Datotečni sistem v Unix/Linux sistemih organizira podatke v različne tipe datotek.

Osnovni tipi datotek so:

- **navadne datoteke**,
- **direktoriji**,
- **posebne datoteke**,
- **povezave (*linki*)**,
- **vtičniki (*sockets*)**.

Nekatere vrste datotek, predvsem posebne datoteke in vtičnike, bomo podrobneje spoznali kasneje.

---

#### Datotečni sistem Linux

Linux uporablja hierarhično drevesno strukturo datotečnega sistema.

Osnova celotnega sistema je korenski direktorij:

```text
/
```

Korenski direktorij se imenuje tudi:

- **root**,
- **koren**.

Vsi ostali direktoriji in datoteke izhajajo iz njega.

Primer strukture:

```text
/
├── etc
├── bin
├── dev
├── usr
├── home
│   └── peter
│       └── faks
│           └── SA
└── proc
```

---

#### Pomembni direktoriji v Linux sistemu

##### `/etc`

Direktorij:

```text
/etc
```

vsebuje konfiguracijske datoteke sistema.

Primeri:

- nastavitve uporabnikov,
- nastavitve programov,
- sistemske konfiguracije.

---

##### `/bin`

Direktorij:

```text
/bin
```

vsebuje osnovne izvršne programe in ukaze, ki jih sistem potrebuje za delovanje.

Primeri:

- `ls`,
- `cp`,
- `mv`,
- `cat`.

---

##### `/dev`

Direktorij:

```text
/dev
```

vsebuje posebne datoteke, ki predstavljajo strojne naprave.

Primeri:

- diski,
- USB naprave,
- terminali.

V Linuxu se naprave obravnavajo kot datoteke.

---

##### `/usr`

Direktorij:

```text
/usr
```

vsebuje uporabniške programe, knjižnice in dodatne sistemske datoteke.

---

##### `/home`

Direktorij:

```text
/home
```

vsebuje domače direktorije uporabnikov.

Primer:

```text
/home/peter
```

Predstavlja domačo mapo uporabnika `peter`.

---

##### Uporabniški direktoriji

Primer:

```text
/home/peter/faks/SA
```

predstavlja strukturo:

```text
/home
 └── peter
     └── faks
         └── SA
```

kjer ima uporabnik `peter` svoje osebne datoteke in poddirektorije.

---

##### `/proc`

Direktorij:

```text
/proc
```

je poseben virtualni datotečni sistem.

Vsebuje informacije o:

- procesih,
- jedru sistema,
- trenutnem stanju računalnika.

Podatki v direktoriju `/proc` niso shranjeni na disku, ampak jih sistem ustvari dinamično.

### Datotečni sistem Linux — dodatni direktoriji

#### `/var`

Direktorij:

```text
/var
```

vsebuje podatke, ki se pogosto spreminjajo med delovanjem sistema.

Primeri:

- dnevniki (*log files*),
- informacije o delovanju sistema,
- podatki, ki jih administrator uporablja za pregled dogajanja v sistemu.

Administrator lahko v direktoriju `/var` preveri:

- kaj se je zgodilo v sistemu,
- napake,
- aktivnosti programov in storitev.

---

#### `/lib`

Direktorij:

```text
/lib
```

vsebuje sistemske knjižnice, ki jih potrebujejo programi za svoje delovanje.

---

#### `/lib64`

Direktorij:

```text
/lib64
```

vsebuje 64-bitne sistemske knjižnice.

---

#### `/boot`

Direktorij:

```text
/boot
```

vsebuje datoteke, potrebne za zagon operacijskega sistema.

Primeri:

- zagonski nalagalnik (*bootloader*),
- jedro sistema (*kernel*),
- datoteke povezane z zagonom sistema.

---

#### `/root`

Direktorij:

```text
/root
```

predstavlja domači direktorij uporabnika `root`.

Pomembno:

- `/root` ni enako kot `/`,
- `/` predstavlja korenski direktorij celotnega sistema,
- `/root` je domača mapa administratorja.

---

#### `/media`

Direktorij:

```text
/media
```

se uporablja za priklop zunanjih naprav.

Primeri:

- USB ključki,
- zunanji diski,
- druge izmenljive naprave.

---

#### `/sbin`

Direktorij:

```text
/sbin
```

vsebuje sistemske ukaze, ki jih običajno uporablja administrator.

Primeri:

- upravljanje sistema,
- konfiguracija naprav,
- vzdrževanje sistema.

---

### Datotečni sistem — osnovni ukazi

#### Ukaz `cd`

Ukaz `cd` (*change directory*) omogoča premikanje med direktoriji po drevesni strukturi.

Primer:

```bash
cd IME-DIR
```

Pomembno:

Pri ukazu `cd` moramo paziti na presledek.

Pravilno:

```bash
cd /usr
```

Napačno:

```bash
cd/usr
```

---

#### Domači direktorij

Sam ukaz:

```bash
cd
```

uporabnika premakne v njegov domači direktorij.

Primer:

```bash
cd
```

Uporabnik:

```text
/home/peter
```

se premakne v:

```text
/home/peter
```

---

#### Ukaz `ls`

Ukaz:

```bash
ls
```

izpiše vsebino trenutnega direktorija.

Prikaže:

- datoteke,
- direktorije.

V nekaterih sistemih lahko uporabimo tudi:

```bash
dir
```

---

#### Ukaz `find`

Ukaz:

```bash
find
```

omogoča iskanje datotek in direktorijev.

Primer:

```bash
find /home -name datoteka.txt
```

Podrobneje bo ukaz predstavljen kasneje.

---

#### Tilda (`~`) — domači direktorij

Znak:

```text
~
```

predstavlja domači direktorij uporabnika.

Primer:

```bash
cd ~
```

uporabnika premakne v njegov domači direktorij.

Primer:

```text
/home/peter
```

---

#### Relativne in absolutne poti

Poti uporabljamo pri:

1. premikanju po direktorijski strukturi,
2. pisanju ukazov in skript.

Nekateri programi zahtevajo uporabo absolutnih poti.

---

##### Absolutna pot

Absolutna pot je pot, ki se začne s poševnico:

```text
/
```

Primer:

```bash
cd /usr/local/bin
```

Pot:

```text
/usr/local/bin
```

je absolutna pot, ker se začne pri korenskem direktoriju.

---

##### Relativna pot

Relativna pot je določena glede na trenutni direktorij.

Primer:

```bash
cd ../local/bin
```

ali:

```bash
cd .ssh
```

---

#### Primeri poti

#### Absolutna pot

```bash
cd /usr/local/bin
```

Začne se iz korenskega direktorija.

---

#### Trenutni direktorij (`.`)

Pika:

```text
.
```

predstavlja trenutni direktorij.

Primer:

```bash
cd ./ssh
```

pomeni:

premik v direktorij `ssh`, ki se nahaja v trenutnem direktoriju.

---

#### Nadrejeni direktorij (`..`)

Dve piki:

```text
..
```

predstavljata nadrejeni direktorij.

Primer:

```bash
cd ..
```

premakne uporabnika eno raven višje v drevesni strukturi.

Primer:

```text
/home/peter/faks
```

ukaz:

```bash
cd ..
```

premakne v:

```text
/home/peter
```

---

#### Skriti direktoriji

V Linuxu se skriti direktoriji začnejo s piko.

Primer:

```text
.ssh
```

je skriti direktorij.

Za prikaz skritih datotek uporabimo:

```bash
ls -a
```

Primer:

```bash
ls -a
```

prikaže tudi:

```text
.ssh
```

Premik v skriti direktorij:

```bash
cd ./.ssh
```

---

#### Okoljske spremenljivke (*Environment variables*)

Ko se uporabnik prijavi v sistem, se nastavijo okoljske spremenljivke.

Te spremenljivke:

- shranjujejo informacije o okolju,
- olajšajo delo uporabnika,
- programom povedo pomembne nastavitve.

Nekateri programi zahtevajo:

- absolutne poti,
- relativne poti.

---

### Osnovni ukazi za pregled tekstovnih datotek

#### Ukaz `cat`

Ukaz:

```bash
cat
```

izpiše vsebino tekstovne datoteke.

Primer:

```bash
cat a.txt
```

Možno je izpisati več datotek:

```bash
cat b.txt c.txt
```

---

#### Ukaz `more`

Ukaz:

```bash
more
```

omogoča prikaz datotek po straneh.

Omogoča:

- premikanje po vsebini,
- iskanje vzorcev.

---

#### Ukaz `less`

Ukaz:

```bash
less
```

je podoben ukazu `more`, vendar je bolj uporaben.

Omogoča:

- premikanje naprej in nazaj,
- iskanje po vsebini,
- boljši pregled velikih datotek.

---

#### Imena datotek v Linuxu

V Linuxu lahko:

- ime datoteke začne z znakom `-`,
- ime datoteke vsebuje posebne znake.

Zaradi tega moramo biti pri uporabi ukazov previdni.

---

### Brisanje datotek in direktorijev

#### Ukaz `rm`

Ukaz:

```bash
rm
```

se uporablja za brisanje datotek.

Primer:

```bash
rm datoteka.txt
```

Pomembno:

Linux nima klasičnega ukaza **undo**.

Ko datoteko izbrišemo, je lahko ni mogoče obnoviti.

---

#### Brisanje več datotek

Primer:

```bash
rm *
```

Ukaz:

```bash
rm *
```

izbriše vse datoteke v trenutnem direktoriju.

Pri tem je potrebno biti zelo previden.

---

#### Rekurzivno brisanje (`rm -r`)

Za brisanje direktorijev in njihove vsebine uporabimo:

```bash
rm -r
```

Primer:

```bash
rm -r direktorij
```

Parameter `-r` pomeni rekurzivno brisanje.

To pomeni, da izbriše:

- direktorij,
- vse poddirektorije,
- vse datoteke znotraj direktorija.

---

#### Opozorilo pri ukazu `rm`

Ukazi:

```bash
rm *
```

in

```bash
rm -r *
```

so nevarni, saj lahko izbrišejo veliko količino podatkov.

Pred uporabo je potrebno vedno preveriti:

- trenutni direktorij,
- datoteke, ki jih bomo izbrisali.

#### Izpis datotek in direktorijev z ukazom `ls`

Ukaz:

```bash
ls
```

izpiše vsebino trenutnega direktorija.

Za podrobnejši izpis uporabimo:

```bash
ls -l
```

Primer:

```text
drwxr-xr-x  2 root root 4096 mar  8 15:58 proc
drwxr-xr-x  2 root root 4096 mar  8 15:58 root
drwxr-xr-x  2 root root 4096 mar  8 15:58 run
drwxr-xr-x  2 root root 4096 mar  8 15:58 sbin
drwxr-xr-x  2 root root 4096 mar  8 15:58 srv
drwxr-xr-x  2 root root 4096 mar  8 15:58 sys
drwxr-xr-x  2 root root 4096 mar  8 15:58 tmp
drwxr-xr-x  2 root root 4096 mar  8 15:58 usr
drwxr-xr-x  2 root root 4096 mar  8 15:58 var
```

---

#### Razlaga izpisa `ls -l`

Primer:

```text
drwxr-xr-x
```

Prvi znak predstavlja tip datoteke:

| Znak | Pomen |
|---|---|
| `-` | navadna datoteka |
| `d` | direktorij |
| `l` | simbolična povezava (*link*) |
| `p` | cev (*pipe*) |

---

#### Pravice dostopa (`rwx`)

Primer:

```text
drwxr-xr-x
```

Za prvim znakom sledijo tri skupine pravic:

```text
d rwx r-x r-x
  |   |   |
  |   |   └── ostali uporabniki
  |   └────── skupina
  └────────── lastnik
```

Pravice:

| Znak | Pomen |
|---|---|
| `r` | read (branje) |
| `w` | write (pisanje) |
| `x` | execute (izvajanje) |

---

#### Primer zaščite datoteke

Primer:

```text
-rwxr-xr--
```

Pomen:

```text
- rwx r-x r--
| |   |   |
| |   |   └── ostali uporabniki
| |   └────── skupina
| └────────── lastnik
|
└──────────── navadna datoteka
```

---

#### Dodatni podatki pri `ls -l`

Primer:

```text
-rwxr-xr-x 1 janez janez 243 mar 8 15:58 file.txt
```

Izpis vsebuje:

| Podatek | Pomen |
|---|---|
| `-rwxr-xr-x` | zaščita datoteke |
| `1` | število povezav |
| `janez` | lastnik datoteke |
| `janez` | skupina |
| `243` | velikost datoteke |
| `mar 8 15:58` | datum spremembe |
| `file.txt` | ime datoteke |

---

#### Povezave in simbolični linki

Drugi stolpec pri `ls -l` prikazuje število povezav.

Primer:

```text
2
```

predstavlja število povezav do datoteke ali direktorija.

Simbolični linki so posebne datoteke, ki kažejo na drugo datoteko ali direktorij.

Primer:

```text
lrwxrwxrwx
```

Prvi znak:

```text
l
```

pomeni, da gre za simbolično povezavo.

---

#### Dodatne možnosti ukaza `ls`

#### Izpis po času

Ukaz:

```bash
ls -t
```

razvrsti datoteke glede na čas spremembe.

Novejše datoteke so prikazane na vrhu.

---

#### Iskanje po vzorcih

Ukaz `ls` lahko uporabljamo tudi za iskanje po vzorcih.

Primer:

```bash
ls *.txt
```

izpiše vse datoteke s končnico:

```text
.txt
```

---

#### Zaščita datotek in direktorijev

Zaščito datotek vidimo z ukazom:

```bash
ls -l
```

Primer:

```text
-rwxr-xr--
```

---

#### Lastnik, skupina in ostali

Pri zaščiti imamo tri uporabniške skupine:

| Oznaka | Pomen |
|---|---|
| `u` | uporabnik oziroma lastnik (*user/owner*) |
| `g` | skupina (*group*) |
| `o` | ostali (*others*) |

---

#### Spreminjanje pravic z ukazom `chmod`

Ukaz:

```bash
chmod
```

spreminja pravice datotek in direktorijev.

---

#### Dodajanje pravice izvajanja

Primer:

```bash
chmod u+x file
```

Doda pravico izvajanja (`execute`) lastniku datoteke.

---

#### Odstranjevanje pravice pisanja

Primer:

```bash
chmod u-w file
```

Odstrani pravico pisanja (`write`) lastniku.

---

#### Razlika med zaščito datotek in direktorijev

Zaščita direktorijev in datotek ni popolnoma enaka.

Pri datotekah:

- `r` omogoča branje vsebine,
- `w` omogoča spreminjanje vsebine,
- `x` omogoča izvajanje programa.

Pri direktorijih:

- `r` omogoča ogled vsebine direktorija,
- `w` omogoča dodajanje in brisanje datotek,
- `x` omogoča dostop do direktorija.

---

#### Izvajanje programov

Če datoteka nima pravice izvajanja:

```bash
./program
```

ne bo delovala.

Dodamo pravico izvajanja:

```bash
chmod +x program
```

Sedaj lahko program zaženemo:

```bash
./program
```

---

#### Interpretiranje ukazov

Pri interpretiranih programih ukazni interpreter bere program ukaz po ukazu.

Preverja:

- pravilnost ukazov,
- izvajanje posameznih ukazov.

---

#### Brisanje zagnanega programa

Primer:

Zaženemo program:

```bash
./a.out
```

Nato izbrišemo datoteko:

```bash
rm a.out
```

Program lahko še vedno deluje.

Razlog:

- program je že naložen v pomnilnik (RAM),
- njegova koda se še vedno izvaja,
- datoteke na disku pa ni več.

Ko bi želeli program ponovno zagnati:

```bash
./a.out
```

to ne bi bilo mogoče, ker datoteka na disku ne obstaja več.

---

#### Privzete pravice in ukaz `umask`

Ko ustvarimo novo datoteko:

```bash
touch datoteka.txt
```

sistem določi začetne pravice.

Privzete pravice preverimo z ukazom:

```bash
umask
```

Primer:

```bash
umask
```

Rezultat:

```text
0002
```

---

#### Kaj pomeni `umask`?

`umask` določa, katere pravice se odstranijo pri ustvarjanju novih datotek in direktorijev.

Primer:

```text
0002
```

pomeni:

- od privzetih pravic se odšteje vrednost `2`,
- uporabniki iz skupine ostalih nimajo pravice pisanja.

---

#### Primer pravic pri `umask 0002`

Pri privzeti vrednosti:

```text
umask = 0002
```

se ustvarijo:

#### Nove datoteke:

```text
664
```

oziroma:

```text
rw-rw-r--
```

#### Novi direktoriji:

```text
775
```

oziroma:

```text
rwxrwxr-x
```

---

#### Zaščita direktorijev

Pri direktorijih se zaščita začne z:

```text
d
```

Primer:

```text
drwxr-xr-x
```

Pomen:

```text
d rwx r-x r-x
| |   |   |
| |   |   └── ostali
| |   └────── skupina
| └────────── lastnik
|
└──────────── direktorij
```

Direktoriji uporabljajo enake oznake:

- `r` - read,
- `w` - write,
- `x` - execute,

vendar imajo drugačen pomen kot pri navadnih datotekah.

---

### Ukazi za delo z datotekami in skriptami

#### Primer uporabe ukaza `ls`

Ukaz:

```bash
ls
```

izpiše vsebino trenutnega direktorija.

Primer:

```bash
ls /
```

izpiše vsebino korenskega direktorija.

Rezultat:

```text
bin
boot
dev
etc
home
lib
lib64
media
mnt
opt
proc
root
run
sbin
sys
tmp
usr
var
```

---

#### Povezovanje ukazov s cevjo (`pipe`)

V Unix/Linux sistemih lahko ukaze izvajamo na več načinov:

1. posamezno,
2. kot zaporedje ukazov z uporabo cevi (*pipe*),
3. kot skripte.

---

#### Pipe (`|`)

Pipe omogoča, da izhod enega ukaza uporabimo kot vhod drugega ukaza.

Primer:

```bash
ls / | grep bin
```

Postopek:

1. `ls /` izpiše vse direktorije v korenskem direktoriju,
2. `grep bin` izbere samo vrstice, ki vsebujejo besedo `bin`.

Rezultat:

```text
bin
sbin
```

---

#### Primer: izpis števila datotek v direktoriju

Za izpis števila datotek v direktoriju lahko uporabimo več ukazov skupaj.

Primer:

```bash
ls /bin | wc -l
```

Postopek:

- `ls /bin` izpiše vsebino direktorija `/bin`,
- `wc -l` prešteje število vrstic.

Rezultat predstavlja število datotek v direktoriju.

---

#### Ukaz `awk`

Ukaz:

```bash
awk
```

omogoča obdelavo in izpis podatkov po določenih pravilih.

Primer:

```bash
ls -l | awk '{print $9}'
```

Ukaz izpiše samo deveti stolpec iz izpisa ukaza `ls -l`.

Ker deveti stolpec običajno vsebuje ime datoteke, dobimo seznam imen datotek.

---

#### Bash skripte

Namesto zaporednega pisanja ukazov lahko ukaze shranimo v skripto.

Primer:

```bash
delo.sh
```

V skripti imamo lahko zapisane ukaze:

```bash
set -x

ls /bin
ls /usr/bin
ls /usr/sbin

set +x
```

---

#### Zagon bash skripte

Skripto zaženemo z ukazom:

```bash
bash delo.sh
```

Primer rezultata:

```text
+ ls /bin
162

+ ls /usr/bin
2904

+ ls /usr/sbin
271
```

---

#### Ukaz `set`

Ukaz `set` omogoča dodatne nastavitve izvajanja skript.

#### Prikaz izvajanja ukazov (`set -x`)

Ukaz:

```bash
set -x
```

vključi izpis ukazov, ki se izvajajo.

Primer:

```text
+ ls /bin
162
```

Znak:

```text
+
```

pomeni, da je ukaz izpisan pred njegovim izvajanjem.

---

#### Izklop izpisa (`set +x`)

Ukaz:

```bash
set +x
```

izklopi prikaz izvajanja ukazov.

---

#### Ukaz `file`

Ukaz:

```bash
file
```

prikaže informacije o datotekah.

Primer:

```bash
file *
```

izpiše informacije o vseh datotekah v trenutnem direktoriju.

Primeri rezultatov:

```text
document.pdf: PDF document
log.txt: ASCII text
program: executable file
```

Ukaz lahko prepozna vrste datotek:

- PDF,
- tekstovne datoteke,
- dnevnike (*log*),
- izvršne programe,
- druge formate.

---

#### Ukaz `cat`

Ukaz:

```bash
cat
```

izpiše vsebino datoteke.

Primer:

```bash
cat delo.sh
```

Rezultat:

```bash
set -x
ls /bin
ls /usr/bin
ls /usr/sbin
set +x
```

---

#### Uporaba ukaza `cat`

Ukaz `cat` je uporaben pri:

- pregledovanju vsebine datotek,
- preverjanju skript,
- odpravljanju napak (*debugging*).

Pri skriptah lahko z ukazom `cat` preverimo:

- kako so ukazi zapisani,
- v kakšnem vrstnem redu se izvajajo,
- ali vsebujejo napake.

---

#### Prva vrstica bash skripte

Vsaka bash skripta običajno vsebuje prvo vrstico:

```bash
#!/bin/bash
```

Ta vrstica določa:

- kateri ukazni interpreter naj se uporabi,
- da se bo skripta izvajala z uporabo Bash lupine.

Ta vrstica se imenuje:

```text
shebang
```

---

#### Primer bash skripte

```bash
#!/bin/bash

set -x

ls /bin
ls /usr/bin
ls /usr/sbin

set +x
```

Ko sistem zažene skripto, prebere prvo vrstico in uporabi navedeni interpreter:

```text
/bin/bash
```

---

### Datotečni sistem

Linux uporablja **hierarhični datotečni sistem**.

To pomeni, da so datoteke in direktoriji organizirani v drevesno strukturo, kjer je osnova:

```text
/
```

(korenski direktorij oziroma *root*).

---

#### Hierarhični datotečni sistem

Glavne značilnosti:

- vse particije (razen korenske particije) lahko priklopimo kjerkoli v datotečni hierarhiji,
- datoteke in direktoriji so opisani s posebno podatkovno strukturo, imenovano **inode**,
- vsaka datoteka ima svojo pot v datotečnem sistemu,
- datoteke imajo določeno:
  - lastništvo,
  - skupino,
  - dovoljenja oziroma zaščite.

---

##### Particije in priklop

Disk je razdeljen na particije.

Na particije se nato nanaša operacijski sistem.

Primer:

```text
Disk
│
├── particija 1
├── particija 2
└── particija 3
```

V Linuxu lahko particije priklopimo (*mount*) na različna mesta v datotečni hierarhiji.

Primer:

```text
/
├── home
├── var
└── data
```

Določena particija je lahko priklopljena na:

```text
/home
```

ali:

```text
/data
```

---

##### Korenska particija (`root`)

Korenska particija:

```text
/
```

je posebna.

Drugih particij ne moremo priklopiti kot zamenjavo za korensko particijo.

Razlog:

- varnost,
- osnovno delovanje sistema,
- sistem mora imeti začetno točko za zagon.

---

### Inode

#### Kaj je inode?

**Inode** je posebna podatkovna struktura, ki opisuje zgradbo datotek in direktorijev.

Shranjuje informacije o datoteki, kot so:

- lastnik,
- skupina,
- dovoljenja,
- velikost,
- lokacija podatkov na disku,
- čas sprememb.

Sama vsebina datoteke ni shranjena v inode, ampak inode kaže na lokacijo podatkov.

---

#### Prikaz inode podatkov

Običajen ukaz:

```bash
ls -l
```

prikaže osnovne informacije.

Če uporabimo:

```bash
ls -li
```

dobimo tudi številko inode.

Primer:

```text
123456 -rw-r--r-- 1 janez users 1024 file.txt
```

Prva številka:

```text
123456
```

predstavlja inode številko.

---

#### Uporaba inode

Navadni uporabniki inode podatkov običajno ne uporabljajo neposredno.

Inode je predvsem pomemben pri:

- upravljanju datotečnih sistemov,
- administraciji sistema,
- odpravljanju težav.

---

#### Priklop datotečnih sistemov (*mount*)

##### Ukaz `mount`

Ukaz:

```bash
mount
```

se uporablja za priklop datotečnih sistemov.

Primer:

```bash
mount
```

brez dodatnih parametrov izpiše trenutno priklopljene datotečne sisteme.

---

#### Priklop ob zagonu sistema

Ukaz `mount` se uporablja tudi med zagonom računalnika.

Postopek zagona:

1. sistem prebere informacije o particijah,
2. priklopi potrebne datotečne sisteme,
3. omogoči dostop do podatkov.

Particija se najprej pogosto priklopi za branje:

```text
read
```

nato pa se omogoči tudi pisanje:

```text
write
```

---

#### Datoteka `/etc/fstab`

Informacije o samodejnem priklopu particij so zapisane v:

```text
/etc/fstab
```

Pregled datoteke:

```bash
cat /etc/fstab
```

Datoteka vsebuje informacije:

- katera particija se priklopi,
- kam se priklopi,
- kateri datotečni sistem uporablja,
- možnosti priklopa.

---

#### Ukaz `umount`

Ukaz:

```bash
umount
```

se uporablja za odklop priklopljenega datotečnega sistema.

Primer:

```bash
umount /dev/sdb1
```

---

#### Ukaz `findmnt`

Ukaz:

```bash
findmnt
```

omogoča pregled priklopljenih datotečnih sistemov.

Primer:

```bash
findmnt
```

Prikaže:

- naprave,
- priklopne točke,
- vrste datotečnih sistemov.

---

#### Standardni vhodi in izhodi

##### `stdin`

`stdin` (*standard input*) predstavlja standardni vhod programa.

Podatki se običajno berejo iz:

- tipkovnice,
- drugega procesa,
- datoteke.

Vhodni podatki se obdelujejo v glavnem pomnilniku.

---

#### Dovoljenja in pravice datotek

Pravice datotek vidimo z ukazom:

```bash
ls -l
```

Primer:

```text
lrwxrwxrwx
-rwsr-xr-x
```

---

#### Simbolične povezave

Primer:

```text
lrwxrwxrwx
```

Prvi znak:

```text
l
```

pomeni:

```text
link
```

oziroma simbolično povezavo.

---

#### Posebne pravice (`set-user-id`)

Primer:

```text
-rwsr-xr-x
```

Črka:

```text
s
```

na mestu pravice izvajanja pomeni:

```text
set-user-id
```

---

##### Posebne vrste datotek

Prvi znak pri izpisu `ls -l` določa tip datoteke.

Primer:

```text
crwxrwxrwx
```

---

##### Znak `c`

Če je prvi znak:

```text
c
```

gre za **znakovno napravo** (*character device*).

Podatki se berejo znak po znak.

Primeri:

- terminali,
- vhodne naprave.

---

##### Znak `b`

Če je prvi znak:

```text
b
```

gre za **bločno napravo** (*block device*).

Podatki se berejo v blokih oziroma straneh.

Primeri:

- trdi diski,
- particije.

---

##### Povzetek pomembnih ukazov

| Ukaz | Namen |
|---|---|
| `ls -li` | Prikaže datoteke skupaj z inode številko |
| `mount` | Prikaže ali priklopi datotečne sisteme |
| `umount` | Odklopi datotečni sistem |
| `cat /etc/fstab` | Prikaže konfiguracijo priklopa |
| `findmnt` | Prikaže priklopljene datotečne sisteme |
| `ls -l` | Prikaže pravice in lastništvo datotek |

---

#### Podatkovna struktura inode

Primer ukaza:

```bash
ls -l /bin
```

Pri izpisu datotek Linux uporablja podatke, ki so shranjeni v podatkovni strukturi **inode**.

---

##### Kaj vsebuje inode?

Za vsako datoteko ali direktorij je v inode shranjeno:

- kdo je lastnik datoteke,
- kateri skupini pripada datoteka,
- tip datoteke,
- pravice dostopa,
- čas dostopa,
- čas spremembe,
- število povezav do datoteke,
- velikost datoteke,
- diskovna naprava, kjer se datoteka nahaja.

---

##### Podatki v inode

Primer podatkov:

| Podatek | Opis |
|---|---|
| `uid` | ID uporabnika, ki je lastnik datoteke |
| `gid` | ID skupine lastnika |
| `mode` | tip datoteke in dovoljenja |
| `ino` | številka inode |
| `size` | velikost datoteke |
| `blocks` | število zasedenih blokov |
| `atime` | čas zadnjega dostopa |
| `mtime` | čas zadnje spremembe vsebine |
| `ctime` | čas zadnje spremembe statusa |

---

#### Struktura `stat`

Podatke o datoteki lahko dobimo preko sistemskega klica:

```text
stat(2)
```

Primer strukture:

```c
struct stat
{
    dev_t     st_dev;
    ino_t     st_ino;
    mode_t    st_mode;
    uid_t     st_uid;
    gid_t     st_gid;
    dev_t     st_rdev;
    off_t     st_size;
    blksize_t st_blksize;
    blkcnt_t  st_blocks;
    time_t    st_atime;
    time_t    st_mtime;
    time_t    st_ctime;
};
```

---

#### Pomen elementov strukture `stat`

| Element | Pomen |
|---|---|
| `st_dev` | številka naprave |
| `st_ino` | številka inode |
| `st_mode` | zaščita in tip datoteke |
| `st_uid` | ID lastnika |
| `st_gid` | ID skupine |
| `st_size` | velikost datoteke v bajtih |
| `st_blocks` | število zasedenih blokov |
| `st_atime` | čas zadnjega dostopa |
| `st_mtime` | čas zadnje spremembe vsebine |
| `st_ctime` | čas zadnje spremembe statusa |

---

#### Številke inode

V strukturi `stat` imamo zapisane številke inode.

Pomembno:

- inode številke so unikatne znotraj posamezne particije,
- pri različnih particijah se lahko iste številke ponovijo.

Primer:

```text
Particija 1:
inode 2

Particija 2:
inode 2
```

To ni napaka, saj sta particiji ločeni.

---

#### Preverjanje pravic pred izvedbo ukaza

Preden sistem dovoli določeno operacijo, mora preveriti podatke v inode.

Primer:

Uporabnik želi:

- prebrati datoteko,
- spremeniti datoteko,
- zagnati program.

Sistem najprej preveri:

- kdo je lastnik,
- kateri skupini pripada,
- kakšne so pravice dostopa.

Šele nato dovoli ali zavrne operacijo.

---

#### Časi datotek

Linux uporablja tri pomembne čase.

---

#### `atime` — čas dostopa

(*Access time*)

Shranjuje:

- kdaj je bila datoteka nazadnje prebrana.

---

#### `mtime` — čas spremembe

(*Modification time*)

Shranjuje:

- kdaj je bila vsebina datoteke nazadnje spremenjena.

---

#### `ctime` — čas spremembe statusa

(*Change time*)

Shranjuje:

- kdaj so bili nazadnje spremenjeni podatki o datoteki.

Primer:

- sprememba pravic,
- sprememba lastnika,
- sprememba skupine.

---

#### Indirektni bloki v inode

Datoteka je na disku shranjena v blokih.

Majhne datoteke lahko zasedejo samo en blok.

Pri velikih datotekah (npr. več sto MB ali GB) se podatki razdelijo v več blokov.

Vprašanje:

Kako sistem ve, kje se nahajajo vsi deli datoteke?

Odgovor:

Uporablja kazalce v inode.

---

#### Neposredni kazalci

Prvih nekaj kazalcev v inode neposredno kaže na bloke podatkov.

Primer:

```text
inode
 |
 +---- Data Block
 |
 +---- Data Block
 |
 +---- Data Block
```

---

#### Indirektni kazalci

Pri večjih datotekah inode vsebuje kazalce na bloke kazalcev.

Primer:

```text
inode
 |
 +---- Indirect Block
          |
          +---- Data Block
          |
          +---- Data Block
```

---

#### Zelo velike datoteke

Pri zelo velikih datotekah lahko obstajajo:

- enojno indirektni bloki,
- dvojno indirektni bloki,
- trojno indirektni bloki.

Večja kot je datoteka, več nivojev kazalcev mora sistem pregledati.

---

#### Tipi datotek

Linux pozna več vrst datotek:

- navadne datoteke,
- direktorije,
- posebne datoteke,
- povezave (*linki*),
- vtičnike (*sockets*).

---

#### Posebne pravice datotek — SUID bit

Pri običajnih pravicah:

```text
rwx
```

lahko na mestu `x` vidimo:

```text
s
```

Primer:

```text
-rwsr-xr-x
```

To pomeni:

- nastavljen je **SUID bit**,
- program se izvaja s pravicami lastnika datoteke.

---

#### Primer SUID

Ukaz:

```bash
ls -l /usr/bin/passwd
```

Rezultat:

```text
-rwsr-xr-x 1 root root 47032 jan 27 01:50 /usr/bin/passwd
```

Opazimo:

```text
s
```

namesto:

```text
x
```

---

##### Zakaj uporablja ukaz `passwd` SUID?

Datoteka:

```text
/etc/passwd
```

in:

```text
/etc/shadow
```

vsebujeta informacije o uporabnikih in geslih.

Navaden uporabnik nima pravice pisanja v datoteko `shadow`.

Kljub temu mora uporabnik lahko spremeniti svoje geslo.

Zato:

- program `passwd` ima SUID,
- program se izvaja z dovoljenji lastnika (`root`),
- uporabniku omogoči varno spremembo gesla.

---

#### Setuid

**Setuid** omogoča, da uporabnik zažene program z dovoljenji lastnika datoteke.

Primer:

Datoteka:

```text
root
 |
 passwd
```

Uporabnik:

```text
janez
```

zažene:

```bash
passwd
```

Program se izvaja kot:

```text
root
```

vendar samo za namen spremembe gesla.

---

#### Varnost SUID datotek

Datoteke s SUID bitom so pomembne za varnost.

Napadalci pogosto iščejo:

- programe s SUID pravicami,
- napačno nastavljene privilegije.

Primer preverjanja:

```bash
find / -perm -4000
```

---

#### Setgid (SGID)

Setgid deluje podobno kot SUID, vendar uporablja skupine.

Namesto:

```text
uid
```

uporablja:

```text
gid
```

---

##### SGID na datotekah

Če je nastavljen na datoteko:

```text
-rwxr-sr-x
```

se program izvaja s pravicami skupine lastnika.

---

##### SGID na direktorijih

Pri direktorijih ima posebno funkcijo.

Če je nastavljen:

- nove datoteke v direktoriju podedujejo skupino direktorija.

To je uporabno pri sodelovanju več uporabnikov.

Primer:

Skupina:

```text
projekt
```

Direktorij:

```text
/projekt
```

Vsi novi dokumenti bodo pripadali skupini:

```text
projekt
```

---

#### Primer ukaza chmod za SUID

Dodajanje SUID:

```bash
sudo chmod u+s /usr/bin/whoami
```

Odstranjevanje SUID:

```bash
sudo chmod u-s /usr/bin/whoami
```

---

#### Ukaz `whoami`

Ukaz:

```bash
whoami
```

izpiše trenutno uporabniško ime.

Primer:

Če smo prijavljeni kot root:

```bash
whoami
```

rezultat:

```text
root
```

---

#### Povzetek posebnih bitov

| Bit | Namen |
|---|---|
| SUID | program se izvaja kot lastnik datoteke |
| SGID | program se izvaja kot skupina lastnika |
| Sticky bit | omeji brisanje datotek v direktorijih |

---

#### Varnostno opozorilo

Datoteke s posebnimi biti (`s`) moramo posebej preverjati.

Razlog:

Napadalci pri napadih pogosto iščejo:

- SUID programe,
- napačno nastavljene pravice,
- programe, ki omogočajo pridobitev višjih privilegijev.

---

#### Delo z direktoriji in posebne pravice

##### Primeri ukaza `ls`

Ukaz:

```bash
ls -l primeri/
```

izpiše podroben seznam datotek in direktorijev.

Primer:

```text
drwxr-xr-x 2 janez janez 4096 Mar 23 12:11 primeri
```

---

##### Izpis informacij o direktoriju

Ukaz:

```bash
ls -ld primeri/
```

izpiše informacije o samem direktoriju in ne o njegovi vsebini.

Primer:

```text
drwxr-xr-x 2 janez janez 4096 Mar 23 12:11 primeri
```

---

##### Ukaz `cd -`

Ukaz:

```bash
cd -
```

deluje kot nekakšen **undo za ukaz `cd`**.

Primer:

Uporabnik je trenutno v:

```text
/home/janez
```

Nato izvede:

```bash
cd mapa1
cd mapa2
cd mapa3
```

Sedaj se nahaja v:

```text
/home/janez/mapa1/mapa2/mapa3
```

Če izvede:

```bash
cd -
```

se vrne nazaj na prejšnjo lokacijo:

```text
/home/janez
```

Ukaz omogoča hitro vračanje na zadnji obiskani direktorij.

---

### Sticky bit (`t` bit)

#### Kaj je sticky bit?

Sticky bit je posebna pravica v Linux datotečnem sistemu.

Prikaže se na mestu, kjer bi običajno pričakovali **pravico izvajanja (x - execute)**:

```text
x
```

namesto tega pa vidimo:

```text
t
```

Primer:

```text
drwxrwxrwt
```

---

#### Primer: direktorij `/tmp`

Direktorij:

```text
/tmp
```

se uporablja za shranjevanje začasnih datotek.

Primer izpisa:

```bash
ls -ld /tmp
```

Rezultat:

```text
drwxrwxrwt 26 root root 20480 Apr 4 12:25 /tmp
```

Opazimo:

```text
t
```

na koncu pravic.

---

#### Namen sticky bita

Brez sticky bita:

- uporabniki z možnostjo pisanja lahko brišejo tudi datoteke drugih uporabnikov.

S sticky bitom:

- vsi uporabniki lahko berejo in pišejo v direktorij,
- vsak uporabnik lahko briše samo svoje datoteke,
- `root` lahko briše vse datoteke.

---

#### Primer uporabe

Ustvarjanje direktorija:

```bash
mkdir /foo
```

Dodelitev vseh pravic:

```bash
chmod 777 /foo
```

Dodajanje sticky bita:

```bash
chmod o+t /foo
```

Odstranjevanje sticky bita:

```bash
chmod o-t /foo
```

---

#### Primer sticky bita

```text
drwxrwxrwt
```

Pomen:

```text
d rwx rwx rw t
| |   |   |
| |   |   └── sticky bit
| |   └────── ostali uporabniki
| └────────── skupina
└──────────── lastnik
```

---

### Namestitev paketov v različnih sistemih

Operacijski sistemi uporabljajo različne sisteme za nameščanje paketov.

Primeri:

| Sistem | Orodje |
|---|---|
| Darwin / Mac OS X | Fink |
| Debian | `dpkg`, `apt-get` |
| FreeBSD/OpenBSD | Ports |
| Gentoo Linux | Portage |
| IRIX | Tardist |
| NetBSD | pkgsrc |
| Slackware Linux | `.tgz` paketi |
| Solaris | pkg |
| GNU/Linux | različni upravljalniki paketov |

---

#### Pogosti ukazi GNU/Linux in Unix

Najpogosteje uporabljeni ukazi:

##### Navadni uporabnik

| Ukaz | Namen |
|---|---|
| `cat` | izpis vsebine datotek |
| `less` | pregled datotek po straneh |
| `more` | pregled datotek |
| `ls` | izpis datotek in direktorijev |
| `find` | iskanje datotek |
| `grep` | iskanje vzorcev |
| `awk` | obdelava podatkov |

---

##### Ukaz `lsof`

###### List Open Files

Ukaz:

```bash
lsof
```

pomeni:

```text
list open files
```

Uporablja se za pregled:

- katere datoteke uporablja kateri proces,
- koliko datotek je odprtih,
- katere knjižnice uporablja proces.

---

##### Proces ID (`PID`)

Vsak proces ima svojo številko:

```text
PID
```

(*Process ID*)

PID omogoča identifikacijo procesa.

---

##### Primer uporabe

Ukaz:

```bash
lsof -p 2099
```

izpiše informacije o procesu:

```text
PID = 2099
```

Prikaže:

- odprte datoteke,
- uporabljene knjižnice,
- naprave.

---

##### Primerjava izvajanja programa in brisanja datoteke

Ko zaženemo program:

```bash
./program
```

se program:

1. prenese iz diska v RAM,
2. začne izvajati.

Če nato izbrišemo datoteko:

```bash
rm program
```

program še vedno teče.

Razlog:

- koda programa je že v pomnilniku,
- diskovna datoteka ni več potrebna za trenutno izvajanje.

Težava nastane, ko želimo program ponovno zagnati:

```bash
./program
```

To ni več mogoče, ker datoteke na disku ni.

---

### Ukazi v bash skriptah

#### Izvajanje ukaza znotraj spremenljivke

V bashu lahko uporabimo:

```bash
$()
```

Znotraj oklepajev izvedemo ukaz.

Primer:

```bash
B=$(seq 7)
```

Ukaz:

```bash
seq 7
```

izpiše:

```text
1
2
3
4
5
6
7
```

Rezultat se shrani v spremenljivko:

```text
B
```

---

#### PID trenutnega procesa

Posebna spremenljivka:

```bash
$$
```

vrne PID trenutnega procesa.

Primer:

```bash
echo $$
```

izpiše PID ukaznega interpreterja.

---

#### Dodatne možnosti ukaza `lsof`

##### Datoteke uporabnika

Ukaz:

```bash
lsof -u janez
```

prikaže datoteke, ki jih uporablja uporabnik:

```text
janez
```

---

##### Omrežne povezave

Ukaz:

```bash
lsof -i -p 2063
```

prikaže:

- omrežne povezave procesa,
- odprte porte,
- komunikacijo preko omrežja.

---

##### Prikaz PID procesov

Možnost:

```bash
-t
```

prikaže samo PID procesa.

---

##### Direktorij

Možnost:

```bash
+D
```

prikaže datoteke povezane z določenim direktorijem.

Primer:

```bash
lsof +D /home/janez
```

---

#### Ukaz `awk`

`awk` je močno orodje za obdelavo tekstovnih podatkov.

Omogoča:

- delo z vrsticami,
- delo s stolpci,
- spreminjanje podatkov,
- dodajanje in odstranjevanje podatkov.

---

#### Prednosti ukaza `awk`

Z `awk` lahko izvajamo obdelavo podatkov brez pisanja posebnega programa v jeziku C.

Omogoča podobne operacije:

- branje podatkov,
- filtriranje,
- spreminjanje,
- izpis rezultatov.

Primer:

```bash
ls -l | awk '{print $9}'
```

izpiše samo imena datotek.

---

### Informacije o sistemu

#### Ukaz `dmesg`

Ukaz:

```bash
dmesg
```

prikaže sistemska sporočila jedra.

Uporablja se za:

- preverjanje zagona sistema,
- pregled napak,
- pregled naprav.

---

#### Ukaz `inxi`

Ukaz:

```bash
inxi -Fxz
```

izpiše informacije o sistemu.

Primeri informacij:

- procesor,
- pomnilnik,
- grafična kartica,
- disk,
- omrežje,
- različica sistema.

---

## Instalacija programske opreme

### Pregled poglavja

Pri nameščanju programske opreme in operacijskega sistema se srečamo z naslednjimi temami:

- instalacija operacijskega sistema (OS),
- hierarhija datotečnega sistema,
- sistemska programska oprema,
- binarna in izvorna (source) instalacija,
- upravljanje paketov,
- varnostni popravki.

---

### Instalacija operacijskega sistema (OS)

Pri namestitvi operacijskega sistema je potrebno razmisliti o:

- namenu sistema,
- namestitvenem mediju,
- sami namestitvi,
- opravilih po namestitvi.

---

### Namen sistema

Pred namestitvijo operacijskega sistema določimo:

- izbiro strojne opreme,
- strukturo diska,
- izbiro datotečnega sistema,
- izbiro programske opreme.

Izbira je odvisna predvsem od tega, za kakšen namen bo računalnik uporabljen (osebni računalnik, strežnik, razvojno okolje, virtualni strežnik ipd.).

---

### Medij instalacije

Operacijski sistem lahko namestimo preko različnih medijev:

- omrežja,
- USB ključka,
- SD kartice,
- drugih prenosnih medijev.

#### Razvoj skozi čas

Nekoč so se za namestitev uporabljale predvsem:

- diskete,
- CD/DVD mediji.

Danes se najpogosteje uporabljajo:

- USB ključki,
- omrežna namestitev,
- ISO slike.

V prihodnosti bo večina namestitev verjetno potekala neposredno iz oblaka (*cloud*).

---

### Razvoj jedra operacijskega sistema

Vprašanje:

> Ali lahko kdorkoli razvija oziroma dopolnjuje jedro operacijskega sistema?

Odgovor:

Ne. Jedro običajno razvijajo in vzdržujejo razvijalci oziroma skupnost, ki skrbi za posamezen operacijski sistem.

---

### Instalacija sistema

Pri namestitvi operacijskega sistema običajno namestimo:

- jedro operacijskega sistema,
- osnovno sistemsko programsko opremo,
- dodatne programe.

Pri tem je pomembno razmisliti:

- kako dodatna programska oprema vpliva na varnost sistema,
- kako vpliva na zmogljivost sistema.

Več nameščene programske opreme pomeni večjo funkcionalnost, hkrati pa tudi večjo možnost varnostnih ranljivosti.

---

### Virtualni računalniki (Virtual Machine - VM)

Virtualni računalnik (**Virtual Machine - VM**) predstavlja navidezni računalniški sistem, ki deluje znotraj drugega računalniškega sistema.

VM lahko temelji na:

- programski opremi,
- strojni opremi,
- kombinaciji obeh.

---

#### Vrste virtualnih računalnikov

##### Sistemski virtualni računalniki

Predstavljajo popoln navidezni računalnik.

Vključujejo:

- emulacijo strojne opreme,
- operacijski sistem,
- aplikacije.

---

##### Procesni virtualni računalniki

Procesni oziroma aplikacijski virtualni računalniki omogočajo izvajanje posamezne aplikacije znotraj gostiteljskega operacijskega sistema.

Njihov namen je zagotoviti okolje, ki ni odvisno od:

- strojne opreme,
- operacijskega sistema.

Primeri:

- Java Virtual Machine (JVM),
- .NET CLR.

Vir:

https://sl.wikipedia.org/wiki/Virtualno_izvajalsko_okolje

---

### Virtualni sistemi

Pri uporabi virtualnih sistemov razmišljamo o:

- prednostih,
- slabostih,
- vplivu na varnost,
- vplivu na zmogljivost.

---

### Opravila po instalaciji

Po uspešni namestitvi sistema običajno izvedemo:

- registracijo sistema,
- odstranitev nepotrebne programske opreme,
- namestitev posodobitev,
- omogočanje oziroma onemogočanje sistemskih storitev.

Primeri storitev:

- `httpd`
- `sshd`

---

### Hierarhija datotečnega sistema

Datotečni sistem naj bo čim bolj standardiziran.

Nekateri sistemi UNIX standardu sledijo bolj dosledno kot drugi.

Pomembna pojma sta:

- deljeni (*shareable*) podatki,
- nedeljeni (*unshareable*) podatki.

Poleg tega razlikujemo še:

- statične podatke,
- dinamične podatke.

---

### Deljeni in nedeljeni podatki

#### Deljeni (shareable)

Gre za podatke, ki:

- se redko spreminjajo,
- jih lahko priklopimo samo za branje.

Primeri direktorijev:

```text
/usr
/opt
```

---

#### Nedeljeni (unshareable)

Gre za podatke, ki:

- so specifični za posamezen računalnik,
- se pogosto spreminjajo.

Primeri:

```text
/etc
/boot
```

---

### Statični in dinamični podatki

#### Statični podatki

Primeri:

```text
/bin
/usr/bin
```

Po namestitvi se običajno ne spreminjajo.

---

#### Dinamični podatki

Primeri:

```text
/var/mail
/var/run
```

Ti podatki se med delovanjem sistema pogosto spreminjajo.

---

### Pogosti imeniki

#### Korenski imenik

```text
/
```

Mora omogočati zagon in popravilo sistema.

---

#### `/usr`

Shranjuje večinoma podatke, namenjene samo branju.

---

#### `/usr/local`

Shranjuje lokalno nameščeno programsko opremo.

---

#### `/var`

Shranjuje:

- dnevniške datoteke (log),
- začasne podatke,
- vrste opravil (*spool*),
- podatke, ki se pogosto spreminjajo.

---

#### Kaj je spooling?

Spooling predstavlja način posredovanja podatkov med programom in počasnejšo napravo.

Najpogostejši primer je:

- tiskanje dokumentov.

Program odda opravilo, tiskalnik pa ga obdela kasneje.

---

### Izbira programske opreme

Pri nameščanju programske opreme moramo upoštevati:

- nadgradnjo operacijskega sistema,
- nadgradnjo programov,
- konfiguracijske datoteke,
- različice programov,
- zagonske programe (daemoni),
- odvisnosti med programi,
- ročno ali avtomatsko namestitev,
- lastniško programsko opremo.

---

#### Konfiguracijske datoteke

Sistem vsebuje veliko konfiguracijskih datotek, ki omogočajo lažje upravljanje in ponovno namestitev programske opreme.

---

#### Odvisnosti (Dependencies)

Odvisnosti pomenijo, da določena programska oprema za pravilno delovanje potrebuje druge knjižnice ali programe.

Če različice niso združljive, lahko pride do konfliktov.

---

### Instalacija binarnih paketov

#### Prednosti

- hitra namestitev,
- manjša poraba prostora,
- enostavna uporaba.

---

#### Slabosti

- odvisnosti,
- omejen nadzor,
- slabša optimizacija za posamezen sistem.

---

#### Opombe

Na operacijskem sistemu Windows se večina programske opreme namešča v binarni obliki.

Na Linuxu pa lahko programe tudi sami prevedemo iz izvorne kode.

---

### Instalacija iz izvorne kode

#### Prednosti

- velik nadzor nad namestitvijo,
- možnost optimizacije,
- možnost spreminjanja izvorne kode.

---

#### Slabosti

- časovno zahtevna,
- zahtevnejše upravljanje odvisnosti,
- večja kompleksnost,
- ni vsa programska oprema na voljo v izvorni obliki.

---

#### Opomba

Danes se namestitev iz izvorne kode uporablja precej redkeje, predvsem zaradi časovne zahtevnosti.

---

### Zakaj uporabljati upravljalca paketov?

Upravljalci paketov omogočajo:

- dostop do velikega števila programov,
- avtomatsko reševanje odvisnosti,
- evidenco nameščene programske opreme,
- enostavno posodabljanje sistema.

---

### Varnostni popravki

Pri upravljanju sistema moramo:

- preučiti varnostne zahteve sistema,
- redno nameščati varnostne popravke,
- spremljati odvisnosti knjižnic,
- preverjati veljavnost popravkov,
- po potrebi pripraviti lastne popravke.

Majhna varnostna ranljivost lahko hitro postane resen varnostni problem.

---

### Pregled sistemov za nameščanje paketov

Primeri različnih upravljalcev paketov:

| Operacijski sistem | Upravljalec paketov |
|---|---|
| Darwin / macOS | Fink |
| Debian | `dpkg`, `apt`, `apt-get` |
| FreeBSD/OpenBSD | Ports |
| Gentoo | Portage |
| IRIX | Tardist |
| NetBSD | pkgsrc |
| Slackware | `.tgz` |
| Solaris | `pkg` |
| GNU/Linux | različni upravljalci paketov |

---

### Linux - RPM

RPM pomeni:

```text
RPM Package Manager
```

Omogoča:

- poizvedovanje po paketih,
- preverjanje paketov,
- namestitev,
- posodobitev,
- odstranjevanje paketov.

---

### Linux - YUM

`yum` je upravljalec paketov za sisteme, ki uporabljajo RPM.

Omogoča avtomatsko:

- posodabljanje,
- nameščanje,
- odstranjevanje paketov.

> Opomba: `rpm` in `yum` danes veljata za starejša upravljalca paketov.

---

### Linux - APT

Na sistemih Debian in Ubuntu uporabljamo upravljalca paketov **APT**.

Posodobitev seznama paketov:

```bash
sudo apt update
```

Posodobitev sistema:

```bash
sudo apt upgrade
```

Namestitev programa:

```bash
sudo apt install thunderbird
```

Starejša različica ukaza:

```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install thunderbird
```

Danes se pogosteje uporablja ukaz:

```bash
apt
```

namesto starejšega:

```bash
apt-get
```

---

## Pravila, načela in etika

V tem poglavju obravnavamo:

- večuporabniške operacijske sisteme,
- interakcijo med uporabniki,
- zasebnost in varnost podatkov,
- licence programske opreme.

---

### Večuporabniški operacijski sistemi

Večuporabniški operacijski sistemi omogočajo, da na istem računalniku hkrati dela več uporabnikov.

Pri tem se pojavijo različni izzivi:

- zagotavljanje zasebnosti podatkov,
- sodelovanje in deljenje datotek,
- preprečevanje nepooblaščenega dostopa do datotek,
- preprečevanje vplivanja enega uporabnika na delo drugega,
- različni uporabniki potrebujejo različne stopnje privilegijev.

---

### Uporabniški računi v sistemih UNIX

Vsak uporabniški račun:

- ima enolično identifikacijsko številko (**UID**),
- pripada vsaj eni skupini (**GID**),
- je lahko zaščiten z geslom,
- ima določen ukazni interpreter (*shell*), ki omogoča ali onemogoča interaktivno prijavo.

Vsaka datoteka:

- vsebuje UID lastnika,
- vsebuje GID skupine,
- ima določena dovoljenja oziroma zaščito.

---

### Skupine v sistemih UNIX

Skupine predstavljajo zbirko uporabnikov, ki si delijo določene vire.

Lastnosti skupin:

- zapisane so v datoteki:

```text
/etc/group
```

- zapis ima obliko:

```text
ime_skupine:*:GID:uporabnik1,uporabnik2,...
```

- nekateri sistemi omejujejo največje število članov skupine,
- nov uporabnik ob ustvarjanju računa dobi privzeto skupino,
- nekateri sistemi uporabljajo tudi t. i. **shadow** datoteke.

---

### Primer zaščite direktorijev

Primer ukaza:

```bash
ls -al
```

Del izpisa:

```text
drwxr-xr-x  root root ...
drwx------  root root ...
drwxrwxrwt  root root ... /tmp
```

#### Opombe

- večina sistemskih direktorijev ima dovoljenja **755**,
- direktorij **/tmp** uporablja **sticky bit** (`t`).

Če imajo direktoriji dovoljenja **755**, imajo uporabniki praviloma pravico do dostopa (branja in prehajanja), ne pa tudi do pisanja.

---

### Pravila uporabe sistema

Dobro pripravljena pravila naj vsebujejo:

- pravila za sistemske administratorje,
- pravice in dolžnosti uporabnikov,
- pravila za uporabnike z dodatnimi privilegiji,
- pravila za začasne oziroma gostujoče uporabnike,
- načrt ukrepanja ob katastrofalnih izpadih,
- druge pomembne smernice.

---

### Pravila za sistemske administratorje

Dokument za administratorje naj vsebuje:

#### Pravila za zagotavljanje storitev

- čas rednega vzdrževanja,
- termine izdelave varnostnih kopij,
- sistem za prijavo napak,
- kontaktne podatke za nujne primere,
- pravice in dolžnosti uporabnikov,
- pravila za privilegirane uporabnike,
- pravila za gostujoče uporabnike,
- načrt obnove sistema po večjih okvarah.

#### Opombe

Pomembno je:

- kdo je administrator sistema,
- kakšna pooblastila ima,
- kako pogosto se izvajajo varnostne kopije.

---

### Splošna pravila za uporabnike

Pravila za uporabnike običajno vsebujejo:

- pogoje uporabe sistema,
- razpoložljive storitve,
- časovne omejitve,
- pravice in dolžnosti uporabnikov,
- sistem prijave napak,
- kontaktne informacije,
- pravila za uporabnike s posebnimi privilegiji,
- pravila za gostujoče uporabnike,
- postopke ob večjih okvarah sistema.

---

### Uveljavljanje pravil

Za uspešno izvajanje pravil mora biti zagotovljeno:

- da so vsi uporabniki seznanjeni s pravili,
- da se pomembni dogodki beležijo v dnevnikih (*log*),
- da so dnevniki zaščiteni pred spreminjanjem,
- da izvajanje pravil čim manj obremenjuje uporabnike.

#### Opomba

Pomembna je tudi fizična zaščita strežnikov.

Primeri:

- podstrešje ni primerno zaradi visokih temperatur,
- klet ni primerna zaradi nevarnosti poplav.

---

### Ustvarjanje uporabniškega računa

Pri ustvarjanju uporabnika določimo:

- uporabniško ime,
- UID,
- primarno skupino,
- dodatne skupine,
- ukazni interpreter (*shell*),
- geslo,
- domači direktorij,
- začetne nastavitve okolja,
- staranje gesla,
- omejitve uporabe virov,
- omejitve porabe diska,
- filtre za elektronsko pošto,
- pravice dostopa do tiskalnikov,
- druge sistemske nastavitve.

Na koncu vedno preverimo pravilno delovanje novega računa.

---

### Onemogočanje oziroma brisanje uporabniškega računa

Postopek običajno vključuje:

- zaklep ali spremembo gesla,
- spremembo ostalih sistemskih gesel,
- zaustavitev uporabnikovih procesov,
- odstranitev iz sekundarnih skupin,
- preusmeritev ali odstranitev elektronske pošte,
- odstranitev opravil (`cron`),
- izdelavo varnostne kopije uporabniških datotek.

---

### Ukaz `useradd`

Primer:

```bash
sudo useradd albin
```

Ukaz ustvari novega uporabnika.

Administrator lahko uporabniku določi:

- skupine,
- dovoljenja,
- domači direktorij,
- ukazni interpreter,
- druge nastavitve.

---

### Ukaz `userdel`

Primer:

```bash
sudo userdel albin
```

Ukaz izbriše uporabniški račun.

Pri tem moramo preveriti:

- ali želimo obdržati uporabnikov domači direktorij,
- ali uporabnik pripada dodatnim skupinam,
- ali obstajajo datoteke, ki jih še potrebujemo.

---

### Licence programske opreme

Pred uporabo programske opreme je priporočljivo prebrati licenčne pogoje.

Pri licencah razlikujemo:

- sistemsko programsko opremo,
- uporabniško programsko opremo,
- storitve,
- odprtokodno programsko opremo (*Open Source*),
- zaprtokodno programsko opremo (*Closed Source*).

Pomembno je tudi razlikovati:

- uporabo za osebne potrebe,
- uporabo v podjetjih,
- distribucijo programske opreme zunaj organizacije.

#### Primer

Nekatera programska oprema je za osebno uporabo brezplačna, za komercialno uporabo pa je potrebna licenca.

Primer:

- MySQL je brezplačen za številne osebne oziroma odprtokodne projekte,
- v določenih komercialnih primerih pa je potrebna plačljiva licenca.

---

### Etika sistemskega administratorja

Pomembna načela so:

- profesionalnost,
- doslednost,
- spoštovanje zasebnosti,
- zakonitost,
- skrb za stabilnost sistema,
- stalno izobraževanje,
- družbena odgovornost,
- moralna odgovornost.

---

### Primeri etičnih dilem

Primeri situacij:

- sporne vsebine na spletnih straneh,
- poseganje v elektronsko pošto uporabnikov,
- deljenje dostopov nepooblaščenim osebam,
- sodelovanje z organi pregona,
- izvajanje ukazov, ki so v nasprotju z moralnimi načeli.

---

### Dodatno gradivo

#### Upravljanje uporabnikov

Pomembne strani priročnika:

```text
passwd(5)
passwd.conf(5)
login.conf(5)
vipw(8)
group(5)
useradd(8)
usermod(8)
user(8)
userdel(8)
```

---

### Upravljanje uporabnikov – dodatne opombe

#### `passwd.conf`

Konfiguracijska datoteka za nastavitve uporabniških gesel.

---

#### `vipw`

Ukaz:

```bash
vipw
```

omogoča varno urejanje datoteke z uporabniškimi podatki.

Posebnost:

- med urejanjem se datoteka zaklene,
- hkrati jo lahko ureja samo en administrator,
- s tem se prepreči poškodba datoteke.

---

### Dodatno gradivo o licencah

Koristne povezave:

- https://opensource.org/licenses
- https://en.wikipedia.org/wiki/Software_license
- https://www.netbsd.org/Goals/redistribution.html

---

## Avtomatizacija opravil

### Zakaj avtomatizirati opravila?

Avtomatizacija je pomembna zaradi:

- večje zanesljivosti,
- prihranka časa,
- manjše možnosti človeških napak,
- zagotavljanja rednega izvajanja opravil.

Pri avtomatizaciji si pomagamo z:

- ukazno lupino (Shell),
- regularnimi izrazi,
- skriptnimi jeziki,
- programskimi jeziki (Python, C, ...).

---

### Prednosti avtomatizacije

Glavne prednosti avtomatizacije so:

- večja zanesljivost,
- zagotovljena izvedba opravil,
- izboljšana učinkovitost sistema.

Avtomatizacijo lahko pripravljamo:

- zase,
- za druge sistemske administratorje,
- za uporabnike sistema.

---

### Lastnosti dobrega sistemskega administratorja

Profesor je izpostavil sedem pomembnih lastnosti sistemskega administratorja:

- fleksibilnost,
- iznajdljivost,
- pozornost na podrobnosti,
- vzdrževanje rutine,
- vztrajnost,
- potrpežljivost,
- »lenoba« (v pozitivnem pomenu – avtomatizacija ponavljajočih se opravil).

> **Opomba:** Posebej pomembni sta **potrpežljivost** in **pozornost na podrobnosti**, predvsem pri nevarnih ukazih (npr. brisanje datotek), kjer lahko ena napačna izbira povzroči izgubo podatkov.

---

### Programi za razvrščanje opravil (cron)

Najpogostejši program za avtomatsko izvajanje opravil je **cron**.

Primer:

```bash
30 5 * * 6 find /tmp -type f -mtime +7 -atime +7 -exec rm -f '{}' ';'
```

Cron omogoča periodično izvajanje ukazov.

---

#### Struktura cron izraza

Cron uporablja pet polj:

```text
* * * * *
│ │ │ │ │
│ │ │ │ └── dan v tednu (0–6)
│ │ │ └──── mesec (1–12)
│ │ └────── dan v mesecu (1–31)
│ └──────── ura (0–23)
└────────── minuta (0–59)
```

---

#### Primeri cron izrazov

Vsak petek ob 05:02:

```text
2 5 * * 5
```

Od ponedeljka do petka ob 05:02:

```text
2 5 * * 1-5
```

Vsakih 20 minut:

Možne oblike:

```text
*/20 * * * *
```

ali

```text
0,20,40 * * * *
```

Možne so tudi posebne oznake:

```text
@daily
@weekly
@monthly
```

---

#### Absolutna pot pri cron-u

Pri cron opravilih je potrebno uporabljati **absolutne poti**.

Pravilno:

```bash
/home/peter/myscript.bash
```

Relativne poti običajno ne delujejo pravilno, saj cron ne pozna trenutnega direktorija uporabnika.

---

### Ukaz find

Ukaz `find` omogoča rekurzivno iskanje datotek in direktorijev.

Primer:

```bash
find /
```

Ukaz pregleda celotno drevesno strukturo od korenskega direktorija naprej.

---

#### Iskanje navadnih datotek

```bash
find / -type f
```

Možni tipi:

| Tip | Pomen |
|------|--------|
| `-type f` | navadne datoteke |
| `-type d` | direktoriji |

---

#### Časovni parametri

Pri iskanju pogosto uporabljamo:

- `-mtime`
- `-atime`
- `-ctime`

##### `-mtime`

čas zadnje spremembe vsebine datoteke

Primer:

```bash
-mtime +7
```

Datoteka ni bila spremenjena več kot 7 dni.

---

##### `-atime`

čas zadnjega dostopa

Primer:

```bash
-atime +7
```

Datoteka ni bila uporabljena več kot sedem dni.

---

##### `-ctime`

čas zadnje spremembe metapodatkov.

---

#### Parameter `-exec`

Primer:

```bash
find ... -exec rm {} \;
```

Pomen posameznih delov:

- `{}` predstavlja trenutno najdeno datoteko,
- `\;` označuje konec ukaza `-exec`.

---

#### Primeri uporabe ukaza find

##### Iskanje vseh `.cpp` datotek

```bash
time find / -name "*.cpp" > mojCpp2 2> /dev/null
```

Pomen:

- `/` → iskanje od korena sistema,
- `-name "*.cpp"` → poišče datoteke `.cpp`,
- `>` → izhod shrani v datoteko,
- `2> /dev/null` → napake preusmeri v `/dev/null`.

---

##### Iskanje datotek z dovoljenji 0777

```bash
find / -type f -perm 0777
```

Poišče vse datoteke, ki imajo vsa dovoljenja omogočena.

---

##### Sprememba dovoljenj vseh najdenih datotek

```bash
find / -type f -perm 0777 -print -exec chmod 644 {} \;
```

Ukaz:

1. izpiše najdene datoteke,
2. nato spremeni njihove pravice na **644**.

---

##### Iskanje več končnic

Primer:

```bash
find . -type f \( -name "*.php" -o -name "*.html" \)
```

Logični operator **ali** je:

```text
-o
```

---

### Ukaz locate

Ukaz:

```bash
locate -i ime
```

Možnost:

- `-i` ignorira velike in male črke.

---

### Primerjava datotek

Za primerjavo uporabljamo ukaz:

```bash
diff a.cpp b.cpp
```

Primerja vsebino obeh datotek.

---

### Osnove lupine (Shell)

Lupina je interaktivni program, ki:

- izvaja ukaze,
- zaganja programe,
- upravlja procese,
- upravlja vhod in izhod.

---

#### Vgrajeni ukazi

Primeri:

- `jobs`
- `fg`
- `bg`

To so vgrajeni ukazi lupine.

Nasprotno pa ukaz:

```bash
ls
```

ni del lupine, ampak samostojen program.

---

#### Primer

```bash
ls -l $(which ls)
```

ali

```bash
ls -l `which ls`
```

Oba ukaza izpišeta informacije o programu `ls`.

Primer rezultata:

```text
-rwxr-xr-x 1 root root ... /usr/bin/ls
```

---

### Ukaz sed

Ukaz `sed` se uporablja za:

- zamenjavo besedila,
- urejanje datotek,
- avtomatske spremembe vsebine.

---

### Ukaz nohup

Ukaz:

```bash
nohup
```

omogoča, da se program izvaja tudi po odjavi uporabnika iz sistema.

Program ignorira signal za prekinitev ob zaprtju terminala.

---

### Osnovna orodja

Najpogosteje uporabljena orodja pri sistemski administraciji:

- `pipe (|)`
- `ls`
- `find`
- `grep`
- `awk`
- `sed`
- regularni izrazi

---

#### Koristna dokumentacija

##### GNU sed

- Dokumentacija: https://www.gnu.org/software/sed/manual/sed.html

##### GNU awk

- Dokumentacija: https://www.gnu.org/software/gawk/manual/gawk.pdf

##### Primeri uporabe awk

- http://www.grymoire.com/Unix/Awk.html

##### Pomoč (man pages)

```bash
man sed
man awk
man grep
```

---

### Regularni izrazi (Regular Expressions)

Regularni izrazi (Regular Expressions – Regex) predstavljajo temelj številnih ukazov v Linuxu.

Omogočajo:

- iskanje po vzorcih,
- filtriranje podatkov,
- preverjanje pravilnosti zapisov,
- zamenjavo besedila,
- avtomatizacijo obdelave podatkov.

Brez regularnih izrazov bi bila orodja, kot so `grep`, `sed` in `awk`, precej bolj omejena.

Poleg uporabe v ukazni vrstici se regularni izrazi pogosto uporabljajo tudi pri razvoju **leksikalnih analizatorjev** (npr. pri predmetu *Prevajanje programskih jezikov*).

> **Opomba:** Negiranih izrazov (`^`) se, če je mogoče, izogibamo.

---

#### Primer uporabe

```bash
grep vhod | grep "^$" | count
```

Ukaz:

1. prebere datoteko `vhod`,
2. poišče prazne vrstice,
3. jih prešteje.

---

### Osnovni vzorci regularnih izrazov

#### Posamezen znak

```text
a
```

---

#### Seznam znakov

```text
[abc]
```

---

#### Interval znakov

```text
[A-Z]
```

---

#### Negiran izraz

```text
[^0-4]
```

Pomen:

vsi znaki razen števil od 0 do 4.

---

#### Posebni znaki

Poljuben znak:

```text
.
```

Začetek vrstice:

```text
^
```

Konec vrstice:

```text
$
```

Možno je kombinirati več različnih vzorcev.

---

### Kvantifikatorji

Največ enkrat

```text
?
```

---

Nič ali večkrat

```text
*
```

---

Enkrat ali večkrat

```text
+
```

---

Natanko n-krat

```text
{n}
```

---

Najmanj n-krat

```text
{n,}
```

---

Med n in m ponovitvami

```text
{n,m}
```

---

Združevanje izrazov

Primer:

```text
(1[a-z]2|a[0-9]z)
```

Pomen izraza:

Možni sta dve različni obliki zapisa:

#### Prva možnost

```text
1[a-z]2
```

- začne se s številko **1**,
- sledi mala črka od **a** do **z**,
- zaključi se s številko **2**.

Primer:

```text
1b2
```

---

#### Druga možnost

```text
a[0-9]z
```

- začne se s črko **a**,
- sledi ena številka med **0** in **9**,
- konča se s črko **z**.

Primer:

```text
a5z
```

---

### Skripte

Pri pisanju skript uporabljamo:

- zagonske datoteke,
- spremenljivke okolja,
- krmiljenje vhodov in izhodov,
- pogoje,
- zanke,
- funkcije,
- vgrajene ukaze.

---

### Zagonske datoteke in okolje

Ob prijavi uporabnika lahko administrator naloži zagonske datoteke, ki nastavijo uporabniško okolje.

Pri tem se:

- preberejo zagonske datoteke,
- nastavijo okoljske spremenljivke,
- pripravi uporabniško okolje.

---

#### Interaktivna lupina in interpreter ukazov

##### Interpreter ukazov

Interpreter ukazov omogoča izvajanje ukazov in skript.

Primer:

```bash
bash mojaSkripta.sh
```

Interpreter prebere bash skripto in jo izvede.

---

##### Interaktivna lupina

Interaktivna lupina (Shell) omogoča precej več kot zgolj izvajanje skript.

Poleg izvajanja ukazov omogoča tudi:

- samodejno dopolnjevanje ukazov s tipko **Tab**,
- zgodovino ukazov (puščici gor/dol),
- uporabo vgrajenih ukazov,
- uporabo knjižnic in funkcij lupine.

Zaradi tega je delo precej hitrejše kot pri navadnem interpreterju ukazov.

---

### Dedovanje okolja

Okolje se med procesi deduje.

---

#### Primer brez oklepajev

Predpostavimo, da smo v direktoriju:

```text
/work
```

Izvedemo:

```bash
pwd
cd /tmp
ls
pwd
```

Rezultat:

1. `pwd` izpiše

```text
/work
```

2. premaknemo se v `/tmp`

3. `ls` izpiše vsebino direktorija

4. zadnji `pwd` izpiše

```text
/tmp
```

Ker je ukaz `cd` spremenil trenutni direktorij.

---

#### Primer z oklepaji

```bash
pwd
(cd /tmp; ls)
pwd
```

Potek:

1. prvi `pwd`

```text
/work
```

2. ukaza v oklepajih se izvedeta v **podlupini (subshell)**

```bash
cd /tmp
ls
```

3. po zaključku podlupine drugi `pwd` ponovno izpiše

```text
/work
```

Ukazi v oklepajih namreč ne spreminjajo trenutnega okolja glavne lupine.

---

### Primer napake

```bash
cat < mdots | grep "abc" > mdots
```

Napaka:

Datoteka `mdots` je hkrati vhodna in izhodna datoteka.

To lahko povzroči izgubo podatkov.

---

### Primer uporabe več pipe-ov

```bash
cat a.txt | grep "A" | tail -n 3 | head -n 1
```

Potek izvajanja:

1. prebere datoteko `a.txt`,
2. poišče vrstice z znakom **A**,
3. vzame zadnje tri vrstice,
4. izmed teh izpiše prvo.

---

### Krmiljenje tokov

Osnovni deskriptorji:

- `stdin`
- `stdout`
- `stderr`

Operatorji:

```text
>
>>
<
<<
|
```

Dodatna uporabna ukaza:

- `tee`
- `xargs`

---

#### Ukaz tee

Ukaz `tee`:

- prebere standardni vhod,
- rezultat izpiše na zaslon,
- istočasno ga shrani še v eno ali več datotek.

Na ta način lahko rezultat hkrati:

- spremljamo na zaslonu,
- shranimo v datoteko.

Več informacij:

https://www.geeksforgeeks.org/tee-command-linux-example/

---

#### Ukaz xargs

Ukaz `xargs` omogoča gradnjo ukazov iz standardnega vhoda.

Pretvori vhodne podatke v argumente ukaza.

Uporablja se predvsem pri povezovanju ukazov preko pipe.

> **Opomba:** Pri zelo velikem številu argumentov lahko ukaz odpove.

Več informacij:

- https://man7.org/linux/man-pages/man1/xargs.1.html
- https://en.wikipedia.org/wiki/Xargs

---

### Krmiljenje izvajanja

#### Pogoji

- `if`
- `then`
- `else`
- `case`

---

#### Zanke

- `for`
- `while`
- `until`

---

#### Krmiljenje zank

- `break`
- `continue`

---

### Vgrajeni ukazi, funkcije in signali

Vgrajeni ukazi:

- izvajajo se brez ustvarjanja novega procesa,
- zato so hitrejši.

Funkcije:

- uporablja jih trenutna lupina,
- lahko spreminjajo trenutno okolje.

Lupina lahko:

- upravlja procese,
- nadzira opravila (jobs),
- prestreza določene signale,
- nekatere signale pa lahko tudi ignorira.

---

### Perl

#### Prednosti

- hiter razvoj,
- odlična podpora regularnim izrazom,
- enostavno delo z datotekami,
- dobra podpora vhodu in izhodu,
- varnostni mehanizmi.

---

#### Slabosti

- pogosto slabše berljiva koda,
- enostavno napisati program,
- precej težje napisati kakovosten program,
- ni vedno nameščen.

> **Opomba:** Profesor je izpostavil, da ima Perl veliko varnostnih pomanjkljivosti in pogosto zelo zgoščeno, težje berljivo kodo. Zato se danes pogosteje uporablja Python.

---

### Python

Prednosti:

- podobne kot pri Perlu,
- objektno usmerjen,
- dobro strukturiran,
- omogoča pisanje preglednejše kode,
- zelo razširjen in vedno bolj priljubljen.

---

### Ko pomaga samo C

Programski jezik **C** uporabljamo predvsem takrat, ko potrebujemo:

- največjo hitrost izvajanja,
- visoko učinkovitost,
- neposreden dostop do sistemskih funkcij Unix,
- veliko stopnjo prilagodljivosti.

Za sistemskega administratorja oziroma sistemskega programerja je poznavanje jezika **C** zelo koristno.


