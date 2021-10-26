# Sieci Mobilne i Sieci Internetu Rzeczy

B - Blok

C - Część

> 5G to będzie rewolucja w telekomie, bo każda fabryka będzie chciała swoją sieć 5G, która jest superszybka (minimalne opóźnienia), żeby powstawały inteligentne fabryki.

# B0 Sieci komórkowe - wstęp

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

# B1 Sieci GSM (2G)

NSS - Network SubSystem. Później (jak się pojawiły sieci pakietowe) zaczęto to nazywać Core Network. 

<img src="img/21.png" style="zoom:55%;" />

Z GSM pod postacią GRPS pojawiły się pierwsze w sieciach mobilnych usługi pakietowe.

**GRPS** - General Packet Radio Service

Potem powstał EDGE, taki poprawiony GPRS (lepsze przepustowości). 

Później pojawił się standard UMTS, tam HSPA to już w ogóle wywindowało przepustowość.

## Pierwotna idea GSM

Mieliśmy wtedy dobrze rozwiniętą sieć telefoniczną PSTN/ISDN. Były tam usługi pakietowe po kablu telefonicznym. No i wymyślono sobie:

> A jakby tak dołączyć do takiej sieci publicznej abonentów mobilnych, bezprzewodowych?

Chodziło tylko o to, żeby do sieci, któa już jest dokleić tylko dostęp radiowy. Okazało się ile z tym jazdy, że aż ten "dostęp" rozwinął się w osobną sieć. Także w praktyce okazało się, że trzeba zrobić odrębne sieci komórkowe. I dopiero coś co nazywa się Gateway MSC ma styki z siecią publiczną i ostatecznie się wykrystalizowali operatorzy mobilny.



Sieć ISDN była bardzo dobrze rozwnięta, zestandaryzowana i chciało się z tego skorzystać, żeby się nie narobić a dołączyć do niej. Budować tylko to co jest niezbędne.



Dlatego wzięto ISDN jako klasa bazowa i chciano ją zmodyfikować i stworzyć sieć radiową, żeby dało się tym dołączyć do prawdziwej ISDN.

<img src="img/22.png" style="zoom:75%;" />

Czyli widać, że trzeba się zająć dostępem do sieci (bo jest bezprzewodowy i abonenci się poruszają) oraz sterowaniem zgłoszeniami, a cała reszta mogła zostać i być bardzo podobna jak to było w ISDN.

> I to widać w architekturze jak sieć mobilna wykorzstuje system syngalizacji nr 7, tak głęboko jak się tylko da. itd. Natomiast to co trzeba było dobudować, co wynikało z mobilności, to dorobiono.

## Generyczne aspekty sieci mobilnych

Nie tylko GSM.

<img src="img/23.png" style="zoom:55%;" />

#### Zasoby radiowe

To jest coś co trzeba dzielić. To jest cenne dobro, więc nie może być tak, że ktoś je weźmie na stałe. Ubiegamy się o licencje, operatorzy mają je podzielone itd. No i jak ktoś już ma jakieś pasmo, to nie jest tak, że na stałe da abonentowi 100kb/s np.

Jak ktoś ma potrzebe to dostaje ten zasób, a jak nie ma potrzeby to mu się odbiera zasób i zwalnia go dla kogoś innego.  

==> Więc cały czas trzeba patrzeć kto co ma i zabierać oddawać itp.  Bo chcemy mieć jakoś usług (a to miała być sieć publiczna, więc niezawodność musiała być 99%), wszystko musi być pod ścisłą kontrolą. (nie to co w Wi-fi).

#### Mobilność

Po to mamy ten dostęp radiowy, żeby można było łazić czy jeździć. Przy wi-fi też jest jakaś mobilność, ale ograniczona (to tak jak przywiąże kogoś do drzewa i powiem, no jesteś mobilny w jakimś tam zakresie (zasięg sznurka)). Tu chodzi oto, żeby tego sznurka nie było. 
Mobilności są dwie:

- twarda - w trakcie połączenia
- nomadyczna - teraz jestem tu, potem pojadę do domu, a cały czas chcę być dostępny dla sieci. Sieć musi mniej-więcej wiedzieć, gdzie jestem, żeby do mnie zadzwonić

#### Usługi końcowe

W sieci telefonicznej był sam głos, a sieci mobilnego wprowadziły wiadomości SMS (Kiedyś to było używane do informowania od operatora, potem dopiero komercjalizacja poszła a dzisiaj to głównie alerty RCB.)	

