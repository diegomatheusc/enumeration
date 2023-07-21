# Nmap
O Nmap é uma das ferramentas mais populares para escanear redes. Ele pode ser executado a partir da linha de comando e está disponível em várias plataformas. É capaz de detectar hosts ativos, varrer portas abertas e identificar os serviços em execução em cada porta.

**Descoberta de Hosts Ativos:** Use a opção -sn para realizar um escaneamento de descoberta de hosts ativos, também conhecido como "Ping Scan". Isso permite verificar quais hosts estão online sem varrer portas específicas. Por exemplo:

`nmap -sn 192.168.0.0/24`

**Varredura de Portas TCP:** A opção padrão do Nmap realiza uma varredura TCP básica nas 1.000 portas mais comuns. Use a opção -p para especificar portas específicas ou um intervalo de portas. Por exemplo, para escanear a porta 80:

`nmap -p 80 192.168.0.1`

**Varredura de Portas UDP:** Algumas aplicações usam o protocolo UDP para comunicação em vez de TCP. Para escanear portas UDP, use a opção -sU. Por exemplo:

`nmap -sU -p 53 192.168.0.1`

**Varredura Abrangente de Portas TCP e UDP:** Use a opção -p- para escanear todas as 65.535 portas TCP ou UDP. No entanto, tenha em mente que essa varredura pode levar muito tempo e pode ser intrusiva para a rede.

`nmap -p- 192.168.0.1`

**Identificação do Sistema Operacional:** O Nmap pode tentar adivinhar o sistema operacional dos hosts usando a opção -O. Isso pode ajudá-lo a saber quais sistemas operacionais estão sendo executados em sua rede.

`nmap -O 192.168.0.1`

**Detecção de Serviços**: A opção -sV permite que o Nmap detecte a versão dos serviços em execução nas portas abertas. Isso pode ajudar a identificar vulnerabilidades específicas associadas a versões desatualizadas de software.

`nmap -sV 192.168.0.1`

**Output em Formato de Script:** O Nmap pode produzir saída em diversos formatos, incluindo XML, grepable e padrão. Use a opção -o para salvar a saída em um arquivo específico. Por exemplo:

`nmap -oN output.txt 192.168.0.1`

**Scripts de NSE (Nmap Scripting Engine):** O Nmap possui uma poderosa engine de scripts que permite realizar verificações mais avançadas. Use a opção --script para executar scripts específicos. Por exemplo:

`nmap --script smb-os-discovery 192.168.0.1`

# Zenmap
O Zenmap é uma interface gráfica para o Nmap, que torna o processo de escaneamento mais amigável, especialmente para aqueles que não estão familiarizados com a linha de comando.

# Netcat
O Netcat é uma ferramenta de linha de comando que pode ser utilizada para verificar a abertura de portas em um host remoto.

**Teste de Porta:** Você pode usar o Netcat para verificar se uma porta específica está aberta em um determinado host. Por exemplo, para testar se a porta 80 está aberta no host 192.168.0.1:

`nc -vz 192.168.0.1 80`

**Escutando Portas (Servidor):** O Netcat pode ser usado como um servidor para escutar em uma determinada porta e aguardar conexões. Por exemplo, para escutar na porta 1234:

`nc -l -p 1234`

**Conexão a um Servidor:** Você também pode usar o Netcat para se conectar a um servidor que esteja ouvindo em uma porta específica. Por exemplo, para se conectar a um servidor na porta 1234:

`nc 192.168.0.1 1234`

**Transferência de Arquivos:** O Netcat pode ser usado para transferir arquivos entre hosts. No host receptor, você pode escutar em uma porta e redirecionar o arquivo para onde deseja salvá-lo:
No host receptor (onde você deseja salvar o arquivo):

`nc -l -p 1234 > arquivo_recebido.txt`

No host remetente (onde o arquivo está localizado):

`nc 192.168.0.2 1234 < arquivo_local.txt`

**Conexão com Shell Remota:** O Netcat pode ser usado para criar uma conexão de shell remota em uma porta específica. No host receptor, você escuta na porta e, no host remetente, você se conecta a essa porta:
No host receptor (onde você quer obter acesso à shell remota):

`nc -l -p 1234 -e /bin/bash`

No host remetente (onde você deseja iniciar a conexão remota):

`nc 192.168.0.2 1234`

**Transferência de Texto:** Você pode usar o Netcat para enviar e receber mensagens de texto entre hosts. No host receptor, você escuta em uma porta e, no host remetente, você envia a mensagem:
No host receptor:

`nc -l -p 1234`

No host remetente (enviar mensagem "Hello"):

`echo "Hello" | nc 192.168.0.2 1234`


# Wireshark
Embora o Wireshark seja mais conhecido como um analisador de protocolos de rede, ele também pode ser usado para obter informações sobre os dispositivos ativos em uma rede.

# Angry IP Scanner
Esta é uma ferramenta de varredura de rede simples, mas eficaz, que ajuda a encontrar hosts ativos em uma rede.

