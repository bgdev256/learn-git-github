## O que é o git?
É um sistema controle de versão
É um servidor para guardar seus códigos, é um repositório de códigos

## Para que serve o git?
- Manter histórico de alteração
- Ter controle sobre cada alteração no código
- Para que uma alteração feita por uma pessoa não prejudique a modificação que outra pessoa fez, por exemplo upar um arquivo sobre o arquivo que seu colega upou com as modificações dele, o sistema informa que existem alterações a serem baixadas!

- Serve para guardar com segurança, compartilhar com outros colaboradores, e gerenciar as diferenças versões do mesmo código.

- O git serve para trabalhar de forma mais organizada em equipe, as alterações nos arquivos são mantidos em um servidor específico para isso
- Salvar o histótico de modificações dos arquivos e ter acesso a eles posteriormente!

### COMANDO: git init
- Serve para o git passar a enxergar determinado diretório como um repositório e obeservar as mudanças nos arquivos
- Cria um repositório GIT dentro de um diretório, onde fica registrado os dados daquele arquivo, por exemplo o histórico de alterações dele.


### COMANDO: git add
> Adiciona arquivos aptos para fazer commits
- Passa a monitorar as mudanças nos arquivos
Pode ser usado de duas formas:
Um arquivo por vez: "git add nome_do_arquivo.extensão"
Todos os arquivos do diretótio: "git add ."

## O que é um commit?
> Commit é salvar um estado ou uma versão do código, de maneira a criar um histórico de alterações e um ponto de retorno caso necessário, como um checkpoint.

### COMANDO: git commit -m
> Realiza o commit
- Você está salvando o progresso do desenvolvimento, marcando um checkpoint no seu código, possibilitando que você retorne aquele ponto específico.
- "-m" Possibilita você passar uma mensagem deescritiva daquele commmit explicando o que foi modificado!

### Configuração de AUTOR:
Ver o nome do autor:
- git config user.name

Ver o email do autor:
- git config user.email

Mudar o nome e email do Autor localmente e globalmente:
- git config --local (Para o projeto em específico)
- git config --global (Máquina como um todo)

![git_config_user](img/git_config_user.png)

## Mostrar o histórico de commit

- git log
![git_log](img/git_log.png)

### Informações deste comando
- Identidade única: hash
- Bransh: Local onde está -> ???
- Autor
- Email do autor
- Data
- Descrição

#### **HASH - Identidade única de um commit**
![info_hash_git_log](img/info_hash_git_log.png)

>Usado para fazer coisas(???) vou aprender mais pra frente!

#### **BRANSH - Não sei o que é (Aprender)**
![info_bransh_git_log](img/info_bransh_git_log.png)

>Não sei para o que é usado (Aprender)
O que sei é que a primeira palavra por exemplo 'HEAD' -> está relacionado a localidade do código, mas ficou meio breve está informação!

#### **AUTHOR NAME - Nome do autor do commit**
![info_nome_git_log](img/info_nome_git_log.png)

#### **AUTHOR EMAIL - Email do autor do commit**
![info_email_git_log](img/info_email_git_log.png)

#### **DATE - Data commit**
![info_data_git_log](img/info_data_git_log.png)

#### **DESCRIPTION - Descrição**
![info_descricao_git_log](img/info_descricao_git_log.png)
>**Boa prática** explicar em breves palavras o que aquele commit é responsável de forma clara, para que qualquer leitor entenda do que se refere!

## Outros formatos de visualização de logs

### COMANDO: 'git log --oneline' (Muito utilizado)
![git_log_oneline](img/git_log_oneline.png)
>Mostra os commit em apenas uma linha, informando o começo do 'hash' e a 'descrição' apenas.

### COMANDO: 'git log -p'
![git_log_p](img/git_log_p.png)
>Mostra os commit de maneira mais detalhada, informando o que foi alterado.

### COMANDO: 'git log --help'
>Abre uma documentação de ajuda

### Outros comandos
>Acesse o link e veja alguns comandos interessantes:   
>site: https://devhints.io/git-log   
>pdf: [Git Log Cheatsheet](doc/git_log_cheatsheet.pdf)


## Não monitorar determinados arquivos ou pastas
>Nem sempre você vai querer monitorar todos os arquivos e pastas de um diretório, para isto existe uma maneira de fazer o GIT ignorar eles!

![git_ignore](img/git_ignore.png)
>Nesta image, se a pasta 'img' e os arquivos 'anotacoes.md' e 'index.html' eu quero monitorar apenas o arquivo html, para isto eu crio um arquivo chamado '.gitignore' e dentro dele, eu escrevo o nome do que eu quero que o git ignore!

### Ignorar pastas
>Para ignorar pastas você coloca o nome da pasta e uma barra na frente como na imagem: 'img/'

### Ignorar arquivos
>Para ignorar arquivos você coloca apenas o nome do arquivo como na imagem: 'anotacoes.md'

## Como aplicar?

>Para que funcione, você faz agora o commit do arquivo '.gitignore' como nas imagens a seguir:

![git_add_ignore](img/git_add_ignore.png)
![git_commit_ignore](img/git_commit_ignore.png)

## Quando fazer um commit?
>É um assunto que é discútivel! Mas um consenso é que
>### nunca se deve fazer um commit em códigos não funcionais!

### Recomendações:
>- Final do dia;
>- Pequenas alterações;
>- **Novas funcionalidades**;
>- **Bugs corrigidos**.

