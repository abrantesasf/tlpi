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
  * 1993, 4.4BSD

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

