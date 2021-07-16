# Scheda di Illuminazione Digitale per vetture [ACME](http://acmetreni.it/index.php/it/) [UicX Cuccette Comfort](https://scalaenne.wordpress.com/2013/06/08/carrozze-uic-x-parte-sesta-cuccette/) in Scala H0
Questa scheda e' pensata per illuminare in maniera digitale le vetture ACME UicX *Cuccette Comfort 1995R e 1998R*, in scala H0.</br>
E' stata progettata espressamente sugli ingombri stutturali della carrozza per massimizzare il realismo luminoso garantendo **tutte** le zone illuminate in maniera indipendente: 
- Corridoio 
- *Luci Diurne Cuccette* (9 Cuccette Oppure 8 più compartimento Cuccettista)
- **Luci Notturne Blu Cuccette** (9 Cuccette Oppure 8 più compartimento Cuccettista)
- Ritirate (sulle vetture 1995R)
- Predisposizione per le *Luci di Coda Rosse* 

**Codice Identificativo Progetto: TFX063**

**Ultima Revisione HardWare: 1.02**

**Ultima Revisione SoftWare: 011**

**Alcune Immagini Dimostrative:**

- Carrozza in condizioni luminose *Diurne* con tutti i LED bianchi accesi

<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/diurna_bianchi.jpg" width="1280">

- Carrozza in condizione luminose *Diurne* con *corridoio* illuminato e *Cuccette con luci blu*.

<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/diurna_blu.jpg" width="1280">

- Carrozza in condizioni luminose *Notturne* con tutti i LED bianchi accesi 

<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/notturna_bianchi.jpg" width="1280">

- Carrozza in condizione luminose *Notturne* con *corridoio* illuminato e *Cuccette con luci blu*.

<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/notturna_blu.jpg" width="1280"></br>

- Scheda nella sua posizione appoggiata sopra gli interni:

<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/scheda_posizionata.jpg" width="1280"></br>

------------

