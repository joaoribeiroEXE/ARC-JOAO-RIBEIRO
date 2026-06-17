Claro! Você pode colocar um mini tutorial em cada slide. Fica profissional e demonstra que você sabe instalar e utilizar as ferramentas.


---

IPTraf-NG

Instalação

1. Atualizar os repositórios

sudo apt update

Atualiza a lista de pacotes disponíveis para garantir que a versão mais recente da ferramenta seja instalada.

2. Instalar o IPTraf-NG

sudo apt install iptraf-ng

Baixa e instala a ferramenta no sistema.

Execução

sudo iptraf-ng

Ao abrir a ferramenta, será exibido um menu com várias opções.

As principais são:

IP Traffic Monitor → Monitora em tempo real todas as conexões IP da interface.

General Interface Statistics → Exibe estatísticas gerais da placa de rede.

Detailed Interface Statistics → Mostra informações detalhadas sobre os pacotes transmitidos e recebidos.

LAN Station Monitor → Exibe informações sobre os dispositivos conectados na rede local.


Demonstração prática: faça um ping entre as VMs para mostrar o aumento do tráfego.


---

Iperf3

Instalação

1. Atualizar os repositórios

sudo apt update

2. Instalar

sudo apt install iperf3

Execução

Na VM que será o servidor:

iperf3 -s

Esse comando coloca a máquina em modo servidor, aguardando conexões.

Na outra VM:

iperf3 -c IP_DO_SERVIDOR

Substitua IP_DO_SERVIDOR pelo endereço IP da primeira máquina.

Outros comandos úteis

Teste UDP:

iperf3 -c IP_DO_SERVIDOR -u

Teste por 30 segundos:

iperf3 -c IP_DO_SERVIDOR -t 30

O que observar

Ao final do teste são exibidos:

largura de banda (Mbps ou Gbps);

quantidade de dados transmitidos;

velocidade média da conexão.



---

NtopNG

Instalação

Atualizar os pacotes:

sudo apt update

Instalar:

sudo apt install ntopng

Iniciar o serviço:

sudo systemctl start ntopng

Verificar se está funcionando:

sudo systemctl status ntopng

Acesso

Abra um navegador e acesse:

http://localhost:3000

ou

http://IP_DA_VM:3000

O que mostrar

No painel principal aparecem:

dispositivos conectados;

utilização da largura de banda;

protocolos utilizados;

consumo por aplicação;

gráficos em tempo real;

estatísticas da rede.



---

TCPDump

Instalação

Atualizar os repositórios:

sudo apt update

Instalar:

sudo apt install tcpdump

Execução

Capturar todos os pacotes:

sudo tcpdump

Capturar apenas pacotes ICMP (ping):

sudo tcpdump icmp

Capturar uma porta específica:

sudo tcpdump port 80

Salvar a captura em um arquivo:

sudo tcpdump -w captura.pcap

O que mostrar

Abra o TCPDump e, em outra VM, execute:

ping IP_DA_OUTRA_VM

Os pacotes ICMP aparecerão imediatamente no terminal, mostrando a captura em tempo real.


---

Resumo para falar ao professor

IPTraf-NG: "Serve para monitorar o tráfego da rede em tempo real pelo terminal. Consigo ver conexões, interfaces e estatísticas."

Iperf3: "É usado para medir a largura de banda entre dois computadores. Uma máquina atua como servidor e a outra como cliente."

NtopNG: "É um monitor de rede com interface web. Mostra gráficos, dispositivos conectados, protocolos e consumo de banda de forma visual."

TCPDump: "É um analisador de pacotes. Ele captura tudo o que passa pela rede ou apenas o tráfego que eu escolher, como ping ou uma porta específica, sendo muito utilizado para diagnóstico e segurança."

Se você apresentar dessa forma, demonstrando a instalação, executando um comando e explicando rapidamente o resultado, estará cobrindo exatamente o que o professor espera em uma demonstração prática.