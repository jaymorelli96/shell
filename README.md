## Jean Morelli

# **Shell cheatsheet** 

### man

​	Formatação e exibição do manual pages

 * Input

   ```$ man man```

* Output

  ```man - format and display the on-line manual pages ...```

  

### info

​	Se comporta como ```man``` command, é um comando mais novo com alguns “features” a mais.

* Input

  ```$ info id```

* Output

  ```´id´: Print user indentity...```



### id

​	Escreve a indentidade do usuario, pode ser passado certos argumentos que são opcionais.

* Input

  `$ id jeanmorelli` onde jay é o usuário.

* Output

  ```uid=501(jeanmorelli) gid=20(staff) groups=20(staff),501(access_bpf),12(everyone),61(localaccounts),79(_appserverusr),80(admin),81(_appserveradm),98(_lpadmin),701(com.apple.sharepoint.group.1),33(_appstore),100(_lpoperator),204(_developer),250(_analyticsusers),395(com.apple.access_ftp),398(com.apple.access_screensharing),399(com.apple.access_ssh),400(com.apple.access_remote_ae)```




### whoami

​	É o equivalente do commando `id -un`, escreve o nome do atual usuário.

* Input

  `$ whom`

* Output

  `jean morelli`



### who

​	Escreve informações sobre o usuário que esta logado no momento.

* Input

  `$ who`

* Output

  ```aa
  jeanmorelli console  Feb 10 22:03
  jeanmorelli ttys000  Feb 11 17:59
  ```



### tty

​	Escreve o nome do dispositivo do terminal, é para o uso de shell scripting e para comandos que precisam de informação do dispositivo

* Input

  `$ tty`

* Output

  `/dev/ttys000`



### finger  \<user>

​	Escreve informação sobre o sistema do usurário.

* Input

  `$ finger jeanmorelli`

* Output

  ```
  Login: jeanmorelli    			Name: jean morelli
  Directory: /Users/jeanmorelli       	Shell: /bin/zsh
  On since Mon Feb 10 22:03 (WET) on console, idle 20:55 (messages off)
  On since Tue Feb 11 17:59 (WET) on ttys000
  No Mail.
  No Plan.
  ```



### last

​	Lista as sessões de certos usuários, cada linha contem o nome do usuário, o tty, tempo da sessão entre outras coisas.

 * Input 

   `$ last`

* Output

  ```jeanmorelli  ttys000   Tue Feb 11 17:59   still logged in ```



### date

​	Escreve a data  e hora atual

 * Input

   `$ date`

* Output

  `Tue Feb 11 19:06:03 WET 2020`

  

### time \<command>

​	Escreve o tempo que levou um comando a ser executado

* Input

  `$ time info`

* Output

  `info  0.00s user 0.01s system 0% cpu 11.853 total`



### passwd

​	Quando o comando é executado, faz um prompt para mudar a senha de um dado usuário.

 * Input 

   `$ passed`

* Output

  ```a 
  Changing password for jeanmorelli.
  Old Password:
  New Password:
  Retype New Password:
  ```

  

### echo \<argument>

​	Escreve uma linha de texto

* Input

  `$ echo Hello World!`

* Output

  `Hello World!`



### mesg

​	Permite ou não permite mandar mensagem para outro usuário.

 * Input

   `$ mesg`

* Output

  `is Y`



### mail e/ou mailx

​	Envia e recebe emails

* Input

  `$ mail`

* Output

  ```
  mail jeanmorelli
  Subject: test
  Testando!
  EOT
  ```



### su

​	Substitui a identidade do usuário, deixando o usuário como outro durante sua sessão 

 * Input

   `$ su`

* Output

  ```
  Password:
  ```



### bc

​	Calculadora básica do terminal

* Input

  `$ bc`