### Poziomy/bloki sterowania

<img src="img/24.png" style="zoom:75%;" />

Z powyższych trzech aspektów wynikają 3 generyczne bloki sterowania:

- Zarządzanie zasobami radiowymi
  - blok funkcjonalny, który jest odpowiedzialny za zorganizowanie sposobu udzielania dostępu klientom do zasobu radiowego i pamiętajmy, to musi być w dwóch aspektach rozpatywane - płaszczyzny danych i płaszczyzny sterowania. Żebym ja mógł przesyłać dane, to muszę najpierw sieci to powiedzieć, i to powiedzenie odbywa się na tych samych zasobach radiowych. I na zasoby na data i control pane idzie jakaś rywalizacja i sieć musi to jakoś rozwiązać.
- Zarządzanie mobilnością
  - w aspekcie nomadycznym (od czasu do czasu terminal jak się gdzieś przemieści, to się rejestruje gdzie jest, żeby sieć wiedziała)
  - aspekt twardy (jak mam połączenie zarezerwowane, to może one zostać poddane tzw "handover'owi")
- Sterowanie zgłoszeniami
  - to bardziej realizacja usług użytkownika (czyli user robi coś z siecią core za pomocą sieci radiowej np. transfer pakietów (np. VoIP))
    - W 2G, 3G transfer pakietów to było coś kompletnie innego niż transfer głosu. Od 4G to jest to samo bo VoIP over LTE. LTE jest siecią pakietową a usługa głosowa to jest realizowana na tych pakietach właśnie. Sieć LTE nie widzi głosu tylko pakiety o parametrach do przesłania.

## Podstawowe koncepcje

### Komórka

Organizacja zasób w sieciach mobilnych odbywa się na zasadzie komórek. Obszarów relatywnie małych, które są pokryte poprzez stacje bazowe. De facto stacje bazowe to anteny. Przedstawiamy komórki jako hexagonalne obszarki, ale one nigdy nie są hexagonalne, nie ma takiej możliwości. One są kompletnie nieregularne to zależy od ukształtowania terenu, i wielu rzeczy jakie tylko sobie możemy wyobrazić. One zachodzą na siebie (jak nie zachodzą to mamy dziury (tak jak w tych moich bierszczadach)). 

>  Jak jest antena sektorowa, to ona jest w narożniku i jej "dzieci" wysyłaja do niej, a może być antena dookólna i jest na środku komórki

Teminal cały czasz mierzy co się dzieje dookoła (jaki zasięg skąd), jak wykryje ze jest w zasięgu lepszej stacji (zasięg lepszy) to się zamelduje w niej. Ale nawet nie - póki terminal jest w obszarze liczącym kilka komórek, to on tylko pilnuje czy jest w tym obszarze, czy on przypadkiem nie przeszedł obszaru, że on nie widzi żadnej z tych stacji bazowych, wtedy przerejestruje się mówicą sieci "jestem już nie w tej piaskownicy tylko innej". Żeby sieć mniej więcej widziała, gdzie on jest.
Natomiast jak on gada teraz, to cały czas śle komunikaty pomiary z tego co widzi naookoło. Terminal jak zaczyna połączenie to dostaje od sieci listę stacji bazowych, które ma monitorować pod kątem jakości sygnału i raporty wysyłać do sterownika. A sieć wie co się dzieje w kontekście innych stacji obok i sama decyduje czy nie przełączyć w końcu jakiegoś terminala na inną stację bazową. Np. jestem bliżej i mam lepszy zasięg (dB) z jakiejś stacji, ale nie ma tam zasobów to sieć mnie przerzuca (**handover**) do innej stacji bez wiedzy terminala.

Czyli sieć robi handovery i to się nazywa **centralny arbitraż zasobów**. Bo np. w sieciach pakietowych, terminal może sam zainicjować handover. W pakietówce opóźnienia 0.5 sekudny są spoko, ale w głosówce już nie. A nasz sieć ma mieć niezawodność 99.9%

<img src="img/25.png" style="zoom:75%;" />

### Mobilność nomadyczna

<img src="img/26.png" style="zoom:75%;" />

