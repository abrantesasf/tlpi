# Capítulo 1: história e padrões

* Desenvolvimento não foi controlado por um único fornecedor ou
  organização. Permitiu inovação, mas implementação divergiram causando
  problemas de portabilidade.
* Termos:
  * UNIX: denomina sistemas operacionais que passaram nos tetes de conformidade
    do The Open Group (que é a dona da marca UNIX) e, assim, ganharam o direito
    de serem nomeados Sistemas UNIX. O teste verifica a conformidade com o
    "_Single UNIX Specification_".
  * Unix: denomina sistemas operacionais que se parecem e se comportam como os
    sistemas UNIX clássicos, mas que não passaram (ou que não querem passar)
    pelos testes do The Open Group. Aqui estão as implementações livres, como o
    Linux e o FreeBSD).


## 1.1 Breve história do UNIX e C

* Pré-releases:
  * 1969: assembly em PDP-7
  * 1970: assembly em PDP-11
* Releases:
  * 1971 (novembro), UNIX v1: assembly em PDP-11. Tinha compilador FORTRAN e
    diversos utilitários (ar, cat, chmod, chown, cp, dc, ed, find, ln, ln, mail,
    mkdir, mv, rm, sh, su, who)
  * 1972 (junho), UNIX v2: instalado em 10 máquinas
  * 1973 (fevereiro), UNIX v3: tinha compilador C e pipes. Grande parte do
    código já em C, mas ainda muito assembly
  * 1973 (novembro), UNIX v4: primeira versão escrita quase totalmente em C
  * 1974 (junho), UNIX v5: instalado em mais de 50 máquinas. Começa
    licenciamento por taxa nominal para universidades, junto com documentação e
    código fonte (AT&T proibida de comercializar)
  * 1975 (maio), UNIX v6: aumento do licenciamento nominal para universidades,
    primeira versão a ser utilizada amplamente fora da AT&T.
* Universidade da Califórnia em Berkeley:
  * 1975/1976: Ken Thompson passa 1 ano em Berkeley e, junto com vários
    estudantes, adiciona muitas funcionalidades ao sistema (C shell, vi,
    sendmail, compilador Pascal, gerenciamento de memória virtual). Um dos
    estudantes, Bill Joy, funda a Sun Microsystems.
  * Berkeley Software Distribution (BSD):
    * BSD e 2BSD incluíram essas novas funcionalidades e ferramentas, mas não
      eram sistemas completos.
* Divergência de sistemas:
  * 1979 (janeiro), UNIX v7: incluiu as novas funcionalidades e criou outras
    (awk, make, sed, tar, uucp, Bourne shell)
  * 1979 (dezembro), 3BSD: primeira distribuição Unix completa de Berkeley,
    iniciando a divergência como UNIX original.
  * 1981: monopólio da AT&T foi quebrado, permitindo que a AT&T comercializasse
    software
  * 1981, System III: UNIX comercial da AT&T, baseado no UNIX v7
  * 1983, 4.2BSD: implementação TCP/IP, sockets e diversas ferramentas de rede
  * 1983, SunOS: baseado no 4.2BSD
  * 1983, System V: UNIX comercial da AT&T
  * 1989, System V Release 4 (SVR4): UNIX comercial da AT&T, que incluiu muitas
    funcionalidades de rede do BSD. Foi licenciado para outros fornecedores para
    a criação de outras versões UNIX.
  * 1986, 4.3BSD
  * 1991, BSD Net/2: uma versão baseada no 4.3BSD sem nenhum código proprietário
    da AT&T.
  * 1992, 386/BSD: uma versão do BSD Net/2 portado para a arquitetura
    x86-32. Não foi continuado, mas deu origem ao NetBSD e ao FreeBSD.
  * 1992, BSD/OS: uma versão baseada no BSD Net/2 e no 386/BSD que a Berkeley
    Software Design (da universidade da califórnia) estava licenciando e
    vendendo, com binário, fontes e suporte. Foi processada pelo UNIX System
    Laboratories (USL), da AT&T, sob alegação de que continha código
    proprietário da AT&T. A Universidade da Califórnia contra-processou dizendo
    que o System V não tinha dado crédito ao código que o BSD criou.
  * 1993, NetBSD: uma adaptação do 386/BSD que enfatizou a portabilidade para
    diversos hardwares.
  * 1993, FreeBSD: adaptação do 386/BSD que enfatizou performance, e foi o mais
    difundido dentre todos os BSD.
  * 1993, 4.4BSD
  * 1994: acordo entre a USL e a Univ. da Califórnia a respeito do código do
    BSD: a universidade removeu 3 arquivos do código do BSD Net/2, fez algumas
    mudanças menores em outros arquivos e incluiu avisos de copyright da AT&T em
    uns 70 outros arquivos. Em troca poderia continuar distribuindo
    comercialmente.
  * 1994, 4.4BSD-Lite: foi a versão após o acordo com a AT&T.
  * 1995, 4.4BSD-Lite Release 2 foi lançado; FreeBSD e NetBSD também alteraram a
    base do código para o 4.4BSD-Lite, tirando o BSD Net/2 de sua base (e assim,
    também tirando o código da AT&T)
  * 1996, OpenBSD: um fork do NetBSD que enfatizou a segurança.
  * 2003, Dragonfly BSD: baseado no FreeBSD, enfatizava SMP.

