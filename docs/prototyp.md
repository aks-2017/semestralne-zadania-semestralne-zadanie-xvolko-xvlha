

# Funkčný prototyp pre OSHI IP/SDN

## Inštalácia

Pre nainštalovanie a spustenie Mininetu pre OSHI je potrebné stiahnuť a nainštalovať všetky potrebné požadované súbory.

Ako prvé je potrebné stiahnuť nasledujúce súbory v ktorých sa nachádzajú rozšírenia pre Mininet a skripty pre inštalovanie rozšírení:

sudo git clone [https://github.com/netgroup/Dreamer-Management-Scripts](https://github.com/netgroup/Dreamer-Management-Scripts)

sudo git clone [https://github.com/netgroup/Dreamer-Mininet-Extensions](https://github.com/netgroup/Dreamer-Mininet-Extensions)

Ako ďaľší krok treba nainštalovať OSHI požadované súbory:

1.1) netaddr (pip) - sudo pip install netaddr

1.2) ipaddress (pip) - sudo pip install ipaddress

1.3) OSHI dependecies pomocou skriptu:

        cd Dreamer-Management-Scripts/oshi/

        ./setup.sh

1.3.1) Treba stiahnúť OpenwSwitch

$ git clone https://github.com/openvswitch/ovs.git

1.3.2) Inštalácia RYU controllera - sudo pip install ryu

1.3.3) Dreame RYU patch stiahnutie:

$ git clone  https://github.com/netgroup/dreamer-ryu

1.3.4) networkx pre MPLS-VS (pip) - sudo pip install networkx

1.4) Open vSwitchd service:

        sudo update-rc.d -f openvswitch-controller remove

        sudo update-rc.d -f openvswitch-switch remove

1.5) Mininet (commit: aae0affae46a63ef5e54d86351c96417c3888112):

git clone git://github.com/mininet/mininet

        cd mininet/

        git reset --hard aae0affae46a63ef5e54d86351c96417c3888112

        cd ..

        mininet/util/install.sh -ent

1.6) Dreamer-Topology-Parser-and-Validator (git) -

git clone [https://github.com/netgroup/Dreamer-Topology-Parser-and-Validator.git](https://github.com/netgroup/Dreamer-Topology-Parser-and-Validator.git)

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

sudo ./mininet\_deployer.py –-topology topo/topo\_vll\_pw.json