Załóżmy, że klienci sobie biegają, komórki są niezbyt duże i teraz mamy ich przepinać między komórkami, bo chcemy ich tak precyzyjnie mieć. (Cały czas nawet jak ktoś nie gada, to żeby go non-stop mieć). No i wtedy tak. Ktoś się porusza i zawsze jak zasięg jest lepszy w jakimś miejscu to przełączamy komórkę. Za każdym razem np. Ileż to tej sygnalizacji by było walone na darmo.

> To tak jakby mam pilnowała dziecka w piaskownicy każąć mu mówić co chwila przy którym kamyku on jest.
>
> To bez sensu. Chodzi o to, czy on jest w tej piaskownicy czy już w innej, wtedy groźnie. 

Obszary przywołań to są nasze piaskownice i póki dziecko chodzi w niej po kamykach to jest git. Ale jak przejdzie do innego, to chcemy od niego to usłuszeć. I to jest właśnie **nomadyzm** obszary przywołań wysyłają  info (parametry, nazwy, co umie itd.), żeby terminal wiedział gdzie jest, dostaje od obszaru liste stacji bazowych i pamięta. I nagle terminal nie widzi (słaby zasięg) żadnej stacji z listy, wtedy mówi "o kurcze przeszedłem stację bazową" muszę się przerejestrować. Odbiera od sieci nowy obszar i mówi do niej "teraz jestem tutaj, jak coś do mnie to tu szukajcie".  

> Jak dużo komórek to obszar, jak szybko się przełącza, jak często terminal dostaje info to wszystki sobie wylicza operator i on to wie na podstawie pomiarów, statystyk itp.  
>
> Operator robi kompromis, żeby sygnalizacji nie było za dużo, ale żeby też było ez znaleźć klienta, gdy przychodzi do niego połączenie.

Jak ktoś dzwoni do klienta, to sieć wie, w którym jest obszarze i wtedy okólnik z każdej stacji bazowej (broadcast) jest tam wysyłany  "ej, gościu ktoś do Ciebie, zgłoś się". I terminal wtedy odpowiada na tej, na której ma najlepszą moc. I terminal mówi do niej "dajcie mi kanał sygnalizacyjny, bo zdaje się to o mnie chodzi".

W mobilności twardej mamy zestawiony kanał i jego trzeba błyskawicznie przełączać przy poruszaniu się, żeby ani bit nie uciekł. I to jest realizowane wedługo paradygmatu *make before break*, póki terminal się nie przełączy do nowego zarezerwowanego dla niego zasobu w innej stacji bazowej, to cały czas korzysta z tej starej.

## Usługi końcowe

Usługi końcowe to były

- rozmówne
- wywiedzione z rozmównych
  - np. fax

Usługą z poziomu użytkownika była **Transparentność usługi względem mobilności**
A jej realizacją **zmiany wymuszone mobilnością** ( w tym *roamingiem*)

<img src="img/28.png" style="zoom:75%;" />

SSP jak user zaczynał być mobilny sygnalizowały to SCP, które były warstwą sterowania i jak kazały mu się przełączyć, to SSP wysyłał do STP a tamten do odpowiednigo SSP wiadomość, że zaraz tu się dołączymy. No i następny SSP sygnalizował znowy do STP, że następny węzeł to kolejny SSP i tak aż do SSP, z którem połączony jest user, do którego dzwonimy. Czyli widzimy już tu rozdzielenie płaszczyzny sterowania od danych.

## Standaryzacja GSM

GSM standaryzwało szereg ciał. Na początku GSM - ETSI, potem 3GPP się z tego wykrystalizowało od czasu R99 i do dzisiaj sprawuje piecze nad tym. Ważny dla GSM system sygnalizacji SS7 standaryzuje głównie ITU-T. Dodatkowo dla GSM z transportem IP następujące instytucje biorą udział:

- IETF - stos SIGTRAN
- ITU-T - protokół sterowanie zgłoszeniami BICC
- IETF/ITU-T - Megaco/H.248 (protokół sterowania bramami medialnymi)

## Punkt wyjścia dla GSM - PSTN, ISDN i SS7

<img src="img/29.png" style="zoom:75%;" />

To są dwa rysunki dla sieci PSTN/ISDN/SS7

<img src="img/30.png" style="zoom:75%;" />



Mamy sieć stałą (między CA/MSC a drugim CA/MSC) i mamy dostępy radio do niej (obszar pomarańczowy)). W sieci komórkowej mamy zmian obszarów pomarańczowych. 

Więc w GSM:

