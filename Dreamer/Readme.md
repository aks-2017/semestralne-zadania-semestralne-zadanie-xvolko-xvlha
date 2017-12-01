# OSHI - Open Source Hybrid IP/SDN
## Juraj Volko, Marek Vlha
## Cvičenie: Streda - 15.00
-------------------
#Inštalácia

1.1) netaddr (pip) - sudo pip install netaddr

1.2) ipaddress (pip) - sudo pip install ipaddress

sudo git clone https://github.com/aks-2017/semestralne-zadania-semestralne-zadanie-xvolko-xvlha/tree/master/Dreamer

sudo git clone https://github.com/openvswitch/ovs.git

1.3) Inštalácia RYU controllera - sudo pip install ryu

1.4) networkx pre MPLS-VS (pip) - sudo pip install networkx

2) V skripte Dreamer-Mininet-Extensions/mininet\_extensions.py prepísať cestu pre dva súbory:

| RYU\_PATH = &#39;/home/user/workspace/dreamer-ryu/ryu/app/&#39; |
| --- |
|   |

PROJECT\_PATH = &#39;/home/user/workspace/Dreamer-Mininet-Extensions/&#39;

Na

| RYU\_PATH = &#39;../workspace/dreamer-ryu/ryu/app/&#39; |
| --- |
|   |

PROJECT\_PATH = &#39;../workspace/Dreamer-Mininet-Extensions/&#39;

## Spúštanie Mininet Aplikácie pre OSHI topológie:

Spustenie OSHI IP/SDN Miniet príkladu s OSHI topológiou vo formáte json:

cd Dreamer-Mininet-Extensions

sudo ./mininet/topo\_dovi.json

Po úspešnom vytvorení topológie sa vytvorí súbor vll_pusher.cfg -> tento súbor je nutné presunúť to priečinku /Dreamer-VLL-Pusher-master/ryu a v tomto priečinku 

Zapnite Xming a následne v okne s vytvorenou topológiou zadajte príkaz "xterm ctr8 ctr8" - otvorí sa vám okno s kontrolérom, presuňte sa do priečinku app "cd /home/mininet/dreamer-ryu/ryu/app" a zadajte "ryu-manager rest_topology.py ofctl_rest.py --observe-links"

V druhom okne sa presuňte do priečinku "cd /home/mininet/Dreamer-VLL-Pusher/ryu" a zadajte "./vll_pusher.py --controller localhost:8080 --add"

Otvorte okno s mininetom a zadajte "pingall"