* Output

  ```
  bc 1.06
  Copyright 1991-1994, 1997, 1998, 2000 Free Software Foundation, Inc.
  This is free software with ABSOLUTELY NO WARRANTY.
  For details type `warranty'.
  3 + 2
  5
  
  ```



### cal

# 

​	Abre o calendario do mes atual

* Input

  `$ cal`

* Out

  ```
     February 2020
  Su Mo Tu We Th Fr Sa
                     1
   2  3  4  5  6  7  8
   9 10 11 12 13 14 15
  16 17 18 19 20 21 22
  23 24 25 26 27 28 29
  ```



### clear

​	Limpa o terminal

 * Input 

   `$ clear`

* Output

  ```
  $
  
  
  ```

  

### ps

​	Escreve as informações dos processos que estão sendo executados no momento

* Input

  `$ ps`

* Output

  ```
  PID TTY           TIME CMD
  18985 ttys000    0:00.03 /Applications/iTerm.app/Contents/MacOS/iTerm2 --server login -fp jeanmorelli
  18987 ttys000    0:05.15 -zsh
  23006 ttys000    0:00.00 mail jeanmorelli
  ```

  



### jobs

​	Escreve os jobs em execução (Built in command)

* Input

  `$ jobs`

* Output

  `[1]  + suspended  mail jeanmorelli`



### \<Ctrl> \<z>

​	Suspende o processo mais recente do "foreground". O ultimo processo a ser interagido com o tty



### bg \<pid>

​	Retoma jobs suspenso para o "background", o identificador é o id

* Input 

  `$ bg 1`

* Output

  ```
  [1]  + 34927 continued  mail jeanmorelli
  (continue)
  [1]  + 34927 suspended (tty input)  mail jeanmorelli
  ```

#### 



### bg \<jobid>

​	Retoma jobs suspenso para o "background", o identificador é o nome do processo

* Input 

  `$ bg mail`

* Output

  ```
  [1]  + 34927 continued  mail jeanmorelli
  (continue)
  [1]  + 34927 suspended (tty input)  mail jeanmorelli
  ```

  

### fg \<pid>

​	Retoma jobs suspenso para o "foreground"

* Input

  `$ fg mail`

* Output

  ```
  [1]  + 34927 continued  mail jeanmorelli
  (continue)
  
  
  
  
  ```

  

### fg \<jobid>

Retoma jobs suspenso para o "foreground"

* Input

  `$ fg mail`

* Output

  ```
  [1]  + 34927 continued  mail jeanmorelli
  (continue)
  
  
  
  
  
  ```

  

​	



## Comandos para manipulação de ficheiros e directórios



### pwd

​	Escreve o path do directório atual

* Input

  `$ pwd`

* Output

  `/Users/jeanmorelli/Documents/Programming`



### ls

​	Faz uma lista de conteúdo que fazem parte do directório atual

* Input

  `$ ls`

* Output

  ```
  C          Dev        Processing WebDev
  Coursera   FlutterDev Python     flutter
  Dart       IDE        Terminal
  ```



### cd

​	Muda de directório para o path indicado

* Input

  `$ cd FlutterDev`

* Output após commando `pwd`

  `/Users/jeanmorelli/Documents/Programming/FlutterDev`



### find

Comando find, recursivamente "anda" pela árvore de directórios a procura de certo arquivo ou directório.

* Input 

  `$ find OneDrive`

* Output

  ```
  onedrive
  onedrive/Icon
  onedrive/.849C9593-D756-4E56-8D6E-42412F2A707B
  ```



### locate

​	Locate comando, procura na base de dados para todos os pathnames que fazem "match" com um  "pattern" especifico. Funciona mais ou menos como o find, mas é mais rápido que o find.

* Input

  `$ locate *dir2*`

* Output

  `/example-dir2.c`



### mkdir e rmdir

​	Mkdir serve para a criação de directórios enquanto o rmdir serve para remover.

* Input 

  `$ mkdir dir1`

  `$ rmdir dir2`

* Output após comando `ls`

  `dir1`



### chmod 

​	Modificação de permissões de arquivos, conhecido como "Change Mode".

* Input

  `chmod 0 file1.txt`

* Output após `$ ls -l`

  ```
  ----------   1 jeanmorelli  staff     0 Feb 11 22:13 file1.txt
  ```



### cat

​	Junta e escreve arquivos



* Input e Output

  `$ cat file1` Vai escrever os conteúdos do arquivo para o output padrão

  `$ cat file1 file2 > file3` Vai escrever os conteúdos de file1 e file2 no file3



### more e less

​	`	less` pode ser usado para leitura de arquivos que ocupem mais de uma tela, permite fazer um rolamento na pagina. Possível "descer" e "subir".

`		more` pode ser usado para leitura de arquivos que ocupem mais de uma tela. Possível somente "descer" a pagina.



### cut

​	Faz o "cut" de certa parte de cada linha do arquivo.

* Input

  `cut -c3 example.txt`

* Output

  ```
  a
  b
  c
  ```

* `$ cat example.txt`

  ```
  zzazz
  zzbzz
  zzczz
  ```

  

### vi

​	Texto Editor Vim



### head \<filename>

​	Escreve as primeiras linhas de um arquivo

* Input

  ```
  $ touch file1.txt
  $ vim file1.txt
  $ head -n 1 file1.txt
  ```

* Output

  ```
  test first line
  ```



### tail \<filename>

​	Escreve as últimas linhas de um arquivo

* Input

  `$ tail -n 1 file1.txt`

* Output

  `test last line`



### ln 

​	Cria um link para um arquivo, fazendo uma copia deste arquivo como um outro nome desejado.

* Input 

  `$ ln file1.txt f1`

* Output

  `$ test first line`



### cp

​	Copia um arquivo para o outro desejado

* Input

  ```
  $ cp file1.txt file2.txt
  $ head -n 1 file2.txt
  ```

* Output

  `test first line`



### mv

​	Move arquivos para outros directórios

* Input

  ```
  $ mv file2.txt bash
  $ cd bash && ls
  ```

  

* Output

  ```
  file2.txt
  ```



### rm

​	Remove um directório ou arquivo desejado.

* Input

  `$ rm file2.txt && ls`

* Output

  ```
  $
  ```



### umask

​	Desliga permissão de escrita para outros usuários

* Input

  `$ umask 002`

* Output

  Permissão de arquivos `-rw-rw-r--`

  

### file

​	Escreve o nome do arquivo que foi passado como argumento e uma breve descrição do mesmo.

* Input

  `$ file file2.txt`

* Output

  `file2.txt: ASCII text`



### wc

​	Se uma opção não for selecionada, escreve o número de linhas do arquivos, o número de palavras e por fim o número de caracteres.

* Input

  `$ wc file2.txt`

* Output

  `2       3      17 file2.txt`



### split

Divide um arquivo em pedaços	

* Input

  `$ split file2.txt && ls`

* Output

  `file2.txt xaa`



### grep \<expressão> \<ficheiro>

​	Um "pattern search" de arquivo. Procura qualquer arquivo dado como input, selecionando linhas que fazem match. Usado com regex.

* Input

  `$ grep 'test' file2.txt`

* Output

  **`test `** `first line`



### sort

Faz um sorte de um desejado arquivo

* Input

  ```
  $ head sort.txt
  > 2
  	3
  	4
  	1
  	0
  $ sort sort.txt
  ```

* Output

  ```
  0
  1
  2
  3
  4
  ```



### diff

​	Faz uma comparação de arquivos linha por linha. Escreve as linhas que são diferentes

* Input 

  `$ diff sort.txt sort2.txt`

* Output

  ```
  4c4
  < 1
  ---
  > 8
  ```



### compress

​	"Compress" arquivos 

* Input

  `$ compress sort.txt`

* Output

  Arquivo comprimido



### uncompress 

 	Faz o "uncompress" de arquivos.

* Input

  `$ uncompress xaa.z`

* Output

  Arquivo uncompressed



### chgrp

​	Muda o grupo ID de um arquivo.

* Input

  `$ chgrp staff sort.txt && ls -l ` 

* Output

  ```
  -rw-r--r--  1 jeanmorelli  staff  12 Feb 12 10:45 file2.txt
  -rw-------  1 jeanmorelli  staff  11 Feb 12 10:42 sort.txt
  -rw-------  1 jeanmorelli  staff  11 Feb 12 10:49 sort2.txt
  -rw-------  1 jeanmorelli  staff  17 Feb 12 10:24 xaa
  ```



### chown

​	Muda owner de um arquivo.

* Input

  `$ chown jeanmorelli sort.txt`

* Output

  ```
  -rw-r--r--  1 jeanmorelli  staff  12 Feb 12 10:45 file2.txt
  -rw-------  1 jeanmorelli  staff  11 Feb 12 10:42 sort.txt
  -rw-------  1 jeanmorelli  staff  11 Feb 12 10:49 sort2.txt
  -rw-------  1 jeanmorelli  staff  17 Feb 12 10:24 xaa
  ```

  

### df e du

​	Escreve as estatísticas sobre a quantidade de espaço livre no disco (df)

O `du` escreve as estatísticas do uso do disco.

* Input

  `$ df`

* Output

  ```
  Filesystem    512-blocks      Used Available Capacity iused      ifree %iused  Mounted on
  /dev/disk1s5   489620264  21445888 122195232    15%  484108 2447617212    0%   /
  devfs                680       680         0   100%    1179          0  100%   /dev
  /dev/disk1s1   489620264 336126872 122195232    74% 1667442 2446433878    0%   /System/Volumes/Data
  /dev/disk1s4   489620264   8390776 122195232     7%       5 2448101315    0%   /private/var/vm
  map auto_home          0         0         0   100%       0          0  100%   /System/Volumes/Data/home
  /dev/disk1s3   489620264   1032224 122195232     1%      36 2448101284    0%   /Volumes/Recovery
  ```

  

### mount

Adiciona um arquivo em seu path temporariamente para ser utilizado com o find por exemplo

* Sintaxe

  `mount -t type device dir`



### umount

Faz o "umount", retira o arquivo que foi adicionado em seu path

* Sintaxe

  `umount [options] filesystem`





## Variáveis e Operadores



* Representa o número de argumentos passados ao programa: **$#**
* Referencia todos os parâmetros posicionais: **$**
* Representa o nome do programa ou script a ser executado: **$0**
* Representa o número do processo a ser executado: **$$**
* Representa o número do último processo executado em segundo plano: **$!**
* Representa o estado do último comando não executado em segundo plano: **$?**



​	**Operadores Lógicos**

* AND: **-a**
* OR: **-o**
* NOT: **!**
* Menor do que: **-lt**
* Menor ou igual a: **-le**
* Igual a: **-eq**
* Maior do que: **-gt**
* Maior ou igual a: **-ge**
* Diferente: **-ne**



​	**Manipulação de Strings**

* Iguais: **str1 == str2**
* Diferentes: **str1 != str2**
* De comprimento maior que zero: **-n string**
* De comprimento igual a zero: **-z string**



​	**Manipulação de ficheiros**

* É um directório: **-d dir**
* É um ficheiro regular: **-f**
* É um ficheiro com permissão de leitura: **-r**
* É um ficheiro com permissão de escrita: **-w**
* É um ficheiro com permissão de execução: **-x**
* É um ficheiro com conteúdo: **-s**
* É um ficheiro do utilizador actual:  **-O**
* É um ficheiro do grupo actual: **-G**
* É um pipe: **-p**
* É mais recente: **file -nt file2**
* É mais antigo: **file -ot file2**



	## Estruturas de controlo de execução em "bash"

**1)**

* Sintaxe da estrutura `if`

  ```bash
  if list; then list; [elif list; then list] ... [else list;] fi
  ```

  

* Exemplo de sua utilização

  ```bash
  if[str1 -e str2]; then
  	echo "It is equal!"
  ```



**2)**

* Sintaxe da estrutura `for`

  ```bash
  for name [in word]; do list; done	
  ```

* Exemplo de sua utilização

  ```bash
  i=1
  for i in 1 2 3 4 5
  do
          echo " -> $i "
  done
  ```



**3)**

 * Sintaxe da estrutura `case`

   ```bash
   case word in [ [(] pattern [ | pattern ] ... ) list ;; ] ... esac
   ```

* Exemplo de sua utilização

  ```bash
  case $curso in
          law)
                  echo "Not a geek!"
                  ;;
          CS)
                  echo "You are a geek!"
                  ;;
          *)
                  echo "Dont know about you"
                  ;;
  esac
  ```



**4)**

 * Sintaxe da estrutura `while`

   ```bash
   while list; do list; done
   ```

* Exemplo de sua utilização

  ```bash
  i=0
  while [ $i -lt 3 ]; do
          echo "$i"
          i=$(($i+1))
  done
  ```

  

**5)**

 * Sintaxe da estrutura `until`

   ```bash
   until list; do list; done
   ```

* Exemplo de sua utilização

  ```bash
  i=0
  until [ $i -eq 3 ];
  do
          echo "$i"
          i=$(($i+1))
  done
  ```



