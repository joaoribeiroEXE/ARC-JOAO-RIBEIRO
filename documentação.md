Ferramentas de Diagnóstico e Monitoramento de Redes Linux

Introdução

O monitoramento de redes é uma atividade fundamental para administradores de sistemas e infraestrutura de TI. Através dele é possível identificar falhas, gargalos de desempenho, uso excessivo de banda, problemas de conectividade e possíveis incidentes de segurança.

Neste trabalho serão analisadas quatro ferramentas amplamente utilizadas em ambientes Linux: IPTraf-NG, Iperf3, NtopNG e TCPDump. Cada uma possui características específicas que auxiliam no diagnóstico e monitoramento de redes de computadores.

---

1. IPTraf-NG

a) Identificação e Objetivo

O IPTraf-NG é uma ferramenta de monitoramento de tráfego de rede baseada em terminal. Seu objetivo é fornecer informações em tempo real sobre conexões TCP, tráfego IP, estatísticas por interface e utilização da rede.

O principal problema que resolve é a necessidade de monitoramento rápido e leve em servidores Linux sem interface gráfica.

b) Procedimento de Instalação

No Ubuntu 24.04:

sudo apt update
sudo apt install iptraf-ng

Execução:

sudo iptraf-ng

Não requer dependências adicionais.

c) Comandos Fundamentais

Iniciar a ferramenta:

sudo iptraf-ng

Principais recursos disponíveis no menu:

- IP Traffic Monitor
- General Interface Statistics
- Detailed Interface Statistics
- Statistical Breakdowns
- LAN Station Monitor

d) Cenários de Aplicação Prática

- Monitoramento de servidores Linux.
- Verificação de tráfego suspeito.
- Identificação de máquinas consumindo muita banda.
- Diagnóstico rápido de problemas de rede.

e) Pontos Fortes e Fracos

Vantagens

- Leve e rápido.
- Fácil instalação.
- Não necessita interface gráfica.
- Baixo consumo de recursos.

Desvantagens

- Interface limitada.
- Não gera gráficos avançados.
- Pouca capacidade de análise histórica.

---

2. Iperf3

a) Identificação e Objetivo

O Iperf3 é uma ferramenta utilizada para medir largura de banda, throughput e desempenho entre dois dispositivos conectados em rede.

Seu objetivo principal é avaliar a capacidade real de transmissão de dados entre dois pontos.

b) Procedimento de Instalação

Ubuntu 24.04:

sudo apt update
sudo apt install iperf3

Servidor:

iperf3 -s

Cliente:

iperf3 -c IP_DO_SERVIDOR

c) Comandos Fundamentais

Teste TCP:

iperf3 -c 192.168.1.10

Teste UDP:

iperf3 -c 192.168.1.10 -u

Teste reverso:

iperf3 -c 192.168.1.10 -R

Definir tempo de teste:

iperf3 -c 192.168.1.10 -t 30

d) Cenários de Aplicação Prática

- Validação de links de rede.
- Testes de infraestrutura.
- Diagnóstico de gargalos.
- Comparação de desempenho antes e depois de alterações na rede.

e) Pontos Fortes e Fracos

Vantagens

- Alta precisão.
- Fácil utilização.
- Suporte a TCP e UDP.
- Resultados detalhados.

Desvantagens

- Não realiza monitoramento contínuo.
- Necessita dois dispositivos para os testes.

---

3. NtopNG

a) Identificação e Objetivo

O NtopNG é uma plataforma de monitoramento de tráfego baseada em navegador web.

Seu objetivo é fornecer visualização detalhada do tráfego da rede, hosts ativos, protocolos utilizados e consumo de banda através de dashboards e gráficos avançados.

b) Procedimento de Instalação

Ubuntu 24.04:

sudo apt update
sudo apt install ntopng

Iniciar serviço:

sudo systemctl start ntopng

Acessar:

http://localhost:3000

ou

http://IP_DA_VM:3000

c) Comandos Fundamentais

Verificar status:

sudo systemctl status ntopng

Reiniciar serviço:

sudo systemctl restart ntopng

d) Cenários de Aplicação Prática

- Redes corporativas.
- Data centers.
- Monitoramento de links de internet.
- Identificação de usuários que consomem mais banda.
- Análise de protocolos utilizados.

e) Pontos Fortes e Fracos

Vantagens

- Interface web moderna.
- Gráficos em tempo real.
- Relatórios históricos.
- Identificação detalhada de protocolos e aplicações.

Desvantagens

- Maior consumo de CPU e memória.
- Configuração mais complexa.
- Alguns recursos avançados exigem versões pagas.

---

4. TCPDump

a) Identificação e Objetivo

O TCPDump é um analisador de pacotes para linha de comando.

Seu objetivo é capturar e examinar pacotes trafegando em uma interface de rede, permitindo análises detalhadas de protocolos e comunicações.

b) Procedimento de Instalação

Ubuntu 24.04:

sudo apt update
sudo apt install tcpdump

c) Comandos Fundamentais

Captura simples:

sudo tcpdump

Captura em interface específica:

sudo tcpdump -i eth0

Capturar pacotes ICMP:

sudo tcpdump icmp

Capturar porta específica:

sudo tcpdump port 80

Salvar em arquivo:

sudo tcpdump -w captura.pcap

d) Cenários de Aplicação Prática

- Troubleshooting avançado.
- Investigação de falhas.
- Auditorias de rede.
- Análise de segurança.
- Captura de tráfego para análise posterior em ferramentas como Wireshark.

e) Pontos Fortes e Fracos

Vantagens

- Extremamente poderoso.
- Captura detalhada de pacotes.
- Compatível com diversos filtros.

Desvantagens

- Curva de aprendizado maior.
- Grande volume de informações.
- Exige conhecimento de protocolos de rede.

---

Comparação Geral das Ferramentas

Ferramenta| Função Principal| Interface
IPTraf-NG| Monitoramento em tempo real| Terminal
Iperf3| Teste de largura de banda| Terminal
NtopNG| Monitoramento avançado e histórico| Web
TCPDump| Captura de pacotes| Terminal

Quando utilizar cada ferramenta?

IPTraf-NG

Quando for necessário visualizar rapidamente o tráfego da rede em tempo real.

Iperf3

Quando o objetivo for medir desempenho e largura de banda entre dois dispositivos.

NtopNG

Quando for necessária uma análise completa da rede com gráficos e relatórios.

TCPDump

Quando for necessária uma investigação detalhada de pacotes específicos.

---

Conclusão

As ferramentas estudadas possuem finalidades complementares e são amplamente utilizadas por administradores de redes Linux.

O IPTraf-NG destaca-se pela simplicidade e monitoramento em tempo real. O Iperf3 é ideal para testes de desempenho e largura de banda. O NtopNG fornece análises avançadas através de interface web e gráficos detalhados. Já o TCPDump é uma das ferramentas mais completas para captura e análise de pacotes.

O domínio dessas ferramentas permite identificar problemas rapidamente, melhorar o desempenho da infraestrutura e garantir maior confiabilidade dos serviços de rede.

Referências

Documentação oficial do NtopNG. Disponível em: https://www.ntop.org/guides/ntopng/ . Acesso em 02 jun. 2026.

Documentação oficial do Ntop. Disponível em: https://www.ntop.org/products/traffic-analysis/ntop/ . Acesso em 02 jun. 2026.

Manuais Linux Ubuntu 24.04.

Documentação oficial das ferramentas IPTraf-NG, Iperf3 e TCPDump.