## REPOSITÓRIO REMOTO: Servidor de modificações
>Serve para que  você possa salvar, acessar suas alterações e compartilhar com outras pessoas. Pelo jeito a estrutura de pastas são importantes, ou não, porque você pode colocar em qualquer outro lugar o servidor, se você for fazer um servidor local, para aprendizado assim como eu, seguindo o curso, é melhor fazer uma pasta fora da pasta que está os arquivos do projeto.
Tenho a pasta CURSOGIT/ onde estava todos os arquivos, eu criei uma nova pasta, git_github/ movi todos os arquivos para ela, e criei em CURSOGIT/ uma nova pasta chamada servidor/. Veja como ficou na imagem a seguir:

![estrutura_pasta](img/estrutura_pasta.png)
> No Git:

![git_estrutura](img/git_estrutura.png)

## Criando um servidor local

> Dentro da pasta servidor, use o comando 'git init --bare'

### COMANDO: git init --bare
> Este servidor será apenas para controlar alterações, para isto é usado o parâmetro '--bare', neste repositório não vai ser possível editar arquivos, serve apenas para armazenar alterações.

![git_init_bare](img/git_init_bare.png)

> Você copia o caminho do seu repositório que esta sendo utilizado como servidor

![copy_address](img/copy_address.png)

>- Vá até o seu repositório onde está os arquivos do projeto
>- Adicione um repositório remoto

## COMANDO: git remote add 'nome' 'endereço'
![git_remote_add](img/git_remote_add.png)

>Nome do meu servidor é 'servidor_local'
![serv_name](img/serv_name.png)

>O endereço do meu servidor é 'C:/Users/bgdev/Documents/Cursos/CursoGit/servidor/'   
![serv_address](img/serv_address.png)
> Mas poderia ser qualquer outro, por exemplo:
>- Endereço IP de outro computador na rede;
>- Outra pasta da máquina local;
>- URL de outro servidor;
>- **Qualquer endereço válido para um repositório Git**.

## COMANDO: git remote
> Lista os repositórios remotos que o repositório local conhece.

![git_remote](img/git_remote.png)

## COMANDO: git remote -v
> Lista o endereço do repositório remoto.

![git_remote_v](img/git_remote_v.png)

>Informa também onde vai **BUSCAR** dados:
![git_remote_fetch](img/git_remote_fetch.png)
>E **ENVIAR** dados:
![git_remote_push](img/git_remote_push.png)

>Existe a possibilidade de **BUSCAR** de um endereço e **ENVIAR** para outro. Usadas em infraestruturas mais robustas e complexas.

## COMANDO: git clone
### Compartilhando / Trabalho em equipe
> Simulando que tenhamos que trabalhar em equipe, e compartilhar nosso projeto, criamos uma pasta dentro de CURSOGIT/, chamada user2/

>E então para que o user2 tenha o projeto para trabalhar, precisamos **CLONAR** os dados do **repositório servidor**

> Assim, vai criar dentro da pasta user2/ uma pasta chamada servidor, para renomear, é necessário apenas colocar o nome desejado na frente do endereço.

![git_clone](img/git_clone.png)

>Comando:
![comando_git_clone](img/comando_git_clone.png)
>Endereço:
![git_clone_address](img/git_clone_address.png)
>Nome da pasta em nosso repositório:
![git_clone_pasta](img/git_clone_pasta.png)

> O repositório foi clonado, mas retornou um **WARNING**, notificando que foi clonado um repositório **vazio**!
![git_clone_warning_empty](img/git_clone_warning_empty.png)


> Isso aconteceu porque adicionamos esse repositório servidor no git_github/ mas não enviamos os dados para ele!

![estado_atual](img/estado_atual.png)

## Enviar os dados para o Servidor

### COMANDO: git push

>Apenas o comando git push, não é suficente para enviar os dados, pois ainda faltam algumas informações como:
>- Para onde? Qual é o **DESTINO**?
>- De onde? Qual é a **ORIGEM**?

>#### DESTINO:
>![git_push_destino](img/git_push_destino.png)

>#### ORIGEM:
>![git_push_origem](img/git_push_origem.png)

>Com este comando enviamos todos os DADOS, CÓDIGOS E TODAS ALTERAÇÕES que fizemos até o momento para o servidor!

## Trazer os dados para o novo USUÁRIO

Quando clonamos o repositório para o user2/ renomeamos a pasta, para projeto, mas o servidor não, ele fica com outro nome:

![git_origin](img/git_origin.png)


### Renomear um ?servidor? Não sei se seria bem renomear o servidor, mas ta renomeando alguma coisa!

>**É importante os servidores terem o mesmo nome**
### COMANDO: git remote 'nome_alterar' 'nome_novo'

![git_remote_rename](img/git_remote_rename.png)

### COMANDO: git pull
>Este comando pega os dados de um repositório **REMOTO** e trás para o **LOCAL**

![git_pull](img/git_pull.png)

>#### Resultado:
>![git_pull_ls](img/git_pull_ls.png)
>O resultado não foi como esperado seguindo a trilha do curso, pois coloquei para monitorar a pasta como um todo, e acabou que eu mandei não os arquivos da pasta git_github/ mas sim os arquivos da pasta CURSOGIT/!

> O que importa é que o arquivo index foi **compartilhado**!
>![git_pull_ls2](img/git_pull_ls2.png)

![git_result](img/git_result.png)

## **PUSH = EMPURRAR** = ENVIAR AS MODIFICAÇÕES

## **PULL = PUXA** = BAIXAR AS MODIFICAÇÕES     