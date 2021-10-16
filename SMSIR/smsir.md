# SMSIR

B - Blok

C - Część

> 5G to będzie rewolucja w telekomie, bo każda fabryka będzie chciała swoją sieć 5G, która jest superszybka (minimalne opóźnienia), żeby powstawały inteligentne fabryki.

## B0 Sieci komórkowe - wstęp

### Ewolucja od 2G do 5G - Timeline

![](img/1.png)



Każde R, to kolejny Release. Aktualnie trwają pracę nad R17, ale to na papierze

#### 2G - GSM

W Polsce trochę później niż 1990. Ofc wcześniej były inne technologie np. w USA, ale o tym się już nie mówi.

W GSM można było usługi pakietowe, ale to było mega wolne wiele niedogonodności.

Poźniej weszło GPRS i EDGE, gdzie pakietowa usługa została podniesiona do rangi architektonicznego komponentu. Bo w GSM, robiło się transmiję pakietową w kanale rozmównym, więc to nie mogło być szybkie (kilkanaście kb/s). Natomiast w 2.5G (GPRS i EDGE), gdzie podniesiono usługę pakietową do rangi architektury i wytworzyło strukturę sieci rdzeniowej, która de facto jak przyjżeć się klockom pomijając szczegółowe nazwy i inne protokoły jakie są używane, to tak naprawdę przetrwała ona do 4G na pewno, a może i jak się trochę poumawiamy to 5G.

#### 3G - UMTS

Inny sposób kodowania.

Zwiększono przepływność usług pakietowych o rząd wielkości co do 2.5G. Później dorabiano kolejne ficzery, powiększano pasmo. 

Potem zrobiono HSPA, czyli zwiększenie przepływności, ale architektoniczne na tej samej sieci.

#### 4G - LTE

Koniec 2008 pierwsza wersja LTE, czyli to czego używamy dzisiaj. OFDM. - zmiana modulacji, bo w tej wcześniejszej nie dało się nic zrobić (pod Shannona podeszli  i trzeba było inaczej to wymyśleć).

Potem kolejne ficzery agregacja nośnych - czyli LTE4Dvanced. 

Gdzieś R12,R13 pojawiły się standardy *narrow band IoT* i *LTE-M* do obsługi sieci Internetu rzeczy. Niewiele tego wzdrożono (zwłaszcza w Polsce).

> Orange oferuje narrow band IoT, a Plus LTE-M. Ale świadczą takie usługi tylko firmom i to dużym.

#### 5G

5G kolejna instancja. To nie jest tak, że powstało to z niczego i zupełnie przerwało tradycję, historię tego wszystkiego. Po prostu to są kolejne ficzery, które swoją skalą i znaczeniem spowodowały, że nazwano to zupełnie inaczej - 5G (bo pewną masę krytyczną tych ficzerów przekroczono). 

Zmniejszono opóźnienia w radiówce do rzędu 1ms (zmiana procedur obsługi ruchu).

Małe stacje bazowe, wysokie pasma częstotliwościowe.

#### Technologie i ich obszary

<img src="img/2.png" style="zoom:50%;" />

**IMS** - **IP Multimedia Subsystem** - baza dla obecnej rzeczy jaką jest VoiceOverIP, czyli usługi głosowe na LTE. 
Operator większość z nas usługi głosowe nie wrzuca już na UMTS tylko na VoIP.



### Architektury

W ogólności sieć mobilna zawsze ma dwie sekcje

- Radiowa sieć dostępowa
  - **RAN** - Radio Access Network
  - jest po to, żeby przez łącze radiowe przenieść odpowiednie sygnały (niezawodnie itd. itd.)
  - nie zajmuje się usługami *per se*
  - taka niska wartstwa (tylko przesyła a usgługami to się endpointy zajmują -  z jednej strony terminale, z drugiej sieć szkieletowa)
- Sieć szkieletowa
  - **Core** - Core Netowork
  - ona zajmuje się realizacją usług pod kątek użytkownika
- No i są jeszcze terminale (urządzeni końcowe, te w rękach klienta)

Taki podział obowiązuje przez wszystkie generacje zmieniają się tylko bloczki w środku.

#### 2G - GSM

<img src="img/4.png" style="zoom:75%;" />

MS - Mobile Station (czyli terminal)

BTS - Base Transceiver Station



#### 3G - UMTS

  <img src="img/5.png" style="zoom:75%;" />

**Release 99**

Zmiany w RAN:

- UE - User Equipment (czyli terminal)

- Nowy interfejs radiowy opary o WCDMA

- BSC (Base Station Controller) przechodzi w RNC (Radio Network Controller)

Zmiany W CORE:

- MSC -> 3G MSC
- SGSN -> 3g SGSN
- GMSC i GGSN bez zmian
- AuC zmodernizowany (większe bezpieczeństwo)

**Release 4**

O ile bloki są podobne w RAN, to już sygnalizacja w nich jest inna, bo w UMTS inne kodowanie weszło.

