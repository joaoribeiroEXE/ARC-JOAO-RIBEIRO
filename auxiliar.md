MANUAL RÁPIDO - FERRAMENTAS DE MONITORAMENTO DE REDES
1. IPTraf-NG
O que é?
O IPTraf-NG é uma ferramenta de monitoramento de rede via terminal. Ela mostra em tempo real tudo o que está acontecendo na rede, como conexões TCP, tráfego de dados e estatísticas das interfaces.
Quando usar?
Descobrir quem está utilizando a rede.
Monitorar tráfego em tempo real.
Verificar conexões ativas.
Diagnosticar problemas rapidamente.
Instalação
sudo apt update
sudo apt install iptraf-ng
Executar
sudo iptraf-ng
Opções mais importantes
IP Traffic Monitor
Mostra todas as conexões IP em tempo real.
General Interface Statistics
Estatísticas gerais da placa de rede.
Detailed Interface Statistics
Estatísticas detalhadas de pacotes enviados e recebidos.
LAN Station Monitor
Mostra os computadores conectados na rede local.
Como demonstrar
Abrir o IPTraf.
Escolher IP Traffic Monitor.
Selecionar a interface (ex.: enp0s3).
Fazer um ping de outra máquina.
Mostrar o tráfego aparecendo.
Como explicar ao professor
"Essa ferramenta serve para monitorar o tráfego da rede em tempo real. Ela mostra conexões, pacotes e estatísticas da interface. É muito utilizada para descobrir quem está utilizando a rede e identificar problemas rapidamente."
2. Iperf3
O que é?
Ferramenta usada para medir a velocidade da rede entre dois computadores.
Ela mede:
largura de banda;
throughput;
desempenho da conexão.
Quando usar?
Testar velocidade da rede.
Descobrir gargalos.
Validar links de internet.
Testar desempenho entre servidores.
Instalação
sudo apt update
sudo apt install iperf3
Servidor
iperf3 -s
Fica esperando conexões.
Cliente
iperf3 -c IP_DO_SERVIDOR
Faz o teste de velocidade.
UDP
iperf3 -c IP_DO_SERVIDOR -u
Teste de 30 segundos
iperf3 -c IP_DO_SERVIDOR -t 30
Como demonstrar
Abrir uma VM como servidor.
Executar:
iperf3 -s
Na outra VM:
iperf3 -c IP_DO_SERVIDOR
Mostrar o resultado da velocidade.
Como explicar ao professor
"O Iperf3 mede a largura de banda entre dois computadores. Uma máquina funciona como servidor e a outra como cliente. No final ele informa a velocidade da rede em Mbps ou Gbps."
3. NtopNG
O que é?
Ferramenta de monitoramento de rede com interface web.
Ela mostra:
gráficos;
consumo de banda;
dispositivos conectados;
protocolos utilizados;
estatísticas da rede.
Quando usar?
Empresas.
Data centers.
Redes corporativas.
Monitoramento contínuo.
Instalação
sudo apt update
sudo apt install ntopng
Iniciar
sudo systemctl start ntopng
Verificar
sudo systemctl status ntopng
Reiniciar
sudo systemctl restart ntopng
Abrir no navegador
http://localhost:3000
ou
http://IP_DA_VM:3000
Como demonstrar
Mostrar:
Dashboard.
Hosts conectados.
Protocolos.
Consumo de banda.
Gráficos.
Como explicar ao professor
"O NtopNG faz praticamente a mesma função do IPTraf, porém possui interface gráfica. Ele gera gráficos, identifica os dispositivos conectados, mostra quais protocolos estão sendo utilizados e fornece relatórios completos da rede."
4. TCPDump
O que é?
Ferramenta que captura pacotes de rede.
É uma das mais utilizadas para diagnóstico e segurança.
Quando usar?
Investigar falhas.
Capturar pacotes.
Analisar protocolos.
Descobrir problemas de comunicação.
Instalação
sudo apt update
sudo apt install tcpdump
Capturar tudo
sudo tcpdump
Capturar interface específica
sudo tcpdump -i enp0s3
Capturar somente Ping
sudo tcpdump icmp
Capturar porta 80
sudo tcpdump port 80
Salvar captura
sudo tcpdump -w captura.pcap
Como demonstrar
Abrir:
sudo tcpdump icmp
Na outra VM executar:
ping IP_DA_OUTRA_VM
Mostrar os pacotes aparecendo.
Como explicar ao professor
"O TCPDump captura todos os pacotes que passam pela rede ou apenas os que eu selecionar através de filtros. É muito utilizado para diagnóstico, análise de protocolos e investigação de problemas."
DIFERENÇA ENTRE AS FERRAMENTAS
IPTraf-NG → Monitora o tráfego da rede em tempo real.
Iperf3 → Mede a velocidade e o desempenho da rede.
NtopNG → Monitora a rede com gráficos e interface web.
TCPDump → Captura pacotes para análise detalhada.
RESPOSTA RÁPIDA PARA O PROFESSOR
"Por que usar cada uma?"
IPTraf-NG
Quero monitorar o tráfego rapidamente.
Iperf3
Quero medir a velocidade da rede.
NtopNG
Quero visualizar toda a rede com gráficos.
TCPDump
Quero capturar pacotes para descobrir exatamente o que está acontecendo.
DICA IMPORTANTE
Sempre explique os comandos:
sudo apt update → Atualiza a lista de pacotes.
sudo apt install → Instala a ferramenta.
sudo systemctl start → Inicia um serviço.
sudo systemctl status → Verifica se o serviço está funcionando.
-s → Coloca o Iperf3 em modo servidor.
-c → Coloca o Iperf3 em modo cliente.
-u → Faz o teste usando UDP.
-i → Escolhe a interface de rede no TCPDump.
-w → Salva a captura em um arquivo .pcap.