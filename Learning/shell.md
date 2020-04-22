# Aprendizados Básicos de Linux (Comandos) :books:

__Criando áreas de trabalho (WorkSpace):__
```
$ Super + Shift + Page Down
$ Super + Shift + Page Up 
```

__Navegando entre as áreas de trabalho (WorkSpace):__
```
$ Super + Page Down 
$ Super + Page Up 
```

__Maximizar App aberto usando:__
```
$ Super + Seta Cima 
```

__Desmaximizar App aberto usando:__
```
$ Super + Seta Baixo 
```

__Ajustar App aberto a Direita da tela usando:__
```
$ Super + Seta Direita 
```

__Ajustar App aberto a Esquerda da tela usando:__
```
$ Super + Seta Esquerda 
```

__Descobrindo nome do Usuário:__
```
$ whoami
```

__Descobrindo qual diretório estamos:__
```
$ pwd
```

__Se estivermos em um determinado diretório e desejamos retornar ao HOME:__
```
$ cd $HOME
 ou 
$ cd ~
```

__Para mais informações sobre o diretório HOME use:__
```
$ echo $HOME
 ou
$ echo ~ 
```
_Desta forma ele expandira o diretório HOME._

___Observações_ sobre Diretórios:__

_O ```.``` representa o diretório atual;_
_O ```..``` representa o diretório anterior;_
_O comando ```$ ls``` lista os diretórios existentes;_
_O comando ```$ ls -l``` lista os diretórios existentes com informações sobre os mesmos;_
_O comando ```$ ls -la``` lista os diretórios existentes com informações sobre os mesmos (informações de acesso), é diretórios 'escondidos/ocultos' onde o nome do mesmo e antecedido por '.' - Ex.: ```.meu_diretorio_econdido```, o comando ```ctrl + h``` revela todos os diretórios 'escondidos/ocultos';_

__Criando arquivos:__
```
$ touch
```
__O comando ```$ touch``` 'toca o arquivo' em determinado diretório, ou seja:__
- _Se já existir ele irá atualizar a data e a hora do mesmo;_
- _Se não existir ele irá criar o arquivo;_

___Liks Simbólicos_ são atalhos para determinados aquivos__
_Tais arquivos se encontram geralmente no diretório ```$ cd /boot```_

#### Sobre determinados _diretórios_:
  - O ```$ cd /boot``` e onde se encontra o próprio Kernel do Linux;
  - O ```$ cd /dev``` veremos todos os dispositivos ligados na máquina em questão. O comando ```$ df -h``` lista os dispositivos que estão montados, e seus pontos de montagem;
  - O ```$ cd /boot``` e onde se encontra o próprio Kernel do Linux;
  - O ```$ cd /root``` e onde se encontra o diretório do administrador;
  - O ```$ cd /opt``` e são instalados alguns softwares de fora;
  - O ```$ cd /sbin``` e onde se encontra muito dos binários do S.O.;
  - O ```$ cd /bin``` e onde se encontra outros softwares do Linux;
  - O ```$ cd /usr``` e onde se encontra os softwares que o usuário instala;
  - O ```$ cd /var``` e onde se encontra dados variados;
  - O ```$ cd /tmp``` e onde se encontra arquivos temporários do S.O. bom lugar para criar arquivos de teste, pois o S.O. não garante que o mesmo estará la depois do proximo 'boot'.

__O comando ```$ ps``` 'lista' o pid dos processos em execução:__
_Podemos usar o comando: ```$ cd /proc/pid``` e logo após o ```$ ls``` que listaremos vários pseudo arquivos. Também podemos usar o comando: ```$ less nome_do_pseudo_arquivo``` para visualizarmos o mesmo._

#### Misturando _comandos_:
_Vamos 'criar/tocar' um arquivo com o comando: ```$ touch arq.txt``` no diretório: ```$ cd /tmp```, logo após vamos usar o comando: ```$ echo "Um texto qualquer" > arq.txt``` o comando 'echo' serve para escrever qualquer coisa no _stdout_ (standart output) do própio __shell__, já o símbolo __'>'__ significa que estamos conectando o __stdout__ com o arquivo que criamos anteriormente, então esté texto será jogado no arquivo que criado._