Pierwsze releas'y UMTS pracowały z ISDN, potem trzeba bylo przejść na ATM i IP, więc kolejne releas'y dodawały swoje 5gr w tym temacie. Siecią transportową przestawała być stara SDN, tylko pakietówki. I właśnie jak świat zaczął przechodzić na pakietówki, to pomyślano, że sieć komórkową też na pakietówkę hyc, ale jak to zrobić? Pakiet to zupełnie co innego niż stały kanał o stałej przepływności PCM-kowy i okazało się, że dół węzłów trzeba zmodyfikować i okazało się, że nawet architektonicznie można to inaczej zrobić, a nawet warto.

<img src="img/6.png" style="zoom:45%;" />

**Release 5**

<img src="img/7.png" style="zoom:45%;" />

Pojawisło się **3G HSPA** (**H**igh Speed **P**acket **A**ccess). Nowa technologia do zwiększania przepływności bitowej (znacznie!!), którą sprzężono z sieciami Wi-Fi. Ale na tej samej strukturze co 3G, więc bez żadnej tam rewolucji.

<img src="img/8.png" style="zoom:45%;" />

Ile ta technologia dała przepływności?

|            | Downlink  |    Uplink    |
| :--------: | :-------: | :----------: |
| Release 5  | 14.4 Mb/s |  5.76 Mb/s   |
| Release 7  |  28 Mb/s  |  11.5 Mb/s   |
| Release 8  |  42 Mb/s  | 23 Mb/s (R9) |
| Release 10 | 168 Mb/s  |      -       |
| Release 11 | 336 Mb/s  |   70 Mb/s    |

#### 4G -  LTE

UTMS Release 8 to jest LTE/EPC

![](img/9.png)

<img src="img/10.png" style="zoom:45%;" />

### Różne tematy



#### Ewolucja UMTS ku SDN/NFV

![](img/11.png)

**Data Plane** - moja mowa, dane użutkownika (Dane pakietowe)

**Control Plane** - protokoły do wysterowania (przygotowanie węzłów po drodze, do przekazania danych) Data Plane (Sygnalizacja/Sterowanie)

Widać jak na początku szło to przez jedne urządzenia, a potem zaczęły one się specjalizować np. w LTE wydzelono MME (Mobilty Management Element) osobny serwer, przez który dane głosowe nie przechodzą wgl., a on czuwa nad obsługą mobilności userów (hand-overy realizuje).

A w 5G zupełnie oddzielono Data i Control Plane. Niebieskie to rutery, a zółte to serwery. W dzisiejszych czasach w 5G, te serwery zaczynają być zwirtualizowane, to jest realizowane w chmurze. Sterowanie jest ez zwirtualizować, router już nie, bo tam lecą miliony danych.

#### Komutacja kanałów jako rezerwa, Dane - LTE, ugługi głosowe - w trybie CS

<img src="img/12.png" style="zoom:45%;" />

To nie jest tak, że jak operator wprowadzał nową technologie (nowe G), to kasował poprzednią. W Twoim telefonie działa 2G, 3G, 4G. 

I naprzykład sieć GSM backapuje inne, wyższe technologie w zakresie usług głosowych. A są obszary (małe ale są, bieszczady czy coś), gdzie działa tylko 2G np.

#### IMS- scentralizowany model usług

<img src="img/13.png" style="zoom:45%;" />



Warto zwrócić uwagę, na to że VoLTE jest na IMS.  IMS to skomplikowanty podsystem, który wspiera działanie usług głównie głosowych. 

Większość ludzi ma głos po VoLTE i za syngalizację odpowiada tam IMS (jakieś tam serwery, w chmurze, które służą do zestawiania naszych sesji głosowych).

#### 4G LTE - kluczowe techniki

<img src="img/19.png" style="zoom:75%;" />

#### Ewolucja LTE - szybkośc transmisji

LTE to czas gdzie zaczęto wprowadzać wielo-antenowe rozwiązania tzw. **MIMO** - Multiple Input Multiple Output.

LTE zaczęło się od 150Mb/s i ciągłego pasma 20MHZ. a w 2017 układy scalone w terminalach przystosowane są do 1Gb/s i wykorzystania pasma 80-100MHz w kierunku od sieci do usera.

| Rok      | 2012                | 2013                  | 2014                  | 2015             | 2016       | 2017                    |
| -------- | ------------------- | --------------------- | --------------------- | ---------------- | ---------- | ----------------------- |
| Szybkość | 150 Mb/s            | 150 Mb/s              | 300 Mb/s              | 450 Mb/s         | 600 Mb/s   | 1 Gb/s                  |
| Pasmo    | 20 MHz<br />2x2MIMO | 10+10MHz<br />2x2MIMO | 20+20MHz<br />2x2MIMO | 3CA<br />2x2MIMO | 3CA 256QAM | 3-5CA Mhz <br />4x4MIMO |

xCA - Carrier Aggregation x- number of aggregated carriers

MIMO - Multiple Input Multiple Output.

xQAM - Quadrature Amplitude Modulation x - number of combinations

### Ewolucja od 1G do 4G

![](img/14.png)

![](img/15.png)

*Nie ma możliwość, żeby wszyscy userzy w komórce mieli `Max. Szybkość DownLink`, bo pasma nie wystarczy.

