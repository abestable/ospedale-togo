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

## Prossimi Passi - Todo List
- [ ] Definire e documentare i moduli clinici prioritari da implementare
- [ ] Preparare un ambiente di test in Italia con Debian + Cinnamon e software gestionale
- [ ] Creare immagini sistema per i client e predisporre script di configurazione automatica
- [ ] Configurare e testare il server mirror per aggiornamenti locali
- [ ] Pianificare formazione IT e clinica per personale locale
- [ ] Verificare e configurare infrastruttura di rete e alimentazione FV
- [ ] Organizzare un piano di test di sistema completo prima del trasferimento in Togo
- [ ] Definire piani di assistenza remota e monitoraggio post-installazione

