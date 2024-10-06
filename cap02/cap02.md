# Capítulo 2: Conceitos fundamentais


## 2.1 O Kernel: o núcleo do sistema operacional

o termo *sistema operacional* é usado comumente para descrever 2 coisas:

* Todo o "pacote" contendo o software central de gerenciamento dos recursos do
  computador e todas as ferramentas de software que acompanham
* Apenas o software central de gerenciamento e alocação dos recursos do
  computador. O temo *kernel* refere-se a esta concepção e é exatamente isso o
  que queremos dizer quando falamos em sistema operacional.

#### Tarefas realizadas pelo Kernel

É possível rodar programas em um computador sem um kernel, mas o kernel fornece
uma camada para gerenciar os recursos limitados do computador. Tarefas
realizadas pelo kernel:

* **Agendamento de processos**: o Linux/UNIX é um sistema operacional
  *multitarefas* e *preemptivo*.
  * Multitarefa: múltiplos processos residem simultaneamente na memória e cada
    um recebe um pedaço do tempo de processamento da CPU
  * Preemptivo: as regras que dizem qual processo recebe o uso da CPU e por
    quanto tempo são determinadas pelo agendador de tarefas do kernel, e não
    pelos próprios processos
* **Gerenciamento de memória**: o Linux/UNIX emprega técnicas de gerenciamento
  de memória virtual para:
  * Isolar os processos entre si e do kernel
  * Manter na memória apenas as partes que o processo necessita
* **Fornecimento de um sistema de arquivos**: o kernel fornece uma imagem de um
  sistema de arquivos
* **Criação e destruição de processos**: é o kernel que carrega um programa na
  memória, fornecendo recursos (CPU, memória, acesso à arquivos, etc.). Uma
  instância de um programa em execução é chamada de processo. Quando um processo
  termina o kernel libera os recursos para uso por outros processos.
* **Acesso à dispositivos**: o kernel fornece uma interface que padroniza e
  simplifica o acesso aos dispositivos de I/O e gerencia o acesso aos
  dispositivos pelos processos
* **Rede**: o kernel envia e recebe pacotes de mensagens via rede em nome dos
  processos
* **Provisão de uma interface de programação de aplicações através de chamadas
  de sistemas**: os processos podem solicitar tarefas realizadas pelo kernel
  através de pontos de entrada conhecidos como "chamadas de sistema"

O Linux/UNIX também é multiusuário e assim o kernel também fornece ao usuário
uma abstração chamada de **computador virtual privado**, ou seja, cada usuário
pode logar no sistema e trabalhar como se o computador fosse utilizado apenas
por ele.

#### Modo/Espaço Kernel, e Modo/Espaço Usuário

Processadores modernos operam em, pelo menos, 2 modos diferentes, e instruções
de hardware permitem a troca entre um modo e outro:

* **Modo Kernel**
* **Modo Usuário**

Da mesma forma, áreas da memória virtual podem ser marcada como pertencentes ao:

* **Espaço Kernel**
* **Espaço Usuário**

Essa divisão entre modo/espaço kernel/usuário é importante pois:

* Quando a CPU está rodando em modo usuário, ela só pode acessar área de memória
  que foram marcada como espaço do usuário (se tentar acessar uma área de
  memória do espaço kernel ocorrerá uma exception de hardware)
* Quando a CPU está rodando em modo kernel, ela pode acessar áreas de memória do
  espaço kernel e do espaço usuário


#### Visão do Kernel e Visão dos Processos

Para um processo, muitas coisas ocorrem de modo assíncrono. A entrega de sinais
e a ocorrência de eventos de comunicação inter-processos (IPC) são mediados
pelo kernel e podem ocorrer a qualquer momento para um processo. Um processo não
sabe quando será removido da CPU, quais os próximos processos a serem executados
(e em que ordem). Ele não sabe onde está alocado na memória RAM, nem se está no
espaço usuário ou espaço kernel ou no swap. Não sabe onde seus arquivos estão no
disco. Um processo opera em isolamento: ele não pode se comunicar diretamente
com outros processos e, até mesmo, terminar sua própria existência. Também não
pode se comunicar de modo direto com dispositivos.

Para o Kernel, tudo é conhecido. Ele sabe tudo e controla tudo, facilitando a
vida para os processos. O Kernel decide que processo será o próximo a obter a
CPU, quando isso ocorrerá e por quanto tempo. Ele mantém estruturas de dados
contendo todas as informações sobre todos os processos em execução. Também
mantém todas as estruturas de dados de baixo nível para os dispositivos. Também
mantém todas as estruturas de dados que fazem o mapeamento entre a memória
virtual de cada processo e a memória física e o swap do computador. Toda a
comunicação entre os processos é feita através de mecanismos fornecidos pelo
kernel. O kernel cria e termina os processos, e é o responsável por fazer a
comunicação com os dispositivos de I/O, transferindo as informações de e para os
processos dos usuários.


## 2.2 O Shell

É um programa especial projetado para receber comandos do usuário e executar
respostas apropriadas em resposta a esses comandos. É comumente referido por
*interpretador de comandos*. O termo *login shell* refere-se ao processo que é
criado para executar um shell quando o usuário loga no sistema.

Nos sistemas Linux/UNIX o shell é um processo do usuário, e muitos shells
diferentes existem:

* Bourne shell (sh): o mais antigo, escrito por Steve Bourne, padrão para o UNIX
  v7.
* C shell (csh): escrito por Bill Joy em Berkeley.
* Korn shell (ksh): criado como um sucessor para o Bourne shell, por David Korn
  na AT&T
* Bourne Again shell (bash): é a reimplementação GNU do Bourne shell, por Brian
  Fox e Chet Ramey. É o shell mais usado no Linux.

Além de serem utilizado de forma interativa, também permitem a execução de
**shell scripts**, com facilidades de linguagens de programação.
