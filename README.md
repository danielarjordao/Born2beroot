# Bron2beroot

Você vai criar sua primeira máquina no VirtualBox, seguindo instruções específicas. 
Ao final, será capaz de configurar seu próprio sistema operacional com regras rigorosas.

## Como uma máquina virtual funciona e qual é o seu propósito?
Uma máquina virtual é um software que cria um ambiente de computação independente dentro de outro sistema operacional. 
Tem como propósito o isolamento entre sistemas operacionais, produzindo uma área de testes segura, otimizando a utilização de uma máquina física e permitindo uma fácil migração e recuperação de sistemas em caso de falhas.

➤ As instruções destacam que, ao configurar um servidor, é necessário instalar apenas os serviços mínimos essenciais. Nesse contexto, a instalação de interfaces gráficas, como X.org ou equivalentes, é proibida. 

## 1 - Sistema operacional
Você deve agora escolher o sistema operacional, Rocky ou Debian.

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

As instruções indicam a criação de pelo menos 2 partições criptografadas usando LVM (Logical Volume Manager).
As partições devem ser organizadas de acordo com o modelo.
