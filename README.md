# Born2beroot

Você vai criar sua primeira máquina no VirtualBox, seguindo instruções específicas. 
Ao final, será capaz de configurar seu próprio sistema operacional com regras rigorosas.

### Como uma máquina virtual funciona e qual é o seu propósito?
Uma máquina virtual é um software que cria um ambiente de computação independente dentro de outro sistema operacional. 
Tem como propósito o isolamento entre sistemas operacionais, produzindo uma área de testes segura, otimizando a utilização de uma máquina física e permitindo uma fácil migração e recuperação de sistemas em caso de falhas.

➤ As instruções destacam que, ao configurar um servidor, é necessário instalar apenas os serviços mínimos essenciais. Nesse contexto, a instalação de interfaces gráficas, como X.org ou equivalentes, é proibida. 

➤ Você deve agora escolher o sistema operacional, Rocky ou Debian.

### Quais são as diferenças entre os sistemas operacionais Rocky e Debian? E qual a sua escolha?
O Rocky Linux é direcionado principalmente para ambientes empresariais e servidores. E
mbora seja mais complexo e tenha uma comunidade mais recente, oferece uma alternativa para aqueles que buscam a estabilidade anteriormente proporcionada pelo CentOS.
O Debian é reconhecido por sua versatilidade, flexibilidade e vasta experiência no mercado. Sendo mais estabelecido, possui uma ampla base de usuários, proporcionando uma vantagem adicional em termos de suporte e compartilhamento de conhecimento. 
Além disso, oferece diversas opções de configuração durante a instalação, permitindo uma personalização mais detalhada desde o início.
Escolhi o Debian conforme recomendado, pois sua versatilidade, estabilidade e facilidade de suporte, juntamente com a extensa gama de tutoriais disponíveis, são aspectos que me interessam no processo de aprendizado.

### Qual é a diferença entre apt e aptitude?
"Apt" e "aptitude" são dois utilitários relacionados ao sistema de gerenciamento de pacotes em distribuições Linux baseadas no Debian. 
Ambos são utilizados para instalar, remover e gerenciar pacotes no sistema. 
O aptitude, por sua vez, possui uma interface mais visual e algumas vantagens na sugestão de soluções para problemas, enquanto o apt é mais simples nessas funcionalidades.

➤ O download do Debian pode ser feito pelo link abaixo:

