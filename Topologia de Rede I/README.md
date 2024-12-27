Documentação da Topologia de Rede
Descrição Geral
Este projeto representa uma topologia de rede composta por 4 roteadores (Router0, Router1, Router2, Router3) interligados com diferentes protocolos de roteamento (OSPF, RIP e BGP) e conectados a PCs e switches. A configuração foi projetada para permitir a comunicação entre diferentes redes com um mix de protocolos.

Componentes da Rede
Router0 (OSPF e BGP):

Interfaces:
Gig0/0: IP 10.0.0.2 (OSPF)
Gig0/1: IP 192.168.10.2 (BGP)
Protocolos:
OSPF: Configurado para anunciar as redes 10.0.0.0/8 e 1.0.0.0/8.
BGP: Configurado para anunciar 192.168.10.0/24.
Router1 (OSPF e RIP):

Interfaces:
Gig0/0: IP 10.0.0.1 (OSPF)
Gig0/2: IP 172.16.0.1 (RIP)
Protocolos:
OSPF: Configurado para anunciar as redes 10.0.0.0/8.
RIP: Configurado para as redes 172.16.0.0/24.
Router2 (RIP):

Interfaces:
Gig0/0: IP 172.16.0.2
Gig0/1: IP 198.51.100.1
Protocolos:
RIP: Configurado para anunciar 172.16.0.0/24 e 198.51.100.0/24.
Router3 (BGP):

Interfaces:
Gig0/0: IP 192.168.10.1
Gig0/1: IP 200.0.113.1
Protocolos:
BGP: Configurado para anunciar a rede 200.0.113.0/24.
Dispositivos de Acesso
Switch0:

Conectado ao Router1 via interface Fa0/3.
Conectado aos PCs PC0 (10.0.0.2) e PC1 (10.0.0.3).
Switch1:

Conectado ao Router2 via interface Fa0/3.
Conectado aos PCs PC2 (198.51.100.2) e PC3 (198.51.100.3).
Switch2:

Conectado ao Router3 via interface Fa0/3.
Conectado aos PCs PC4 (200.0.113.2) e PC5 (200.0.113.3).
Configuração dos Protocolos de Roteamento
OSPF
Configurado no Router0 e Router1.
Redes Anunciadas:
Router0: 10.0.0.0/8, 1.0.0.0/8.
Router1: 10.0.0.0/8.
RIP
Configurado no Router1 e Router2.
Redes Anunciadas:
Router1: 172.16.0.0/24.
Router2: 172.16.0.0/24, 198.51.100.0/24.
BGP
Configurado no Router0 e Router3.
Redes Anunciadas:
Router0: 192.168.10.0/24.
Router3: 200.0.113.0/24.
