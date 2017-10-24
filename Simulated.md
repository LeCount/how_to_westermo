# Dra igång ett virtuellt testsystem
För att dra igång ett virutelt testsystem med fyra duttar.

Gå till din lokala fawlty/src och något i stil med:

sudo PYTHONPATH=. engine/towers.py --topology ../cfg/topology/mrwalt.yml /home/rrr/Documents/weos/images/WeOS-corazon-9.99.bin

Drar igång fawlty med mrwalts topologi, dvs 4 duttar som är kopplad ihop på 100 sätt. Laddar på alla duttar med WeOS-corazon-9.99.bin

# Kör igång ett test på ditt virtuella testsystem:

Gå till din lokala fawlty/src och kör typ:

sudo PYTHONPATH=. python engine/fawlty.py -t ../cfg/topology/mrwalt.yml -s test/openvpn/frnt_ring -m "&qemu"

Kör igång testet gre/connectiviy


# sätt upp i /etc/conserver/conserver.cf (för fyra duttar)

default towers {
        master localhost;
        type host;
        host localhost;
        portinc 10;
}

default towers-ser {
        include towers;
        protocol raw;
        portbase 65000;
}

default towers-qemu {
        include towers;
        protocol telnet;
        portbase 65001;
}

console qser1 { include towers-ser; port 1; }
console qser2 { include towers-ser; port 2; }
console qser3 { include towers-ser; port 3; }
console qser4 { include towers-ser; port 4; }

console ser1-qemu { include towers-qemu; port 1; }
console ser2-qemu { include towers-qemu; port 2; }
console ser3-qemu { include towers-qemu; port 3; }
console ser4-qemu { include towers-qemu; port 4; }
