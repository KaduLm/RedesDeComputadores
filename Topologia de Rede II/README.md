Documentação da Topologia de Rede

Visão Geral

Esta documentação descreve a topologia de rede projetada para conectar diferentes áreas e dispositivos utilizando protocolos OSPF e BGP. A rede integra dispositivos como roteadores Cisco, switches, e PCs em um cenário que combina redes LAN e WAN.

Componentes da Rede

Roteadores

Router0:

Função: Roteador central, interconecta Router1 e Router3.

Protocolos: OSPF e BGP.

Interfaces configuradas:

GigabitEthernet0/0: 172.168.10.2/24 (OSPF).

GigabitEthernet0/1: 10.0.0.1/8 (BGP).

GigabitEthernet0/2: Conexão com switch para PCs (200.0.113.1/24).

Router1:

Função: Roteador intermediário entre Router0 e Router3.

Protocolos: OSPF e BGP.

Interfaces configuradas:

GigabitEthernet0/0: 172.168.10.1/24 (OSPF).

GigabitEthernet0/1: 10.0.0.2/8 (BGP).

Router2:

Função: Roteador para área OSPF que conecta à LAN.

Protocolos: OSPF.

Interfaces configuradas:

GigabitEthernet0/0: 192.168.10.1/24 (OSPF).

GigabitEthernet0/2: 192.168.10.2/24 (OSPF).

Router3:

Função: Roteador área OSPF que conecta à LAN.

Protocolos: BGP.

Interfaces configuradas:

GigabitEthernet0/0: 192.168.10.2/24 (OSPF).

GigabitEthernet0/1: Conexão com o Router2 (OSPF).

Switches

Switch Área 1:

Conecta os PCs na rede 200.0.113.0/24.

VLAN configurada para segregar tráfego interno.

Switch Área 0:

Conecta os PCs na rede 100.64.1.0/24.

VLAN configurada para segregar tráfego interno.

PCs

Área 1 (Conectados ao Switch na Rede 200.0.113.0/24):

PC0: IP 200.0.113.2/24, Gateway 200.0.113.1.

PC1: IP 200.0.113.3/24, Gateway 200.0.113.1.

Área 0 (Conectados ao Switch na Rede 100.64.1.0/24):

PC2: IP 100.64.1.2/24, Gateway 100.64.1.1.

PC3: IP 100.64.1.3/24, Gateway 100.64.1.1.

Protocolos e Configurações

OSPF

Descrição: O protocolo OSPF (Área 0 e Área 1) é usado para roteamento dinâmico dentro da rede interna.

Configuração:

Área 0: Conecta Router2 e Router3.

Área 1: Conecta Router0 e Router1.

BGP

Descrição: O protocolo BGP é usado para interconectar os roteadores Router0 e Router1.

Configuração:

Router0: Anuncia as redes 10.0.0.0/8 e 200.0.113.0/24.

Router1: Anuncia as redes 172.168.10.0/24 e 192.168.10.0/24.

Funcionamento

Tráfego LAN:

Switches em cada área distribuem o tráfego para os PCs conectados.

Roteamento Dinâmico:

OSPF distribui rotas entre os roteadores na mesma área.

BGP gerencia a comunicação entre diferentes áreas.

Conexão Entre Redes:

Os PCs das redes 200.0.113.0/24 e 100.64.1.0/24 podem se comunicar através dos roteadores e protocolos configurados.