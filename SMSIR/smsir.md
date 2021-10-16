# SMSIR

B - Blok

C - Część

## Wykład 1

5G to będzie rewolucja w telekomie, bo każda fabryka będzie chciała swoją sieć 5G, która jest superszybka (minimalne opóźnienia), żeby powstawały inteligentne fabryki.

5G to kolejna instacja generacji sieci komórkowych.
Cały czas do technologi sieci mobilnych dorabiane są jakieś ficzery, usługi i po prostu jak jest ich dużo w krótkim czasie i ich znaczenie jest przełomowe, to robimy kolejną instancję (kolejne G). 5G, to nie jest coś totalnie nowego, to już ma wieloletnią tradycję.

Sieci mobilne zawsze mają dwie sekcje:

- Radiowa sieć dostępowa
  - ona ma tylko przesłać stumień bajtów z jednego końca na drugi
- Sieć szkieletowa
  - to ona zajmuje się usługami (to jest ta co mnie interesuje)

No i mamy jeszcze terminale (urządzenia końcowe - coś co ma SIM np.)

RAN - Radio Access Network

IMS - IP Multimedia Subsystem



Niebieski to dane (głos, smski)

Zółty to sterowanie



W 5G sygnalizacje(sterowanie) totalnie oddzielono. Żółte to serwery w chmurze w tych czasach. Wirtualizaja ułatwia zarządzanie. Trudno zwirtualizować ruter, bo tam idą tysiące danych, ale samo sterowanie EZ.

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