No final da década de 80 e início da década de 90 temos assim 2 grandes "ramos"
de sistemas UNIX: System V e BSD. Esses dois grandes sistemas UNIX foram
distribuídos e licenciados para diversos fornecedores, que criaram vários e
vários sistemas UNIX específicos (SunOS/Solaris, Digital Ultrix, HP Tru74 UNIX,
IBM AIX, HP-UX, NeXT, Apple A/UX, MS-XENIX, etc). Isso teve vantagens e
desvantagens:

* Vantagens:
  * Inovação
  * Facilitou troca de hardware
* Desvantagens:
  * Portabilidade
  * Sistemas agora eram proprietários


## 1.2 Breve história do Linux

* 1984, Richard Stallman: inicia esforços para criar um UNIX livre e inicia o
  projeto GNU: GNU is not UNIX
* 1985, Richard Stallman: funda a Free Software Foundation (FSF) para suportar o
  projeto GNU e desenvolver software livre em geral.
* 1989: Surge a GPL: General Public License
* 1990: GNU tinha produzido quase tudo o que um sistema precisaria (Emacs, GCC,
  bash, glibc, etc.), menos um kernel (estava previsto o GNU/HURD como kernel)
* 1991: Linux Torvalds começou a criar um kernel UNIX e divulgou em 1991-10-05 a
  versão 0.02 e solicitou ajuda.
* 1994: Linux 1.0 liberado ao público
* 1995: Linux 1.2 liberado ao público
* 1996: Linux 2.0 liberado ao público
* 1999: Linux 2.2 liberado ao público
* 2001: Linux 2.4 liberado ao público
* 2003: Linux 2.6 liberado ao público

Implementação inicial era focado no Intel 80386, mais do que portabilidade. Com
a divulgação e uso em massa, portabilidade para outras arquiteturas começaram:
Digital Alpha, x86-64, PowerPC, SPARC e SPARC64, MIPS, ARM, zSeries, Intel
IA-64, etc.

Precisamente o Linux é apenas o kernel. Informalmente é o kernel para os outros
softwares que formam um sistema completo. Fornecedores começaram a criar as
distribuições Linux para facilitar a instalação para os usuários.


## 1.3 Padronização

No final da década de 1980 e início da década de 1990 havia uma ampla variedade
de sistemas UNIX, alguns baseados no BSD, outros baseados no System V, e outros
ainda com características dos dois sistemas. Cada fornecedor também incluía
outras funcionalidades em seus sistemas, causando problemas de
portabilidade. Isso iniciou uma pressão enorme para a padronização da linguagem
C e também do próprio sistema UNIX.


### 1.3.1 Padronização da linguagem C

Os esforços de padronização da C na década de 1980 resultaram no padrão C89, que
descrevia a sintaxe e a semântica de C e a biblioteca C padrão. Os padrões C são
independentes de sistema operacional, o que significa que um programa C escrito
apenas com a biblioteca C padrão pode ser portado para qualquer outro sistema
que fornecesse uma implementação C.


### 1.3.2 Os padrões POSIX

Com a padronização da C, a pressão para a padronização do UNIX aumentou e o IEEE
lançou o padrão POSIX (Portable Operating System Interface), para promover a
portabilidade das aplicações em nível de código fonte. Isso garantiria uma
interface padrão para o UNIX, facilitando a portabilidade de aplicações.

* 1988/1990, POSIX.1 (POSIX 1003.1): documenta a API de serviços que um sistema
  operacional conforme deveria fornecer para os programas. É baseado nas
  chamadas de sistemas UNIX e na API da biblioteca de funções de C, mas poderia
  ser implementado por qualquer sistema operacional, não especificamente um
  UNIX. Foi aumentado por extensões:
  * 1993, POSIX.1b (POSIX 1003.1b): extensões para tempo real, sincronização de
    arquivos, I/O assíncrono, agendamento de processos, relógios e timers de
    alta precisão, e comunicação inter-processos utilizando semáforos, memória
    compartilhada e fila de mensagens.
  * 1995, POSIX.1c (POSIX 1003.1c): extensões para threads
  * ????, POSIX.1g (POSIX 1003.1g): extensões para APIs de rede e sockets.
  * 2999, POSIX.1d (POSIX 1003.1d): extensões adicionais para realtime
* 1992, POSIX.2: padronizou o shell e diversos utilitários UNIX, incluindo a
  interface de linha de comando para o compilador C.