- ```$ cd /tmp``` para navegar até o diretório desejado;
- ```$ touch arq.txt``` nesse caso se não existir crie o arquivo com o nome passado;
- ```$ echo "Um texto qualquer" > arq.txt``` escreva o texto no arquivo criado anteriormente.
- O comando: ```$ cat arq.txt``` serve para concatenar arquivos mas também serve para ver o que tem dentro do mesmo, (evite usar esse comando para arquivos grande, o mesmo precisa puxar tudo em memória antes de mostra-lo);
- O comando: ```$ more arq.txt``` é semelhante ao comando 'cat', esté comando serve para mostrar arquivos com porte maior de conteúdo, Ex.: ```$ ps aux``` irá listar todos os precessos incluindo os que o usuário não iniciou mas dessa forma temos que usar o _scroll_ para navegarmos entre as informações... Se usarmos o comando: __```$ ps aux | more```__ teremos a apresentação da informações em blocos. Só que mesmo com o comando 'more' as informações precisam ser carregadas na memória antes de serem apresentadas;
- Na pratica para resolvermos esse problema de carregar arquivos grandes... usamos o comando __```$ ps aux | less```__ esse comando usa __streams__ para carregar pedaços do arquivo, ou seja ao invés de carregar tudo na memória, ele vai puxando do stream só o que precisa para apresentar um bloco. Neste caso ainda ganamhos alguns poderes a mais, tais como:
  
  - As teclas ```j``` e ```k``` para navegarmos no arquivo;
  - As teclas ```j = 5``` irá descer 5 linhas e ```k = 7``` irá subir 7 linhas no arquivo;
  -  As teclas ```gg``` para voltar ao topo do arquivo, e ```G``` para o fim do arquivo;
  - Se digitarmos ```/informacao``` essa palavra sera destacada, e podemos usar a tecla ``n``` para irmos navegando nas pesquisa;
  - E a tecla ```q``` para parar/sair.

_Todo texto que for redigido ao __arq.txt__ usando o precedimento (anterior) acima irá sobreescrever o texto já existente, é não adiciona-lo ao mesmo, para tal feito podemos utilizar a estratégia a seguir:_

- ```$ echo "Outro texto qualquer" >> arq.txt``` escreva o texto no arquivo criado anteriormente sem sobreescrever o que já se encontra no mesmo.

#### PROCURE PELA DOCUMENTAÇÃO ATUALIZADA PARA REALIZAR A INSTALAÇÃO DE FORMA CORRETA, A INTENÇãO AQUI E SÓ MOSTRAR O PRECEDIMENTO, POR ISSO OS COMANDO QUE USEI AQUI NO DOCUMENTO COMO UM TODO PODEM ESTAR DESATUALIZADOS.


# ASDF-VM Ambientes de Desenvolvimento

_Idéia de termos vários ambientes de desenvolvimento em cima de variáveis do shell, nós possibilita termos várias verções de uma mesma tecnologia em um determinado Host._

#### Instalação:

```
	$ git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.7.8

	$ git clone https://github.com/asdf-vm/asdf.git ~/.asdf
	$ cd ~/.asdf
	$ git checkout "$(git describe --abbrev=0 --tags)"
```

_Persistindo no .bashrc:_

```
	 $ . $HOME/.asdf/asdf.sh
     $ echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.bashrc
     $ echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.bashrc

``` 

_Se o procedimento ocorreu de forma correta o comando ```$ asdf``` estará disponivel, instale os plugins (que são a grosso modo como um super-set) de cada linguagem. Ex.: ``` $ asdf plugin-add nodejs https://github.com/asdf-vm/asdf-nodejs.git``` serve o nodeJS._

#### Comando ASDF:
	- O ```$ asdf plugin-list``` irá listar todas os plugins intalados no seu Host;
	- O ```$ asdf list-all nome da linguagem (plugin)``` irá listar todas as versões 				  disponíveis do mesmo;
	- O ```$ asdf install 'plugin' 1.0.0``` irá instalar plugins na versão passada;
	- O ```$ asdf global 'plugin' 1.0.0``` irá tornar essa versão do plugins uma versão 			  universal do Host;
	- O ```$ asdf plugin-update --all``` irá atualizar todos os plugins intalados no seu Host;
	- O ```$ asdf update ``` irá atualizar o asdf;
	

# Docker instalação

_Breve intalação e configuração do Docker;_


#### Instalação:
	- O ```$ sudo apt-get remove docker docker-engine docker.io containerd runc ``` removerá qualquer versão do Docker já existente ;
	- O ```$ sudo apt-get update``` atualize seus repósitorios;
	- O ```$ sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent   			  software-properties-common ``` instalação de alguns pacotes de dependências;
	- O ```$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -``` 		  adicionar a key;
	- O ```$ sudo apt-key fingerprint 0EBFCD88 ``` adicionar a key;
	- O ```$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/			  ubuntu \
      $(lsb_release -cs) \
      stable" ``` adicione o repositório;
	- O ```$ sudo apt-get update ``` atualize o mesmo;
	- O ```$ sudo apt-get install docker-ce docker-ce-cli containerd.io``` instale o Docker;
	- O ```$ sudo wget https://github.com/bcicen/ctop/releases/download/v0.7.3/ctop-0.7.3-			  linux-amd64 -O /usr/local/bin/ctop``` FERRAMENTA CTOP para regerencia de containers;
	- O ```$ sudo chmod +x /usr/local/bin/ctop``` permissões da ferramenta;
		- O comando ```$ sudo ctop``` estará disponivel;
	- O ```$ sudo usermod -aG docker $USER``` ira confirugara regras de __user__ do docker._
	
# Geração de chave SSH (TOME CUIDADO COM SUA CHAVE PRIVADA NÃO COMPARTILHE A MESMA COM NINGUÉM)

_Se você não entende o siginificado do mesmo indico fortemente a estudar sobre o assunto ante de continuar com a geração da Key;_

__Criando arquivos:__
```
$ ssh-keygen -o -a 100 -t  ed25519 -f ~/.ssh/id_ed25519 -C "seu email"
$ eval "$(ssh-agent -s)"

```
_A pasta com a doc. com o par de key's se encontra no diretório: ```$ ls ~/.ssh``` faça bom uso e toma cuidado, não compartilhe sua chave privada, faça backup da mesma_
__Adicione a Key:__
```
$ ssh-add ~/.ssh/id_da_key_privada
```
_para facilitar a indentificação adicionei a minha key privada_