# OSHI - Open Source Hybrid IP/SDN
## Juraj Volko, Marek Vlha
## Cvičenie: Streda - 15.00
------------------------------------------
#	Analýza
##	Úvod
Softvérovo definované siete (SDN z angl. Software Defined Networking) je predstavované ako nový koncept, ktorý môže zmeniť fungovanie IP sietí ako ich poznáme dnes .SDN je založené na separovaní sieťovej kontroly a dátových úrovní. Externý SDN kontrolór môže dynamicky pridávať pravidlá do SDN spôsobilých uzlov. Aby bolo možné použiť SDN v IP backbones je nutné zabezpečiť spolupracovanie IP forwardingu a SDN forvardingu. IP routere môžu byť nahradené SDN prepínačmi ktoré ponúkajú rozšírenejšie možnosti ako aj optimalizáciu už existujúcich služieb. Jedná sa teda o zavedenie setov hybridných IP/SDN uzlov, ktoré sú schopné fungovať ako IP routre ale aj SDN uzly, pod kontrolou SDN kontrolerov.

##	OSHI
V juestvujúcich IP/MPLS scenároch existujú tzv. tunely MPLS nazývané LSP. V SDN sieťach môže byť vytvorených viac typov tunelov alebo viac všeobecných sieťových ciest využívajúcich viac rôznych protokolov (TCP/UDP,IP,Ethernet). Uvažujme fungovanie regulárnej IP prevádzky spolu SBP (SDN based paths) na linkách medzi hybridnými IP/SDN uzlami. V koncepte OSHI to teda znamená koexistenciu IP a SDN prevádzky v samostatnom uzle.
![oshi](https://github.com/aks-2017/semestralne-zadania-semestralne-zadanie-xvolko-xvlha/blob/master/docs/image/OSHI.png "Oshi")

#	Návrh
*	Vytvorenie topológie (obr. 1)Hybridnej IP/SDN siete pomocou Topology3D. Žlté – koncový užívateľ (7), zelené – switch (4), červené – “Access OSHI” (3), modré – Core OSHI (5)
![topo](https://github.com/aks-2017/semestralne-zadania-semestralne-zadanie-xvolko-xvlha/blob/master/docs/image/TOPO.png "Topologia")

Obr. 1 - Topológia

*	Nahranie topológie do rozšíreného mininetu na VM
*	Testovanie TCP throughput (Mb/s) použitím OSHI VLL a použitím OSHI IP (Obr. 1) pomocou Dreamer-Measurement-Tools
*	Porovnanie výsledkov s výsledkami z článku [1] v tabubulke(Tab. 1)
![vysledky](https://github.com/aks-2017/semestralne-zadania-semestralne-zadanie-xvolko-xvlha/blob/master/docs/image/TAB.png "Vysledky")

Tab. 1 – výsledky porovnania z článku

##	Použité nástroje
### Oracle VM VirtuaBox
### OSHI-VM – Dreamer-Mininet-Extensions, Dreamer-Topology3D
### Mininet (inštalácia doplnkov do mininetu bude realizovaná skriptami) 
* Ipaddress, netaddr = potrebné pre inštaláciu OSHI
* netaddr
* OSHI dependencies:
Open vSwitch 2.390,
Ryu,
Networkx,
Dreamer-Topology-Parser-and-Validator