![](img/16.png)

Dla nas opóźnienia rzędy 1ms w domu w 5G nic nie znaczą, ale w przemyśle, gdzie opóźnienia muszą być mega niska, to ma znaczenie, czy VR

 <img src="img/3.png" style="zoom:75%;" />

### Shannon

Rozwój sieci mobilnych jest niezmiennie związany z Shannonem.

![](img/17.png)

Cała zabawa rozwoju sieci mobilnej, to się odbywa wokół tego wzoru, bo:

- zeby zwiększać szybkość
  - Zacznamy z pasmem
  - jak pasma brakuje dajemy więcej anten
  - a potem SNR zmniejszamy (walczymy)

Rysunek na przykładzie LTE.

## B1 Sieci GSM

### B1C1 Architektura GSM i podsystem sieciowy

Idea GSM dokleić dostępo mobilny/radiowy do sieci PSTN/ISDN, która już jest. W praktyce okazało się że ten pierwotnie "dostęp" rozwinął się w odzielną sieć. Bo do momentu urządzeń, które mają dostęp do sieci szkieletowej, która już była, to zrobiło się tak dużo, że aż jest to oddzielna sieć. No i pojawili się operatorzy  od samej tej sieci.

Zawsze w każdej technologi jest zawsze aspekt:

- transfer danych użytkownika
- transfer danych sterowania, po to, żeby transfer danych użytkownika mógł zaistnieć

W sieci pakietowej jest łatwiej sterować, bo nie trzeba alokować łączy (jak EON), tu ułatwienie jest takie, że pakiet ma adres docelowy (i każde urządzenie go rozpatruje niezależnie).



#### Generyczne aspekty sieci mobilnych

W każdym "G" są te aspekty i koniec kropka.

Zasoby radiowe, to jest coś co trzeba sobie dzielić. Jak firma ma wykupione jakieś pasmo, to nie ma nigdy tak, ze klientowi da pare kHz na stałe. Jak ktoś ma potrzebę to korzysta z zasobu jak nie ma to mu się zabiera. Więc cały czas trzeba patrzeć kto co ma i kontrolować to, zabierać itp.

Sieci komórkowe wprowadziły nowe usługi np. SMS. Kiedyś to było używane do informowania od operatora, potem dopiero komercjalizacja poszła a dzisiaj to głównie alerty RCB.

Sterowanie zgłoszeniami- czyli słuchanie co user chce zrobić, czy rozmowa, czy smski czy coś

#### Podstawowe koncepcje (1)

komórka 

> wszystko zależy od ukształtowania terenu

Terminal na początku połączenie dostaje od sieci listę stacji bazowych, które ma monitorować w kontekście jakości sygnału i wysyła raporty do sieci. A sieć jak trzeba to przełącza usera na inną komórkę. Sieć patrzy na moc sygnału i obiążenie sieci.

#### Podstawowe koncepcje (2)

Póki user jest w komórce to my chcemy wiedzieć, że jest w niej po prostu, ale jak przejdzie do innej, to sieci musi wiedzieć. To jest nomadyzm. Jak terminal zmieni komórke, to musi o tym sieci powiedzieć. Stacje bazowe wysyłaja co kilkanaście milisekudn "bikony", co sieć umie, jakie ma paramsy, jej nazwa itp. I terminale widzą te stacje i pamiętają. Jak terminal widzi, że jest słabo z mocą sygnału, to ogarnia, że jest w innej komórce i się przerejestowuje i widzi nowe stacje bazowe.

Ale sieć też musi umieć znaleźć terminal jak jest zgłoszenie przychodzę (dzwoni ktoś do nas). To wtedy wszystkie stacje bazowe z komórki, gdzie temirnal jest zarejestrowany dają z anteny dookolnej sygnał, żeby terminal się zgłosił (tak jak mam krzyczy imię dziecka w piaskownicy, żeby się zgłosił). 

Mobilność twarde, żeby była ciągłość ani bajt nie uciekł.

#### Usługi końcowe (... fax)

Nie ma czasu :((

#### Widok ogólny - podystemy

NSS - sieć stała (Network SubSystem)

BSS część radiowa

BSS zajmuje sie zestawieniem drutu

NSS pilnuje tego druta i daje dostęp temu drutowi do sieci szkieletowej

Bo generalnie sieć mobilna to dostęp radiowy do sieci stałej

Terminal a użytkownik to dwie różne rzeczy (mogę przełożyć sima do innego urządzenia).

Sieć stała określa dostępność usług w wymiarze światowym (np. roaming). 

Jak jestem we Francji i  sieć chińska dzwoni do mnie to połęczenie idzie do mojej sieci macierzystej w Polsce i dopiero tam jest info, że ja jesetm we Francji.'

#### Podsystem NSS - elementy i styki

HLR - Home L.. Register  - wszystkie dane o userze, gdzie on jest itp. taka baza danych jedna na operatora

VLR - taki rejestr ale lokalny. taki HLR dla jednego MSC

G-MSC - Gateway MSC - MSC na styku z innymi sieciami np. PSTN
