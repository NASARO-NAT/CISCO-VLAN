1. Porta Access
🔹 Uso principal: Conectar dispositivos finais como PCs, impressoras, telefones IP.
🔹 VLAN: Só pode pertencer a uma única VLAN.
🔹 Marcação de VLAN: Não marca os pacotes com um ID de VLAN (tráfego sem tag).
🔹 Protocolo: Funciona sem necessidade de 802.1Q.
🔹 Exemplo de configuração:

bash
Copiar
Editar
interface GigabitEthernet0/1
 switchport mode access
 switchport access vlan 10
🔹 Quando usar?

Quando um dispositivo precisa estar em apenas uma VLAN.
Para conexões de usuários finais.
2. Porta Trunk
🔹 Uso principal: Conectar switches entre si ou conectar roteadores e servidores que suportam VLANs.
🔹 VLANs: Pode transportar múltiplas VLANs.
🔹 Marcação de VLAN: Marca os pacotes com um ID de VLAN usando 802.1Q.
🔹 Protocolo: Utiliza IEEE 802.1Q para identificar VLANs.
🔹 Exemplo de configuração:

bash
Copiar
Editar
interface GigabitEthernet0/24
 switchport mode trunk
 switchport trunk allowed vlan 10,20,30,40,50
🔹 Quando usar?

Para conectar switches a outros switches.
Para conectar switches a roteadores para roteamento entre VLANs.
Quando for necessário transportar múltiplas VLANs na mesma conexão.
Resumo: Comparação Access x Trunk
Característica	Porta Access	Porta Trunk
Uso	PCs, Impressoras, Telefones IP	Switches, Roteadores, Servidores
VLANs	Apenas 1 VLAN	Múltiplas VLANs
Marcação	Não adiciona tag VLAN	Adiciona tag VLAN (802.1Q)
Exemplo	switchport mode access	switchport mode trunk