## Indice
* [Video Presentazione del Progetto](#video-presentazione-del-progetto)
* [Manuale Scheda](#manuale-scheda)
* [FirmWare](#firmware)
* [HardWare](#hardware)
* [Caratteristiche della Scheda](#caratteristiche-della-scheda)
  - [Ponte di Diodi Schottky](#ponte-di-diodi-schottky)
  - [Chip Step Down Buck MCP16331](#chip-step-down-buck-mcp16331)
  - [Condensatori PowerPack](#condensatori-powerpack)
  - [Protezione Sovratensioni (Opzionale)](#protezione-sovratensioni-opzionale)
  - [Microchip ATmega128A](#microchip-atmega128a)
  - [Lettura Segnale Digitale](#lettura-segnale-digitale)
  - [Sistema ACK](#sistema-ack)
  - [Porta di Programmazione ISP](#porta-di-programmazione-isp)
  - [Cuccette con Luci Diurne e Notturne *indipendenti*](#illuminazione-cuccette-con-luci-diurne-e-notturne)
  - [Ritirare](#illuminazione-ritirate)
  - [Luci di Coda Rosse](#luci-di-coda-rosse)
  - [Altoparlante](#altoparlante)
  - [Decoder PluX](#interfaccia-plux)
  - [Porta SUSI](#porta-susi)
* [Assemblaggio](#Assemblaggio)
* [Contattami](#Contattami)

------------


## Video Presentazione del Progetto
[![Video Presentazione](https://img.youtube.com/vi/yyA5b5wTD80/0.jpg)](http://www.youtube.com/watch?v=yyA5b5wTD80)

------------

## Manuale Scheda
Il manuale della scheda è [disponibile qui](https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/TFX063_MANUALE.odt).

------------

## FirmWare
Il Firmware dedicato e' presente sotto la cartella [FirmWare](https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/tree/main/FirmWare), per poterlo caricare è consigliata la seguente [Shield](https://github.com/TheFidax/ProgrammerUpdaterShield).</br>
Le cifre finali del file .HEX identificano la versione del FirmWare.

*NOTA*: Nella cartella e' presente anche un file chiamto *TFX063_TEST_AUX.hex* ; questo firmware attiva, a scheda alimentata, tutte le AUX.</br>
**Serve Esclusivamente in fase di assemblaggio** per verificare che tutte le saldature siano state effettuate correttamente. **NON E' IL FIRMWARE PER IL FUNZIONAMENTO NORMALE.**

**NOTA: Per conoscere la versione del Firmware presente a bordo e' sufficiente *Leggere la CV 7*.**

------------

## HardWare
Il progetto di questa scheda e' disponibile qui: https://workspace.circuitmaker.com/Projects/Details/luca-fidanza/ACME-UIC-X-Cuccette-Comfort-Class-H0 .</br>
**Viene rilasciato con la seguente Licenza**: https://creativecommons.org/licenses/by-nc-nd/4.0/ .</br>
I **File Gerber**, il **BOM** e il file **Pick and Place** sono nel file **.Zip** disponibile sotto la cartella [HardWare](https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/tree/main/HardWare).</br> 

**NOTA**: Lo spessore *consigliato* del PCB per questa scheda è di: **0,6mm**

------------

## Caratteristiche della Scheda
Di seguito sono riportate le caratteristiche della scheda, poi spiegate in dettaglio nei vari paragrafi dedicati.
- [Schottky Diodes](#ponte-di-diodi-schottky) to provide CC power from Tracks
- [MCP16331](#chip-step-down-buck-mcp16331) to power Board at 5v
- [PowerPack](#condensatori-powerpack) system by 4x 100uF Tantalum capacitors with slow charge system and [Overvoltage Isolation system](#protezione-sovratensioni-opzionale).
- Board can be operate with these systems: CC Analog (from 7v), PWM CC Analog, AC Analog, Digital (DCC & Motorola)
- [AtMega128A](#microchip-atmega128a) to Digital Operation
- [Optoisolator to read Digital signal](#lettura-segnale-digitale)
- [ACK System](#sistema-ack)
- [JST SH6 connector](#porta-di-programmazione-isp) to program AtMega with ISP system and to provide I2C Bus from external target
- [All Cuccettes illuminated](#illuminazione-cuccette-con-luci-diurne-e-notturne) independently (with Day and Night lights)
- [Bathrooms illuminated](#illuminazione-ritirate) independently (Only on 1995R Models)
- Pads for [tail red lights](#luci-di-coda-rosse)
- Rectangular [30mm Speaker](#altoparlante) for PluX Decoder
- [PluX Interface](#interfaccia-plux) (with Sound and SUSI BUS)
- [SUSI Port](#porta-susi) for External Module
- MINIMUM CLEARANCE: 6mil

------------

### Ponte di Diodi Schottky
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/ss310.jpg" width="1280">

Il circuito di alimentazione e' realizzato meadiante 4 diodi Schottky in configurazione [Ponte di Graetz](https://it.wikipedia.org/wiki/Raddrizzatore#Ponte_di_Graetz).</br>
Tale configurazione permette di *raddrizzare* la tensione captata dalle prese di corrente in Conrente Continua a prescindere del sistema di alimentazione:
- Corrente Continua Analogica (fornisce sempre gli stessi poli in uscita)
- Corrente PWM (raddrizza l'onda quadra fornendo una tensione simil continua)
- Corrente Alternata Analogica (raddrizza l'onda sinusoidale fornendo una tensione simil continua)
- Digitale (raddrizza l'onda quadra fornendo una tensione simil continua)

------------

### Chip Step Down Buck MCP16331
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/mcp16331.jpg" width="1280">

L'alimentazione a 5 volt e' fornita dal chip [Microchip MCP16331](https://www.microchip.com/wwwproducts/en/MCP16331), un regolatore di tensione di tipo [Step Down Buck](https://it.wikipedia.org/wiki/Convertitore_buck) in gradi di ricevere in ingresso tensioni fino a 50 volt e di fornire in uscita una tensione stabile a 5 volt con sviluppo di calore minimo.</br>

------------

### Condensatori PowerPack
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/powerpack.jpg" width="1280">

Per sopperire a problemi di captazione di corrente e' previsto un sistema *powerpack* formato da 4 condensatori al Tantalio da 100uF con tensione **massima** di 25 volt.</br>
I condensatori sono separati dal circuito di alimentazione da un Diodo ed un Resistore che rappresentano *il sistema di ricarica lenta*.
Come ulteriore protezione la scheda **può essere equipaggiata** con un sistema di [protezione dalle sovratensioni](#protezione-sovratensioni-opzionale).

------------

### Protezione Sovratensioni (Opzionale)
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/ltc4367.jpg" width="1280">

Questa protezione **e' opzionale**: la sua presenza **e' segnalata dal Jumper J1 *aperto***. (**N.B.** Nella revisione HardWare 1.00 il Jumper J1 **e' assente**, e' stato introdotto dalla versione 1.01)</br>
Le normative [NMRA](https://www.nmra.org/sites/default/files/standards/sandrp/pdf/s-9.1_electrical_standards_2020.pdf) e [NEM](https://morop.org/downloads/nem/fr/nem670_f.pdf) **impongono** che un decoder digitali *supportino* tensioni fino a 27 volt.</br>
L'utilizzo di condensatori a 25 volt *non e' a norma*. **Tuttavia** le stesse normative impongono che la centrale fornisca tensione *massima* di 22 volt.</br>
Pertanto in condizioni di *funzionamento corretto* i condensatori non riceveranno tensioni che possano danneggiarli.

Gli stessi produttori commerciali *consigliano* condensatori da 25 volt:
<img src="https://images.beneluxspoor.net/bnls/aansluitschema_lokpilot_v3.jpg" width="1280">

**In caso di impiego della Scheda su sistemi a Corrente Alternata Analogica questa protezione E' OBBLIGATORIA!** 

Il sistema di protezione si basa sul chip [LTC4367](https://www.analog.com/en/products/ltc4367.html) che **isola** mediante *MOSFET* i condensatori in caso di tensioni *superiori a 23,7 volt*; quando la tensione scende sotto questa soglia i condensatori torneranno alimentati.</br>

------------

### Microchip ATmega128A
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/atmega.jpg" width="1280">

Il *cervello* della scheda e' un microcontrollore [ATmega128A](https://www.microchip.com/wwwproducts/en/ATmega128A) a 64 pin operante a 5 volt con frequenza di 16MHz tramite cristallo esterno.</br>
Il microcontrollore comanda *in maniera indipendente* tutti (leggere NOTA) i LED, in modo tale da garantire la massima flessibilita' di funzionamento.

*NOTA*: Il corridoio e' progettato con *5 segmenti* da 3 led ognuno: il microcontrollore comanda il segmento e **non** il singolo LED.

Il chip e' programmabile **anche** utilizzando l'**Arduino IDE** (mediante *programmatore ISP*) tramite il [MegaCore](https://github.com/MCUdude/MegaCore).</br>

I valori dei **FUSE** sono i seguenti: 
- LOW: 0x3F
- High: 0xC7
- Extended: 0xFF
- LOCKBITS: 0x3F

Il microcontrollore **non può** essere dotato di *bootloader*: non e' presente una porta Seriale.

------------

### Lettura Segnale Digitale
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/dcc.jpg" width="1280">

Il segnale digitale e' letto mediante [Optoisolatore TLP2168](https://toshiba.semicon-storage.com/eu/semiconductor/product/optoelectronics/detail.TLP2168.html) che fornisce l'[isolamento galvanico](https://it.wikipedia.org/wiki/Isolamento_elettrico) del microcontrollore dalla tensione delle rotaie.</br> 
L'optoisolatore e' protetto dall'inversione di corrente mediante Diodo e da un eccessiva corrente mediante resistore.</br>
Tale chip e' bicanale e permette, inoltre, il rilevamento della presenza di un Decoder Esterno analizzando la linea U+ fornita da esso.</br>
Questo sistema **e' compatibile con il DCC e con il Motorola**.

------------

### Sistema ACK
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/ack.jpg" width="1280">

La scheda e' dotata di sistema per fornire l'ACK nella **programmazione DCC mediante binario di programmazione**.

------------

### Porta di Programmazione ISP
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/isp.jpg" width="1280">

Per programmare il microcontrollore e' presente *una porta di programmazione ISP* con connettore JST SH6 per prevenire connessioni invertite.</br>
Questa porta svolge la doppia funzione di **Porta ISP** e **Porta I2C** mediante il seguente schema:</br>

<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/isp_i2c.jpg" width="1280">

------------

### Illuminazione Cuccette con Luci Diurne e Notturne
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/luci_cuccette.jpg" width="1280">

Questa scheda fornisce, per ogni Cuccetta, la **doppia illuminazione**: *Diurna* con LED Bianco Freddo e *Notturna* con LED Blu.</br>
Ogni LED e' indipendente e puo' essere pilotato dal microcontrollore in maniera indipendente dall'altro.</br>

Le vetture Cuccette Comfort si dividono in due tipologie
 - Vettura con 9 Cuccette
 - Vettura con 8 Cuccette + Zona Cuccettista
La scheda **e' compatibile con entrambe le versioni.**

------------

### Illuminazione Ritirate
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/luci_ritirate.jpg" width="1280">

Le carrozze *tipo* **1995R** posseggono finestrini *opacizzati* in corrispondenza delle Ritirate.</br>
La scheda e' progettata con LED per illuminare anche questi spazi, anche essi sono indipendenti.

**NOTA**: Le vetture *Tipo 1998R* **NON HANNO** finestrini in corrispondenza delle Ritirate, e' consigliabile non accendere questi LED per evitare che si vedano in caso di plastica sottile. 

------------

### Luci di Coda Rosse
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/luci_coda_pad.jpg" width="1280">
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/luci_coda_npn.jpg" width="1280">

Su entrambi i lati sono presenti le connessioni per delle **Luci di Coda Rosse**.</br>
Le connessioni prevedere un *polo positivo* collegato alla linea a **5 volt** e un *polo negativo* pilotato dal micro tramite transistor.

------------

### Altoparlante
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/altoparlante.jpg" width="1280">

La scheda ha lo spazio, e connessioni, per un altoparlante da 30 millimetri.</br>
*Consigliato 8 Ohm e 2 Watt*.

------------

### Interfaccia PluX
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/plux.jpg" width="1280">

E' presente un **connettore PluX** per poter utilizzare decoder commerciali.</br>
Durante il funzionamento con Decoder, la scheda di illuminazione diventa un [Modulo SUSI](https://github.com/TheFidax/Rcn600), questa configurazione diventa necessario se e' richiesto un protocollo *proprietario* non decodifcicabile dalla scheda.</br>
Protocolli come:
- [MFX/M4](https://en.wikipedia.org/wiki/M%C3%A4rklin_Digital)
- [RailCom Plus](http://www.esu.eu/en/support/white-papers/railcomplusr/) 

Il connettore PluX fornisce il collegamento alle rotaie (per portare i comandi al Decoder), il [Bus SUSI](https://dccwiki.com/SUSI) (per utilizzare la scheda come modulo SUSI) e il collegamento per un altoparlante (in caso di decoder sonori: es. [ESU LokSound v5 FX](http://www.esu.eu/en/products/loksound/loksound-5-fx/)).

**ATTENZIONE! Non è previsto un "motore fittizio" pertanto in caso di decoder "per locomotive" la *Lettura/Scrittura* delle CVs e' permessa soltanto tramite *PoM!***

*N.B.* Data la presenza di una zona nascosta e' possibile inserire lì un decoder esterno non compatibile con l'altezza della carrozza, oppure con connettore diverso.</br>
Esempio: Decoder [Maerklin mLD3](https://www.maerklin.de/en/products/details/article/60972/) con **connettore 21MTC** collegato mediante extender.
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/decoder_extender.jpg" width="1280">

------------

### Porta SUSI
<img src="https://github.com/TheFidax/TFX063_ACME_UICX_CUCCETTE_COMFORT_H0/blob/main/Images/susi.jpg" width="1280">

Per garantire la massima personalizzazione, e' presente anche **una porta SUSI** per eventuali moduli SUSI esterni.

------------

## Assemblaggio
Il file *BoM* comprende la lista di tutti i pezzi necessario all'assemblaggio in proprio della scheda.</br>
Per esperienza personale consiglio di cominciare l'assemblaggio dal Chip **LTC4367** in quanto il più ostico da saldare a mano; nel caso in cui questo chip *non fosse richiesto* allora è consigliabile cominciare dal *Microcontrollore ATmega128A*.

I successivi pezzi possono essere saldati seguendo un ordine a scelta dell'utente.

*Nel caso in cui si volesse la scheda **gia' assemblata** e' possibile contattarmi all'indirizzo mail sottoriportato oppure seguire eventuali aste di pezzi in esubero sul mio profilo **Ebay***: https://www.ebay.it/sch/the_fidax/m.html

------------

## Contattami
Per curiosita' o ulteriori informazioni puo contattarmi al seguente indirizzo email:  	TheFidaxContactsAtgmail.com