![](img/31.png)

Więc w GSM zmieniono tylko dół (czerwona pętla), bo zmieniło się medium transmisyjne (drut na radiowe fale). W sieci stałej to się wtykamy kablem i jest, a tu trzeba zrobić radiowy dostęp do drutu.

# B1C1 GSM - Architektura  

![](img/20.png)

Mamy część radiową **BSS** - **Base Station Subsystem** (teraz to się RAN nazywa w LTE i GeRAN w UMTS) i sieć stała(kablowa), która się nazywa **NSS - Network SubSystem** (w GSM i GPRS, a w wyższych standardach CORE Network, a w 5G "5G Core").  

Część radiowa to zrobienie medium transmisyjnego, a cześć stała to pilnowanie tego medium i doniesieniem usług z perwspektywy klienta na styk sieci komórkowej, po to zeby ruch mógł wyjść "w świat". No bo sieć komórkowa robi dostęp do siecie publicznej, czy to Internet czy rozmówna publiczna. 

NSS robi autentykacje, uwierzytelnienie.

! Terminal u Użytkownik to są dwie różne rzeczy. Czym innym jest terminal, a czym innym SIM i człowiek. Mogę przełożyć SIM do innego terminala i still będzie działać. 

Dodatkowo sieć stała zapewnia dostępność usług w wymiarze ogólnoświatowym. Jak jadę do Francji, to chciałbym mieć roaming (tego nie zrobi lokalna sieć radiowa, to trzeba poziom wyżej, czyli sieć stała to robi)

> Jak się do mnie dzwoni z Chin a jestem we Francji, no to połączenie idzie do mojej sieci macierzystej, czyli do Polski, no bo skąd sieć Chińska ma wiedzieć, że we Francji jestem.  Dopiero mój operator w Polsce ma bazę danych z informacją, gdzie ja jestem i wtedy zależnie od technologii jakoś tam do tego połączenia ze mną dochodzi.

# B1C2 GSM -  Podsystem Sieciowy NSS

## Elementy i Styki

![](img/32.png)

W PSTN były centrale, no to my też sobie wymyślimy jakieś.... ->:

**MSC - Mobile Switching Center** - centrum komutacyjne dla usług mobilnych, które jest taką upgradowaną centralą ISDN połaczeń głosowych. Upgrade polega np. na realizacji handoverów.

