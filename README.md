# Report Tecnico: Sistema Gestionale Ospedaliero in Togo

## Introduzione

Questo report tecnico riassume le decisioni e le pianificazioni per l'implementazione di un sistema gestionale ospedaliero durante la missione in Togo. Viene descritto il software, hardware e le configurazioni di rete e sistemi operativi discusse, oltre ai criteri di scelta e strategie per aggiornamenti remoti e gestione server.

## Software Gestionale

La scelta del sistema gestionale verte su soluzioni open source integrate, con particolare attenzione a sistemi come OpenMRS e la sua estensione Bahmni, oltre a Open Hospital e OpenEMR come alternative. Il sistema deve supportare una gestione integrata e coordinata di ambulatori multipli, laboratorio, radiologia, sala operatoria, farmacia e triage.

### Funzionalità chiave

- Condivisione dati clinici e referti tra reparti
- Workflow coordinato per il percorso del paziente
- Refertazione digitale e archiviazione immagini
- Gestione sala operatoria con protocolli e tracciamento
- Controllo scorte e prescrizioni elettroniche in farmacia
- Reportistica clinica e amministrativa

### Alternative software

Oltre a OpenMRS, si considerano OpenEMR, Open Hospital e software specifici africani come AjirMed e progetti come mHealth4Afrika.

## Hardware e Infrastruttura

Il materiale hardware comprende numerosi PC Dell Optiplex, laptop Latitude, server Dell PowerEdge, storage IBM Storwize, stampanti Zebra e monitor Dell. I server PowerEdge sono utilizzati per il server principale e per server secondario dedicato a backup, repository di aggiornamenti e servizi di supporto.

### Materiale già disponibile (Fattura 191682676 del 21/10/2025)

- 42 PC Dell Optiplex 3020
- 4 PC Dell Optiplex 9010
- 11 PC Dell Optiplex 390
- 10 stampanti etichette Zebra ZT410
- 2 storage IBM Storwize V3700
- 2 server Dell PowerEdge R730
- 57 monitor Dell E176/E170
- 12 laptop Dell Latitude E5550
- 8 laptop Dell Latitude E5570
- 2 laptop Dell Latitude E5580
- 2 laptop Dell Latitude E5590
- 9 laptop Dell Latitude E5500
- 33 alimentatori di ricambio per laptop

## Configurazione Server

### Server principale

Installare il sistema gestionale su server principale con database, software gestionale e backup.

### Secondo server

Utilizzare il secondo server per backup in tempo reale, repository locale per aggiornamenti dei client, telemedicina e servizi di autenticazione.

## Rete e Alimentazione

La missione sarà alimentata da impianti fotovoltaici con connessione internet via 4G. Implementare una rete locale affidabile con firewall e Wi-Fi, bilanciamento e caching per l'ottimizzazione del traffico.

## Sistemi Operativi

Si consiglia Debian come sistema operativo principale per server e client, accompagnato dall'ambiente desktop Cinnamon su client per interfaccia simile a Windows. Per i server si suggerisce Linux in modalità server headless o con GUI leggera se necessario.

## Gestione Aggiornamenti

Il secondo server sarà utilizzato come mirror locale dei repository Debian per minimizzare il traffico e facilitare gli aggiornamenti da remoto dei circa 60 client. Utilizzo di apt-mirror o rsync per sincronizzare pacchetti, con configurazioni client per puntare al repository locale.

## Strategie di Deployment

Creazione di immagini di sistema per reinstallazioni rapide con strumenti come Clonezilla o FOG Project. Automazione di configurazioni e aggiornamenti tramite script e strumenti di configurazione come Ansible o Puppet.

## Domande Aperte

- Quali sono le priorità cliniche specifiche da configurare nei moduli software?
- Qual è il livello di competenza IT del personale locale che dovrà gestire il sistema?
- Qual è la capacità di banda e stabilità prevista della connessione 4G in Togo?
- Quali protocolli sanitari e legali locali devono essere integrati nel sistema?
- È previsto un supporto tecnico internazionale a lungo termine per manutenzione e aggiornamenti. Come gestirlo al meglio?
- Nel materiale già spedito o da spedire sono inclusi i frutti per le prese ethernet e i cavi necessari per la predisposizione delle prese telematiche?

## Materiale Mancante da Verificare/Acquistare

- Frutti RJ45 e placche per prese di rete da incasso
- Matasse di cavo ethernet (Cat6 o superiore) e connettori di terminazione
- Switch di rete centrali e switch di reparto/locali per la distribuzione
- Patch panel e patch cord per cablaggio armadi di rete
- Tastiere e mouse di ricambio per postazioni client
- Access point o ulteriori dispositivi di rete necessari per copertura Wi-Fi
- Stampanti A4 standard (laser o inkjet) per documentazione clinica e amministrativa
- UPS/ciabatte filtrate e armadi rack per organizzazione del cablaggio

## Proposta di Assegnazione Task

- **Enrico Do**: installazione e configurazione del gestionale
- **Franco Leverare**,**Michele Bensi**: installazione sistema operativo sui server e configurazione dei servers e dello storage (mirror aggiornamenti Debian)
- **Andrea Chesini**: inventario e approvvigionamento del materiale mancante, con spedizione in Togo
- **Irene Spoldi**: gestione stampanti (etichette Zebra e stampanti A4) e materiali di consumo associati
- **Luca Palini**: test end-to-end del sistema prima del deployment
- **Andrea Chesini**, **Alberto Stabile**, **Franco Leveraro**: progettazione infrastruttura di rete
- **Elisa Riceputi**, **Fabrizio Armani**: desiderate un task specifico? Segnalate disponibilità/interessi
- **Andrea Chesini**, **Alberto Stabile**, **Irene Spoldi**, **Luca Palini**, **Enrico Do**: installazione in loco
- **Tutti**: supporto da remoto a lungo termine...

## Prossimi Passi - Todo List

- [ ] Definire e documentare i moduli clinici prioritari da implementare
- [ ] Preparare un ambiente di test in Italia con Debian + Cinnamon e software gestionale
- [ ] Creare immagini sistema per i client e predisporre script di configurazione automatica
- [ ] Configurare e testare il server mirror per aggiornamenti locali
- [ ] Pianificare formazione IT e clinica per personale locale
- [ ] Verificare e configurare infrastruttura di rete e alimentazione FV
- [ ] Organizzare un piano di test di sistema completo prima del trasferimento in Togo
- [ ] Definire piani di assistenza remota e monitoraggio post-installazione
