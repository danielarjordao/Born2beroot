# Bron2beroot

Você vai criar sua primeira máquina no VirtualBox, seguindo instruções específicas. 
Ao final, será capaz de configurar seu próprio sistema operacional com regras rigorosas.

## Como uma máquina virtual funciona e qual é o seu propósito?
Uma máquina virtual é um software que cria um ambiente de computação independente dentro de outro sistema operacional. 
Tem como propósito o isolamento entre sistemas operacionais, produzindo uma área de testes segura, otimizando a utilização de uma máquina física e permitindo uma fácil migração e recuperação de sistemas em caso de falhas.

➤ As instruções destacam que, ao configurar um servidor, é necessário instalar apenas os serviços mínimos essenciais. Nesse contexto, a instalação de interfaces gráficas, como X.org ou equivalentes, é proibida. 

## 1 - Sistema operacional
Você deve agora escolher o sistema operacional, Rocky ou Debian.

O LVM (Logical Volume Manager) é uma tecnologia que possibilita o gerenciamento mais flexível do espaço de armazenamento. 
Ele permite a criação de volumes lógicos, que podem ser utilizados para armazenar e organizar seus dados de acordo com a lógica que fizer mais sentido para você, independentemente do disco físico em que eles estejam armazenados realmente.
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
### O que é o AppArmor?
O AppArmor é um sistema de controle de acesso obrigatório para Linux. 
Ele atua como uma camada adicional de segurança, restringindo as ações de programas e limitando seu acesso a recursos específicos do sistema. 
O AppArmor ajuda a proteger contra ameaças de segurança ao restringir as ações potenciais de programas maliciosos ou vulneráveis.

➤ O download do Debian pode ser feito pelo link abaixo:

[Baixar Debian](https://www.debian.org/)

## 2 - Instalação da Máquina

Para iniciar esta etapa, é necessário decidir se você pretende realizar a parte bônus ou não, pois haverá grandes diferenças na instalação. 
Eu escolhi incluir o bônus, então levarei em consideração as instruções adicionais.

### O que é o LVM e como ele funciona?
O LVM (Logical Volume Manager) é uma tecnologia que possibilita o gerenciamento mais flexível do espaço de armazenamento. 
Ele permite a criação de volumes lógicos, que podem ser utilizados para armazenar e organizar seus dados de acordo com a lógica que fizer mais sentido para você, independentemente do disco físico em que eles estejam realmente armazenados.

### Tipos de partições
Primária: É a única partição em que um sistema operacional pode ser instalado. A restrição é de no máximo 4 partições primárias por disco rígido, ou 3 primárias e 1 estendida.
Secundária/Extendida: Foi concebida para superar a limitação de 4 partições primárias em um único disco físico. Apenas uma partição secundária/extendida pode existir por disco, e ela pode conter exclusivamente partições lógicas.
Lógica: Ocupa uma parte ou a totalidade da partição estendida/primária. Esta porção é formatada com um sistema de arquivos específico, como o ext4, e é atribuída uma letra de unidade. Dessa forma, o sistema operacional reconhece as partições lógicas ou seu sistema de arquivos.
 
### Partições solicitadas no subject
Tamanho total: 33079636992B (30.8GiB)
System Partition - 3144704B (3MiB): Esta informação refere-se ao tamanho da partição do sistema.
Boot - 524288000B (500MiB): Esta é a partição de inicialização, que contém os arquivos necessários para o processo de inicialização do sistema operacional. 
Boot  code size - 1048576B (1MiB): Esta é a quantidade de espaço reservada para o código de inicialização, ocupando 1 megabyte dentro da partição de inicialização. 
Root - 10737418240B (10GiB): A partição raiz é o principal diretório do sistema de arquivos que contém o sistema operacional, programas e configurações do sistema.
Swap - 2469607424B (2.3GiB): A partição de swap é usada como uma extensão da memória RAM. Quando a RAM está cheia, o sistema usa a partição de swap para armazenar temporariamente dados menos utilizados.
Home - 5368709120B (5GiB): Esta é a partição destinada a armazenar os diretórios pessoais dos usuários, onde ficam seus documentos, músicas, imagens, etc.
Var - 3221225472B (3GiB): A partição 'var' armazena dados variáveis, como arquivos de log, spools de impressora e outros dados que podem mudar durante a operação do sistema.
Srv - 3221225472B (3GiB): Geralmente, 'srv' é usado para armazenar dados de serviços ou servidores, mas a utilização específica depende da configuração do sistema.
Tmp - 3221225472B (3GiB): 'Tmp' é geralmente usado para armazenar arquivos temporários.
Var-long - 4294967296B (4GiB): Esta é outra partição 'var' com um tamanho diferente. Pode ser usada para armazenar dados variáveis adicionais, dependendo da necessidade do sistema.
Crypt size - 16777216B (16MiB): Esta informação refere-se ao tamanho de uma partição criptografada.

### O que é GRUB
O GRUB, que significa "Grand Unified Bootloader," é um gerenciador de inicialização (bootloader) amplamente utilizado em sistemas operacionais baseados em Unix, como Linux. O objetivo principal do GRUB é carregar e iniciar o sistema operacional no computador quando este é inicializado.

### Passo a passo
New
Name / Machine folder (soginfre) / Linux / Debian 64-bit
The recommended memory size: 1024MB
Create a virtual hard disk now
VDI (VirtualBox Disk Image) - Pois descarregamos um disco virtual
Dynamically allocated - Significa que a VM não recebe uma alocação fixa de memória no momento em que é criada, em vez disso, a memória é alocada dinamicamente conforme necessário, até atingir um limite máximo definido.
Definir tamanho total - 33079636992B (30.8GiB)
Settings
Storage
Empty
Optical Drive - Selecionar arquivo do Debian baixado.
Start
Install
English
Other
Europe
Portugal
United States
login42 - Conforme solicitado no subject
Vazio
Password
Repeat password
login - Pois pede um usuário extra que não seja o root.
login
Password
Repeat password
Lisboa
Manual - Pois precisamos editar as partições
SCI3 (SDA) - Escolher aonde queremos criar as partições
Yes
pri/log - Esta criada, agora temos que começar a configurar
Create a new partition
525336576B (524288000B + 1048576B) - Primeiro estamos criando o Boot
Primary - Pois é a partição de inicialização
Mount point
/boot
Done setting up the partition
pri/log
Create a new partition
max - Todo o espaço será para memória lógica agora
Logical
Mount point
Do not mount it - Pois ainda faremos as partições
Done setting up the partition
Configure encrypted volumes - Encriptar as partições
Yes
Create encrypted volumes
Selecionar /dev/sda5 - Selecionar o que encriptar
Done setting up the partition
Finish
Yes
Cancel - Pois ainda está vazia
Password - Encriptação
Repeat password - Encriptação
Configure the Logical Volume Manager - Configurar volume lógico
Yes
Create volume group
LVMGroup - Conforme solicitado no subject
Selecionar /dev/mapper/sda5_crypt
Create logical volume
LVMGroup
root - Nome
10737418240B - Tamanho
Create logical volume
LVMGroup
swap
2469607424B
Create logical volume
LVMGroup
home
5368709120B
Create logical volume
LVMGroup
var
3221225472B
Create logical volume
LVMGroup
srv
3221225472B
Create logical volume
LVMGroup
tmp
3221225472B
- Create logical volume
LVMGroup
var-log
4294967296B
Finish
home
Use as:
Ext4 - O sistema de arquivos mais amplamente utilizado nas distribuições Linux
Mount point - home
Done setting up the partition
root
Use as:
Ext4 - O sistema de arquivos mais amplamente utilizado nas distribuições Linux
Mount point - root
Done setting up the partition
srv
Use as:
Ext4 - O sistema de arquivos mais amplamente utilizado nas distribuições Linux
Mount point - srv
Done setting up the partition
swap
Use as:
swap area - Para ser usada como uma extensão da memória
Mount point - swap
Done setting up the partition
tmp
Use as:
Ext4 - O sistema de arquivos mais amplamente utilizado nas distribuições Linux
Mount point - temp
Done setting up the partition
var
Use as:
Ext4 - O sistema de arquivos mais amplamente utilizado nas distribuições Linux
Mount point - var
Done setting up the partition
var-log
Use as:
Ext4 - O sistema de arquivos mais amplamente utilizado nas distribuições Linux
Enter manually
/var/log
Done setting up the partition
Finish partitioning and write changes to disk
Yes
No - Pois não precisamos de pacotes adicionais.
Portugal
deb.debian.org - Pois é a nossa região onde teremos uma melhor conexão
Continue
No - Não queremos que os programadores vejam as nossas estatísticas
Continue (Não selecionar nada)
Yes - Para instalar o GRUB boot
/dev/sda - Aonde instalar
Continue

