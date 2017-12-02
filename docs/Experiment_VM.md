

# Návod na vykonanie experimentu v rozšírení Mininetu:

Najprv treba spustiť virtuálny stroj, ktorý je na stiahnutie na linku: http://repo.netgroup.uniroma2.it/nas/OSHI-VM\_8\_1.ova

Po spustení Virtual boxu a zapnutí virtuálneho stroja je treba potrebné nahrať vašu topológiu do priečinku ~/workspace/Dreamer-Mininet-Extensions/topo odkiaľ ho budeme spúšťať.

Spustenie siete v Mininete:

1. Choď do priečinka s rozšírením mininetu: cd ~/workspace/Dreamer-Mininet-Extensions/
2. Spusti Mininet, to vykonáme spustením mininet deployeru príkazom

sudo ./mininet\_deployer.py --topology [cesta k topológii napr: topo/topo\_dovi.json]

Týmto sa spustí Mininet emulácia siete. Vytvoria sa všetky uzly a fyzické pripojenia. (Koncový užívateľ do siete). Po zapnutí Mininetu ešte nie je možné pripojenie medzi koncovými používateľmi. To preto lebo ešte neboli spustené pripojenia medzi virtuálnymi častiami siete, teda neboli vytvorene tzv. &quot;virtuálne okruhy&quot;.

1. Ďalším krokom je zapnutie ryu kontrolera:

Ten zapneme z patchu ryu kontrolera:

Ako prvé sa treba prihlásiť do xterm uzla kontrolera.

Následne v priečinku: ~workspace/dreamer-ryu/ryu/app# ryu-manager

Treba spustiť príkaz: rest\_topology.py ofctl\_rest.py --observe-links

1. Následne treba pomocou nástroja VLL Pusher:

Treba x ďalšom xterme kontrolera skopírovať konfiguračný súboer pre VLL Pusher, ktorý je vytvorený pri spustení Mininet deployera:

~/workspace/Dreamer-Mininet-Extensions# cp vll\_pusher.cfg ../Dreamer-VLL-Pusher/ryu

Potom treba spustiť VLL Pusher s konfiguračným súborom. Prvý krok je v priečinku vymazať databázu virtuálnych okruhov.

~/workspace/Dreamer-VLL-Pusher/ryu# rm \*.json

Potom v tom istom priečinku spustiť VLL Pusher so súborom:

./vll\_pusher.py --controller localhost:8080 –add

Po splnení všetkých krokov je Mininet sieť spustená spolu so všetkými definovanými uzlami aj spojeniami a je pripravená na experimenty.

