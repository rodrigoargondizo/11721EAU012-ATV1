NOME: RODRIGO FARIA ARGONDIZO
MATRÍCULA: 11721EAU012

ATIVIDADE 1 - SISTEMAS EMBARCADOS 1 

RESUMO DA ATIVIDADE 1

Inicialmente para começarmos o desenvolvimento, foi necessário a instalação do wsl(Windows Subsystem for Linux 2), para conseguir utilizar o linux 20.04 de forma nativa no windows 10. Para a instalação do wsl2, foi preciso utilizar o PowerShell do windows 10. Após ter o procedimento concluido , foi criado um usuário dentro do linux e também através dos comandos sudo apt update , sudo apt upgrade foram feitas as devidas atualizações do sistema. 

Agora que temos o linux pronto para uso dentro do w10, atráves do wsl, foram criados os diretórios onde será desenvolvido a atividade proposta. O próximo passo foi instalar o compilador e a ferramenta de controle de versão, depois foram clonados utilizando a ferramenta de controle de versão, os arquivos necessários para realização das atividades de laboratório.

Foram instaladas também as ferramentas GCC ARM Toolchain e de gravação e depuração de código. Para tudo ficar mais organizado e intuitivo, foi instalado a IDE(Integrated Development Environment - IDE) Visual Studio Code, de código aberto desenvolvido pela microsoft. 

Antes de iniciar o desenvolvimento do código, foi necessário a instalação do USBIP no wsl, para que a comunicação USB seja possível, para isso foi preciso atualizar o kernel do wsl utilizando novamento o windows power shell. No windows, devemos instalar o cliente  USB/IPe e o banco de dados de identificadores USB no Linux. No ubuntu foi preciso instalar os seguintes pacotes linux-tools-generic e hwdata.

Vamos agora fazer a conexão do gravador USB do st-link na porta usb do computador, para prosseguir foi verificado se o serviço udev está rodando, e instalado o driver do ST-LINK no windows, após algumas configurações a comunicação está pronta. Com tudo isso em mãos, agora conseguimos começar o desenvolvimento do código desenvolvido nos roteiros 02 e 03 do laboratório. 

Iremos dividir a descrição do cógido conforme os arquivos usados, temos no projeto o main.c, o startup.c , makefile e o stm32f411-rom.ld (linker). De forma resumida o arquivo main.c é onde tem as principais funções do programa. no arquivo Makefile, foi feito o processo de automatização do código, a fim de tornar o processo de compilação mais simples, no arquivo de startup.c visto que não possuimos um sistema operacional para realizar as seguintes operações, é feito a declaração e inicialização do Stack, declaração e inicialização da Tabela de Vetores de Interrupção, código do Reset handler, outros códigos exception handler e por fim o arquivo stm32f411-rom.ld (linker), que tem por objetivo juntar o código objeto (relocável) em um local e gerar um único arquivo executável (em posição fixa, no caso dos microcontroladores em bare metal).