[Baixar Debian](https://www.debian.org/)

➤ Para iniciar esta etapa, é necessário decidir se você pretende realizar a parte bônus ou não, pois haverá grandes diferenças na instalação. Eu escolhi incluir o bônus, então levarei em consideração as instruções adicionais.

### O que é VDI
O VDI representa uma imagem de disco virtual que contém o sistema operacional, aplicativos e dados associados a uma máquina virtual.
Ao criar uma máquina virtual no VirtualBox, você geralmente escolhe um formato de disco, como VDI, durante o processo de configuração. Isso determina como o armazenamento da máquina virtual será representado no sistema de hospedeiro. O uso do VDI facilita a portabilidade de máquinas virtuais entre diferentes sistemas que executam o VirtualBox.

### Como funciona a memória alocada dinamicamente
Significa que a VM não recebe uma alocação fixa de memória no momento em que é criada, em vez disso, a memória é alocada dinamicamente conforme necessário, até atingir um limite máximo definido.

### O que é o LVM e como ele funciona?
O LVM (Logical Volume Manager) é uma tecnologia que possibilita o gerenciamento mais flexível do espaço de armazenamento. 
Ele permite a criação de volumes lógicos, que podem ser utilizados para armazenar e organizar seus dados de acordo com a lógica que fizer mais sentido para você, independentemente do disco físico em que eles estejam realmente armazenados.

### Tipos de partições
- Primária: É a única partição em que um sistema operacional pode ser instalado. A restrição é de no máximo 4 partições primárias por disco rígido, ou 3 primárias e 1 estendida.
- Secundária/Extendida: Foi concebida para superar a limitação de 4 partições primárias em um único disco físico. Apenas uma partição secundária/extendida pode existir por disco, e ela pode conter exclusivamente partições lógicas.
- Lógica: Ocupa uma parte ou a totalidade da partição estendida/primária. Esta porção é formatada com um sistema de arquivos específico, como o ext4, e é atribuída uma letra de unidade. Dessa forma, o sistema operacional reconhece as partições lógicas ou seu sistema de arquivos.
 
### Partições solicitadas no subject
- Tamanho total: 33079636992B (30.8GiB)
- System Partition - 3144704B (3MiB): Esta informação refere-se ao tamanho da partição do sistema.
- Boot - 524288000B (500MiB): Esta é a partição de inicialização, que contém os arquivos necessários para o - processo de inicialização do sistema operacional. 
- Boot  code size - 1048576B (1MiB): Esta é a quantidade de espaço reservada para o código de inicialização, ocupando 1 megabyte dentro da partição de inicialização. 
- Root - 10737418240B (10GiB): A partição raiz é o principal diretório do sistema de arquivos que contém o sistema operacional, programas e configurações do sistema.
- Swap - 2469607424B (2.3GiB): A partição de swap é usada como uma extensão da memória RAM. Quando a RAM está cheia, o sistema usa a partição de swap para armazenar temporariamente dados menos utilizados.
- Home - 5368709120B (5GiB): Esta é a partição destinada a armazenar os diretórios pessoais dos usuários, onde ficam seus documentos, músicas, imagens, etc.
- Var - 3221225472B (3GiB): A partição 'var' armazena dados variáveis, como arquivos de log, spools de impressora e outros dados que podem mudar durante a operação do sistema.
- Srv - 3221225472B (3GiB): Geralmente, 'srv' é usado para armazenar dados de serviços ou servidores, mas a utilização específica depende da configuração do sistema.
- Tmp - 3221225472B (3GiB): 'Tmp' é geralmente usado para armazenar arquivos temporários.
- Var-long - 4294967296B (4GiB): Esta é outra partição 'var' com um tamanho diferente. Pode ser usada para armazenar dados variáveis adicionais, dependendo da necessidade do sistema.
- Crypt size - 16777216B (16MiB): Esta informação refere-se ao tamanho de uma partição criptografada.

### O que é GRUB
O GRUB, que significa "Grand Unified Bootloader," é um gerenciador de inicialização (bootloader) amplamente utilizado em sistemas operacionais baseados em Unix, como Linux. O objetivo principal do GRUB é carregar e iniciar o sistema operacional no computador quando este é inicializado.

### Entrar de máquina virtual
- Selecionar ```Debian``` GNU/Linux
- Password de encriptacao
- Login criado
- Password do login criado
- ```lsblk``` - Verificar as particoes
- ```apt update``` - Atualiza lista de pacotes
- ```apt upgrade``` - Verifica versoes mais recentes

### O que é SUDO?
O comando sudo em sistemas Unix/Linux, como o Linux, concede temporariamente permissões de superusuário a um usuário regular. Utilizado para realizar ações que afetam o sistema, o sudo exige autenticação, garantindo segurança e controle sobre operações críticas. Isso permite que usuários autorizados executem comandos com privilégios elevados de forma controlada e temporária.

### Instalação do sudo
- ```Su``` - Entrar como usuario root
- Password do root
- ```apt install sudo``` - Instalar pacotes necessarios
- ```sudo reboot``` - Reiniciar a maquina
- ```sudo -V``` - Para checar a instalacao do sudo
- ```sudo adduser login``` - Checar se o login criado na instalacao ja existe
- ```sudo addgroup user42``` - Criar grupo que foi solicitado no subject
- ```getent group user42``` - Checar se o grupo foi criado corretamente, getent (get entries)
- ```sudo adduser login user42``` - Adicionar usuario no grupo user42
- ```sudo adduser login sudo``` - Adicionar usuario no grupo sudo e lhe dar as permissoes de usuario sudo
- ```getent group user42``` - Checar se adicionamos o usuario corretamente no grupo
- ```getent group sudo``` - Checar se adicionamos o usuario corretamente no grupo

### O que é o AppArmor?
O AppArmor é um sistema de controle de acesso obrigatório para Linux. 
Ele atua como uma camada adicional de segurança, restringindo as ações de programas e limitando seu acesso a recursos específicos do sistema. 
O AppArmor ajuda a proteger contra ameaças de segurança ao restringir as ações potenciais de programas maliciosos ou vulneráveis.

### Instalação do AppArmor
- ```sudo apt install apparmor apparmor-profiles apparmor-utils``` - Instalar o apparmor
- ```sudo apparmor_status``` - Verificar status
- ```systemctl status apparmor``` - Conferir se esta funcionando

### O que é SSH e pra que serve
O SSH é uma ferramenta fundamental para a administração e o acesso seguro a sistemas remotos. Ele é amplamente utilizado em ambientes de servidores, data centers e em qualquer situação em que seja necessário realizar operações remotas de forma segura.

### Instalação e configuração do SSH
- ```sudo apt update``` - Atualizar a lista de pacotes disponíveis nos repositórios configurados no sistema
- ```sudo apt install openssh-server``` - Instalar OpenSSH, principal ferramenta de conectividade para o login remoto com o protocolo SSH
- ```Y``` - Para confirmar
- ```sudo service ssh status``` - Verificar se esta ativo e foi instalado corretamente
- ```su``` - Ir para o root para ter as permissoes que precisamos
- Password do root
- ```nano /etc/ssh/sshd_config``` - Alterar configuracoes do ssh
- Encontrar ```#Port22``` e alterar para ```Port4242``` - Conforme solicitada a porta 4242 no subject
- Encontrar ```#PermitRootLogin no``` e apagar o # para tirar do comentario - Conforme solicitado no subject para nao permitir o login pelo usuario Root.
- Salvar alteracoes feitas
- ```nano /etc/ssh/ssh_config``` - Alterar outras configuracoes do ssh
- Encontrar ```#Port22``` e alterar para ```Port4242``` - Conforme solicitada a porta 4242 no subject
- ```sudo service ssh restart``` - Reiniciar o SSH para atualizar as alteraoes
- ```sudo service ssh status``` - Confirmar alteracoes

### O que é UFW e pra que serve
O UFW, que significa "Uncomplicated Firewall," é uma ferramenta de firewall projetada para simplificar o gerenciamento de regras e facilitar o bloqueio ou liberação de tráfego em portas específicas.

### Instalação e configuração do UFW
- ```sudo apt install ufw``` - Instalar o UFW
- ```Y``` - Confirmar instalacao
- ```sudo ufw enable``` - Ativar UFW
- ```sudo ufw allow 4242``` - Abrir porta 4242 confirme solicitado no subject
- ```sudo ufw status``` - Conferir se esta ativo e se a unica porta aberta e a 4242

### O que é DHCP e quais os riscos de deixar a porta 68 aberta
O DHCP, que representa Protocolo de Configuração Dinâmica de Host, é um serviço utilizado em redes de computadores para automatizar a atribuição de endereços IP e configurações associadas. Deixar a porta 68 aberta, vinculada ao serviço DHCP, pode expor a rede a riscos como atribuição não autorizada de endereços IP, roubo de identidade, ataques de negação de serviço (DoS), exploração de vulnerabilidades do serviço DHCP e configurações não seguras. Fechar portas e implementar boas práticas de segurança são fundamentais para proteger a integridade e confiabilidade da rede.

### Fechar a porta 68
- ```sudo ss -tunlp``` - Conferir se a porta 68 aberta
- ```hostname -I``` - Conferir o IP
- ```sudo nano /etc/network/interfaces``` - Entrar no arquivo para configurar as interfaces de rede
- Encontrar ```allow-hotplug enp0s3``` e alterar para ```auto enp0s3``` - Para configurar automaticamente a interface
- Encontrar ```iface enp0s3 inet dhcp``` e alterar para ```iface enp0s3 inet static``` - Alterar a configuracao de IP para estatica e nao DHCP
- Adicionar as linhas a seguir no final
- ```address your_current_ip``` - Definir o endereço de IP estático
- ```netmask 255.255.0.0``` - Aqui você está configurando a máscara de sub-rede
- ```gateway 10.11.254.254``` - Aqui define o gateway padrão
- ```dns-nameservers 10.11.254.254``` - Aqui especifica o servidor DNS
- ```sudo systemctl restart networking``` - Reiniciar
- ```sudo systemctl status networking``` - Verificar status
- ```sudo reboot``` - Reiniciar a maquina
- ```ss -tulnp``` - Verificar se fechou a porta
  
### Qual a diferença entre NAT e Bridged Adapter?
- NAT: Quando uma máquina virtual utiliza NAT, ela compartilha o endereço IP do host para conexões externas, modificando as informações de origem nos pacotes de dados para parecerem originadas do host.
- Rede em Ponte: Ao empregar uma rede em ponte, a máquina virtual adquire seu próprio endereço IP exclusivo na mesma rede física do host, permitindo que seja reconhecida como um dispositivo independente.

### Conectar via SSH
- Fechar a maquina virtual
- ir em Settings / Network
- Trocar de NAT para Bridged Adapter
- ```sudo reboot``` - Para reiniciar
- ```hostname -I``` - Descobrir o ip do hostname
- Ir para o terminal
- ```ssh login@ip -p 4242``` - Conectar via SSH

### Configuração de senha forte para o sudo
- ```mkdir /var/log/sudo``` - Criar a pasta onde ficara os logs das utilizacoes do sudo, conforme solicitado
- ```touch /etc/sudoers.d/sudo_config``` - Criar o ficheiro com as configuracoes de senha
- ```nano /etc/sudoers.d/sudo_config``` - Adicionar comandos abaixo com especificacoes solicitadas e necessarias
- ```Defaults  env_reset``` -  Ajuda a garantir um ambiente limpo e controlado ao executar comandos com privilégios elevados
- ```Defaults  passwd_tries=3``` - O número máximo de tentativas de senha para um comando sudo é 3
- ```Defaults  badpass_message="Error"``` - Especifica uma mensagem personalizada de erro que será exibida se um usuário inserir uma senha incorreta ao usar o sudo
- ```Defaults  logfile="/var/log/sudo/sudo_log"``` - Define o caminho do arquivo de log para o sudo
- ```Defaults  log_input, log_output``` - Habilita o registro de entrada e saída no arquivo de log configurado
- ```Defaults  iolog_dir="/var/log/sudo"``` - Especifica o diretório onde os logs de entrada e saída do sudo serão armazenados
- ```Defaults  requiretty``` - Indica que o sudo só pode ser executado a partir de um terminal interativo (TTY)
- ```Defaults  secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"``` - Especifica os diretórios nos quais os comandos podem ser procurados quando o sudo é usado

### Vantagens e desvantagens do uso de políticas de senha rigorosas
- Vantagens: Contribuem para senhas mais seguras, dificultando a adivinhação ou a quebra por força bruta.
- Desvantagens: Senhas muito complexas ou requisitos frequentes de alteração podem levar os usuários a escolher senhas mais fáceis de lembrar ou a anotá-las, comprometendo a segurança.

### O que é Libpam-pwquality
A função específica do libpam-pwquality é fornecer verificações e políticas de qualidade de senha durante o processo de autenticação. Essa biblioteca é frequentemente usada para melhorar a segurança das senhas no sistema. 

### Configurações de política de senhas fortes
- ```nano /etc/login.defs``` - Entrar no ficheiro e editar politicas de senha
- Encontrar ```PASS_MAX_DAYS 99999``` e alterar para ```PASS_MAX_DAYS 30``` - Maximo de 30 dias utilizando a mesma senha.
- Encontrar ```PASS_MIN_DAYS 0``` e alterar para ```PASS_MIN_DAYS 2``` - Minimo de 2 dias com a mesma senha
- ```PASS_WARN_AGE 7``` - Ja esta configurado certo, para dar um aviso 7 dias antes da senha expirar
- ```sudo apt install libpam-pwquality``` - Instalar a biblioteca Libpam-pwquality para colocar os requisitos
- ```Y``` - Confirmar instalacao
- ```nano /etc/pam.d/common-password``` - Entrar no arquivo para colocar requisitos solicitados
- Encontrar ```pam_pwquality.so retry-=3``` - Atualmente so existe o comando para tentar no maximo 3 vezes
- ```minlen=10``` - O número mínimo de caracteres que a senha deve conter
- ```ucredit=-1``` - Deve conter pelo menos uma letra maiúscula
- ```dcredit=-1``` - Deve conter pelo menos um dígito
- ```lcredit=-1``` - Deve conter pelo menos uma letra minúscula
- ```maxrepeat=3``` - Não pode ter o mesmo carácter mais de 3 vezes seguidas
- ```reject_username``` - Não pode conter o nome do utilizador
- ```difok=7``` - Deve ter pelo menos 7 caracteres que não façam parte da senha antiga
- ```enforce_for_root``` - Implementar esta política para o utilizador root

### O que é script
É uma sequência de comandos armazenados num ficheiro que, quando executado, fará a função de cada comando.

### Construindo o script
➤ Arquitetura 
- ```arch=$(uname -a)``` 
- arch - Variavel
- unane - Informacoes do sistema
- -a - Todas as informacoes disponiveis, incluindo a versao kernel
 
➤ CPU fisica
- ```cpuf=$(grep "physical id" /proc/cpuinfo | wc -l)```
- cpuf=$ - Variavel
- grep - Procurar padroes
- "physical id" - Padrao a ser procurado
- /proc/cpuinfo - Arquivo que vai procurar
- | - Redireciona a saída do comando à esquerda para a entrada do comando à direita
- wc - Comando que conta palavras
- -l - Especifica que apenas o número de linhas deve ser contado

➤ CPU virtual
- ```cpuv=$(grep "processor" /proc/cpuinfo | wc -l)```
- cpuv=$ - Variavel
- "processor" - Padrao a ser procurado
- /proc/cpuinfo - Arquivo que vai procurar

➤ Memoria RAM
- ```ram_total=$(free --mega | awk '$1 == "Mem:" {print $2}')```
- ram_total=$ - Variavel
- free - Exibir informações sobre a memória
- --mega - Exibir em megabytes
- awk - Vai filtrar as informacoes
- $1 == "Mem:" - Procura linhas em que o primeiro campo e "Mem:"
- {print $2} - Printa a segunda coluna que e o total de memoria RAM em megabytes
- ```ram_use=$(free --mega | awk '$1 == "Mem:" {print $3}')```
- ram_use=$ - Variavel
- {print $3} - Printa a terceira coluna que e a quantidade de memoria RAM em uso
- ```ram_percent=$(free --mega | awk '$1 == "Mem:" {printf("%.2f"), $3/$2*100}')```
- ram_percent=$ - Variavel
- "%.2f" - Formula a saida no formato de porcentagem
- $3/$2*100 = Calculo da porcentagem

➤ Memoria em disco
- ```disk_total=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_t += $2} END {printf ("%.1fGb\n"), disk_t/1024}')```
- disk_total=$ - Variavel
- df - Comando usado para exibir informacoes sobre o espaco em disco
- -m - Especifica pra ser exibido em megabytes
- grep -v - Procura padroes e exclui eles
- disk_t += $2 - Criou uma variavel que esta somando os valores da segunda coluna que representa o tamanho do disco
- END - Apos o awk indica que o bloco de código seguinte será executado após todas as linhas serem processadas
- printf ("%.1fGb\n") -  Imprimir um valor de ponto flutuante (float) com uma casa decimal, seguido pela unidade de medida "Gb"
- disk_t/1024 - Converte a variabel de megabytes para gigabytes
- ```disk_use=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_u += $3} END {print disk_u}')```
- disk_use=$ - Variavel
- {disk_u += $3} - Criou uma variavel que esta somando os valores da terceira coluna que representa o tamanho em uso do disco
- {print disk_u} - Imprime a variavel com a soma total do uso de disco
- ```disk_percent=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_u += $3} {disk_t+= $2} END {printf("%d"), disk_u/disk_t*100}')```
- disk_percent=$ - Variavel
- {printf("%d"), disk_u/disk_t*100}') - Calculo da porcentagem de uso do disco
  
➤ Porcentagem de utilizacao da CPU
- ```cpul=$(vmstat 1 2 | tail -1 | awk '{printf $15}')```
- cpul=$ - Variavel
- vmstat - Exibe informações sobre estatísticas de memória virtual
- 1 - Especifica que as estatísticas devem ser exibidas a cada segundo
- 2 - Indica que o vmstat deve ser executado duas vezes para coletar dados em dois intervalos de tempo de 1 segundo
- tail - E usado para exibir as últimas linhas de um arquivo ou saída de um comando
- -1 - Significa que queremos apenas a última linha da saída do vmstat
- '{printf $15}' - Printar a coluna 15 que representa o percentual de uso da CPU pelo sistema
- ```cpu_op=$(expr 100 - $cpul)```
- cpu_op=$ - Variavel
- expr - E utilizado para avaliar expressões aritmética
- 100 - $cpul - Esta diminuindo a variavel de 100
- ```cpu_fin=$(printf "%.1f" $cpu_op)```
- cpu_fin=$ - Variavel
- printf "%.1f" - Formula a saida como um número de ponto flutuante com uma casa decimal 

➤ Ultimo reboot
- ```lb=$(who -b | awk '$1 == "system" {print $3 " " $4}')```
- lb=$ - Variavel
- who - Exibir informações sobre os usuários que estão atualmente conectados
- -b - Especifica que queremos informações sobre a última inicialização do sistema
- $1 == "system" - Filtra a linha que tem system na primeira coluna
- {print $3 " " $4} - Imprime o terceiro e o quarto campo da linha, que representam a data e a hora de inicialização do sistema

➤ Utilizacao de LVM
- ```lvmu=$(if [ $(lsblk | grep "lvm" | wc -l) -gt 0 ]; then echo yes; else echo no; fi)```
- lvmu=$ - Variavel
- if - Comeca uma estrutura condicional
- lsblk | grep "lvm" | wc -l - Filtra as linhas de lvm nas informacoes sobre os blocos d armazenamento do sistema e soma
- -gt 0 - -gt significa "maior que"
- then echo yes - Se for maior que zero a variavel recebera um yes
- else echo no - Se for menor ou igual a zero a variavel recebera um no
- fi - Encerra a condicional

➤ Numero de conexoes TCP
- ```tcpc=$(ss -ta | grep ESTAB | wc -l)```
- tcpc=$ - Variavel
- ss - Exibir informações sobre os sockets de rede.
- -t - Indica que apenas as conexões TCP
- -a - Mostra todas as conexões

➤ Numero de usuarios
- ```ulog=$(users | wc -w)```
- ulog=$ - Variavel
- users - Exibe uma lista dos usuários que estão atualmente conectados ao sistema
- wc -w - O -w especifica que o comando deve contar o número de palavras

➤ Endereco de IP e MAC
- ```ip=$(hostname -I)```
- ip=$ - Variavel
- hostname - Este comando é utilizado para obter ou definir o nome do host da máquina
- -I - Ele retorna os endereços IP associados ao host
- ```mac=$(ip link | grep "link/ether" | awk '{print $2}')```
- mac=$ - Variavel
- ip link - Exibir informações sobre as interfaces de rede no sistema
- awk '{print $2} - Imprimir o segundo campo da linha, que é o endereço MAC

➤ Numero de comandos executados com sudo
- ```cmnd=$(journalctl _COMM=sudo | grep COMMAND | wc -l)```
- cmnd=$ - Variavel
- journalctl - Acessar os logs do sistema
- _COMM=sudo - Filtro para apenas as entradas do log associadas ao comando sudo
- grep COMMAND - filtra as linhas que contenham a string "COMMAND", ajudando a identificar entradas relacionadas a comandos

➤ Estrutura final da forma que foi solicitada no subject recebendo as variaveis criadas
```wall "	Architecture: $arch
	CPU physical: $cpuf
	vCPU: $cpuv
	Memory Usage: $ram_use/${ram_total}MB ($ram_percent%)
	Disk Usage: $disk_use/${disk_total} ($disk_percent%)
	CPU load: $cpu_fin%
	Last boot: $lb
	LVM use: $lvmu
	Connections TCP: $tcpc ESTABLISHED
	User log: $ulog
	Network: IP $ip ($mac)
	Sudo: $cmnd cmd"
```