**HLR - Home Location Register** - rejestr macierzysty, rejestr gdzie na stałe są trzymane wszystkie dane o abonencie (nie personalne tylko te sieciowe - id karty, dane o sim'ie, klucze do szyfrowania, bieżąca lokalizacja z dokładnościa do obszaru MSC, gdzie on jest. Cokolwiek ja chce jako klient, to najpierw zawsze jest weryfikacja w HLR, czy user ma dostęp do usługi.

**VLR - Visitor Location Register** - rejestr lokalny, hierarchicznie niżej niż HLR. 

> np. Orange w jeden centralny HLR w Wawie. A ja jestem we Wrocku, tam już inne MSC funkcjonuje i z tamtym MSC jest skojarzone lokalne VLR i w tym VLR jest lokalne info o mnie gdzie jestem z dokładnościa do obszaru przywołań, której HLR już nie widzi. Ale HRL wie, do którego VLR uderzać, gdyby trzeba było mnie znaleźć.
>
> Jak ktoś z centrali G-MSC chce do mnie, to zagląda do HLR i kieruje się już do MSC skojarzonym z wpisanym tam VLR

**AuC - Authentication Center** - tu są klucze uwierzytelniające klientów.

**EIR - Equipment Identity Register** - rejestr terminali. Nie wszystkich, ale tych które są jakoś specjalne, np. kradziony jest na zastrzeżonej liście albo z jakimś innym statusem i na tej podstawie pewne rzeczy można z nim zrobić a pewnych nie. Nie z Sim'em tylko z terminalem. Generalnie to żeby kradzione wrzucać na black list.Sieć sprawdza czy jest kradziony i jak jest to żadnej usługi nie wykona.

**G-MSC - Gateway MSC** - taki MSC na brzegu z sieciami innymi niż ta operatorska (albo publiczna albo operatorska innego operatora (roaming))

> I taki schemat zachował się w kolejnych standardach. Jak rozumiemy to, to łatwiej nam ogarnąć te nowe G. Zmiany są głównie niskopoziomowe w radiu, bo inaczej się zasobami zarządza (inne częstotliwości, modulacje itp.) oraz sama pakietówka dużo zmian zrobiła.

## Wstawka o sygnalizacji

### Sieć ISDN

ISDN - Integrated Services Digital Network

PSTN - Public Switched Telephony Network

W niej działały protokoły:

- DSS1 -Digital Subscriber System No. 1 - system sygnalizacji w sieciach ISDN
- SS7 - Signallig System no. 7 - używany w sieciach PSTN

#### Architektura sieci ISDN

<img src="img/33.png" style="zoom:120%;" />

**TE** - Terminal Equipment, **CA** - centrala abonencka, **CT** - centrala tranzytowa, **STP** - Signalling Transfer Point (punkt transferowy sygnalizacji) SS7.

**SP** - Signalling Point (punkt końcowy sygnalizacji) SS7.

> W ogólności jest tak, że jest jakaś sieć i trzeba nią zarządzać, żeby abonencki w ramach potrzeby dostawali z niej zasoby. Inaczej się zarządza siecią pakietową, a inaczej w sieci z komutacją łączy (ISDN lub ATM). Zawsze istnieje blok funkcjonalny "Sterowanie zgłoszeniami" - Call Controll.

^Na rysunku to co odpowiada danym usera, to jest zielone (są to kanały rozmówne), są dwa bo kanały zestawiamy "w te i nazat".

**I jak do tego dochodzi, że są te zielone kreski?** Na początek ich nie ma, należą one do puli wspólnej a trzeba je zarezerwować dla jakiejś pary userów, którzy chcą gadać.

1. Po wklepaniu numery i naciśnięciu słuchawki TE wysyła wiadomość *SETUP* zdefiniowaną przez protokół **DSS1** (**Digital Subscriber System no. 1**), która oznacza "chcę się połączyć z jakimś abonentem (o podanym numerze)" (btw. DSS1 jest wykorzystywany w GSM i 2.5G i również w 3G w ramach toru rozmównego).
2. CA dostaje SETUP robi autoryzacje itp (CAC) i przedłuża (patrzy jak to trzeba skomutować najpierw) wysyłająć do CT wiadomość *IAM (Initial Adress Message)* z protokołu **ISUP (ISDN User Part Protocol)** i na jej podstawie (tam jest nr docelowy) jest komutacja i IAM jest przkazywany do następnych CT na podstawie jakiegoś tam routingu w tych CT.
3. Aż na koniec IAM trafi do CA (zauważmy, że w ciemno po drodze zarezerwowano zasoby, bo zakładamy, że user2 odbierze, bo co jak user2 odbierze, a okaże się, że nie ma zasobów w sieci? musimy mieć pewność, że są, więc od razu, w ciemno rezerwujemy).
4. CA wysyła do TE usera2 *SETUP* i wtedy telefon usera2 zaczyna dzwonić, a żeby poinformować sieć, że user2 został znaleziony i jest u niego odgrywany dzwonek TE wysyła wiadomość *ALERTING*
5. CA dostaje wiadomość *ALERTING* i przekazuje fakt znalezeinie i dzwonienia telefonu u usera2 dalej wysyłając do CT wiadomość *ACM (Address Complete Message)*, którą CT przekazują wcześniej ustalonym szlakiem aż do CA przy user1
6. CA przy user1 wysyła do TE user1 wiadomość *ALERTING* i wtedy w telefonie user1 odgrywany jest ton*, który informuje, że połączono się z user2 i czekamy aż odbierze.
   *tak naprawdę to CA, gdy obierze ALERTING sama po gotowym już torze rozmównym wysyła ton, że jest dzwonione u user2. (btw. to u user1 kierunek *up-link* jest zablokowany (co symbolizuje że nie jest pokolorowane na czarno prawa część kółeczka na rysunku w CA usera1))
7. Gdy user2 podniesie słuchawkę to jego TE wysyła wiadomość *CONN (Connect)* do CA i wtedy CA zestawia tor rozmówny między nim a TE usera2. Potem wysyła do CT wiadomość *ANM (Answer Message)*, która powoduje, że tor wcześniej zestawiony jest "udrażniany" (up i down-link działają wszędzie). I na koniec CA wysyła do TE usera2 wiadomość *CONACK (Connection Acknowledgement)*
8. Jak CA otrzyma *ANM*, to wysyła *CONN* do TE usera1 co informuje, że drugi user odebrał i, że zestawiono już połączenie. 
9. TE usera1 po odebraniu *CONN* wysyła tylko potwierdzenie odebrania w postaci *CONNACK*

#### Łącze między TE a CA od strony fizycznej

W ISDN TE z CA było połączone:

- dwoma **kanałami B**, który były kanałem rozmównym
  - Miały one przepływność `64kbit/s`
- jednym **kanałem D**, służącym do sygnalizacji (czyli przez niego przepływały wiadomości protokołu DSS1)
  - Miał on przepływność `16kbit/s`

I to wszytko bylo w jednym drucie telefonicznym. W warstwie elektrycznej podział na kanały reazlizował strumień bitów ramkonwanych i wnim były ramki, które nam wydzielały 2 kanały B i ramki od kanału D.

Z racji, że mamy dwa kanały B, to można naraz prowadzić 2 rozmowy, ale ktoś powie jak to dwie rozmowy na jednym telefonie?

Tak naprawdę to za tym TE były dopiero telefony i one były podłączone do TE i mogło być ich wiele i dwa naraz mogły gadać. Jakby trzeci chciał to by został odrzucony (ale cała procedura odbyła by się z CT, bo kanał D byłby wolny).

**Więc generalnie** wymiana sygnalizacyjna strukturalnie jest odrębna od przestrzeni przeznaczonej na rozmowę. Czyli w bitach były zdefiniowane ramki o długości ileś bitów, gdzie pewne sekwencje (pozycje) bitów mogły być zajmowane tylko przez informacje sygnalizacyjne, a inne sekwencje przez informacje rozmówną.

#### Po co STP?

Z pośród CT wydzielało się takie duże centrale i przy nich organizowało takie Punkty Transferu Sygnalizacji (takie jakby routery wiadomości sygnalizacyjnych), po to żeby ta sieć sygnalizacyjna, była nieco bardziej zagregowana (ofc nie screntralizowana), bo łatwiej tym zarządzać.

No i ostatecznie sygnalizacja sieciowa (^na rys. czerwona) docierała między centralami pośrednio przez STP (czyli jak CA/CT chciało coś wysłać do innego CA/CT to to szło przez STP).

Sieć systemu sygnalizacji była reazlizowana w SS7 przez **MTP - Message Transfer Part** (usługa relatywnie podobna do IP). MTP to taka pseudo sieć pakietowa na potrzeby sygnalizacji.

#### Protokoły sygnalizacyjne ISDN

Ten rysunek zakłada, że od sygnalizacji i danych jest jedno łączę.

<img src="img/34.png" style="zoom:75%;" />

Jak czytać ten rysunek?

Wiadomość ISUP wymieniame między CA i CT nie lecą przecież sobie po powietrzu tylko zasuwają sobie właśnie przez wartwę:

- sieciową (protokoł MTPlayer3) 
  - komutacja się tu odbywa
- łącza danych (MTPlayer2)
  - zabezpieczenie przed błędami itp
- fizyczną (MTP1)
  - przesłanie bajtów

Wiadomości DSS1 między TE i CA są przesyłane przez:

- **LAPD (Link Access Protocol D-channel)** czyli protokół wartwy drugiej
  - od razu druga warstwa bo przecież nie potrzebujemy tu żadnej komutacji (TE i CA są na stałe połączone kablem)
- w warstwie fizycznej mamy wcześniej wspomniany kanał D (ten 16 kbit/s)

#### Pojęcia z tego rozdziału.

![](img/35.png)

#### Podsumowanie

Wymiana sygnalizacji i danych użytkownika wymagają zasobów, które w ogólności* są "wspólne" i trzeba nimi zarządzać w czasie rzeczywistym.

*oprócz przypadku, że między TE i CA mamy BRA, gdzie jest dedykowany kanał D tylko na signalling.

***

Tak wygląda to w ISDN i teraz chodzi o to, żeby jak najwięcej z tych pomysłów wykorzystać w sieci GSM. Sieć mobilna trudni się tym jak zorganizować łącze między TE i CA.

***

### Sygnalizacja a sterowanie

**Sterowanie** to są czynności, które robią urządzenia z Control Plane, a **sygnalizacja** to komunikacja, wymienianie informacji między urządzeniami z Control Plane.

![](img/36.png)

"Data Plane" jest nazywany też "User Plane".

