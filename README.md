## Versionamento com GIT

**Git** é uma ferramenta para controle de versão (vcs: version control system).

Ele é usado em grandes projetos em empresas como Facebook, Twitter, Linkedin, Netflix e muitos outros.

![GitHub Logo](/Users/gesianesilva/Downloads/Git-Logo-2Color.png)

### Primeiros passos com o GIT

1. Instale o pacote do git:

`# apt-get install git `.

2. Crie um diretório de teste:

`# mkdir -p /root/exemplo/repo-teste && cd /root/exemplo/repo-teste `

`# git init `

**GIT init**: O comando git init inicia um repositório vazio ou reinicia um repositório já existente.

Agora vamos criar o arquivo e salvar as informações no repositório.

1. Crie o arquivo de teste.

`# vim arquivo1 `

"DevOps is everything!"

2. Adicione o arquivo na área de Staging.

`# git status `

`# git add arquivo1`

`# git status`

**GIT STATUS**:  Mostra o estado da working tree. Basicamente é usado para ver os arquivos que foram alterados. 

**GIT ADD**: Esse comando atualiza a index usando o conteúdo encontrado na Working Tree, preparando o conteúdo para o próximo commit. Ao modificar o arquivo é necessário adicionar para staging area. Ao realizar o commit o conteúdo do arquivo é salvo dentro do repositório local do GIT.

Antes de salvar as alterações, vamos configurar as informações no GIT:

`# git config --global user.name "Devops Concrete"`

`# git config --global user.email "devops@concrete.com.br"`

**GIT config**: o comando é responsável por definir configurações do repositório ou opções globais do GIT. Você pode buscar informações, definir, remover ou trocar informações de configurações.

Salvando as mudanças realizadas no arquivo:

`# git commit -m "Initial commit"`

Verificando o log de commit do projeto:

`# git log `

`# git log --oneline`

**GIT commit**
Este comando é utilizado para armazenar mudanças do repositório local do GIT. É muito comum o parâmetro *-m* ou em sua forma estendida *–message* para definir uma mensagem simples ao commit a ser realizado. Podemos verificar que essa mensagem é mostrada quando queremos visualizar o log de commits do projeto.


**GIT log**
Mostra o histórico de commit do projeto, mostrando informações como o HASH do commit, nome e e-mail do responsável, data e hora do commit e mensagem que foi armazenada no commit. Podemos utilizar *–oneline* para ocultar os metadados mostrando apenas o começo do Hash e mensagem do commit.


### Realizando rollback das mudanças

`# vim arquivo``

"LINHA DE CONFIGURAÇÃO COM ERRO"

Salve as alterações realizadas:

`# git add arquivo`

`# git commit -m "Teste de erro"`

`# git log --oneline`

`# git revert <id_commit>`

Verifique se o arquivo voltou ao seu estado anterior

`# cat arquivo`

### Trabalhando com Tags

Através de **Tags** podemos marcar pontos importantes do projeto. Normalmente as pessoas usam para marcar versões de release (v1.0, v1.1, v2.0).

1. Crie uma tag no projeto com o nome v1.0.

`# git tag -a "v1.1" -m "novo conteúdo adicionado"`

2. Liste as tags 

`# git tag`

Também podemos utilizar tags em commit já realizados anteriormente.

1. Identifique o ID do commit

`# git log --oneline`

2. Crie uma tag para o primeiro commit do projeto

`# git tag -a v1.2 <id_commit>` 

### Trabalhando com Branches

Branches ("ramos") são utilizados para fazer ramificação do projeto a partir da sua linha principal.

A Branch default do repositório é a Branch master.

Os branches podem ser mesclados (merge) uns com os outros para unificar o projeto novamente.

Vamos criar um branch testing.

1. Crie um branch de nome testing

`# git checkout ­-b testing`


2. Liste os branches do projeto.

`# git branch`


3. Salve as mudanças no novo branch.

`# echo “DevOps” >> arquivo2`

`# git add ­­--all`

`# git commit ­-m “Novo arquivo adicionado”`

### GIT checkout

O comando checkout é utilizado para você navegar entre as branches do seu projeto. Podemos usar o parãmetro -b para criar a branch caso ela não exista e transferir os arquivos atuais para a branch.

### GIT branch

O comando branch é usado para gerenciar as branches do projeto. Você pode criar, listar ou deletar branches do projeto.

Vamos mesclar o branch de testing com o master.

1. Visualize as diferenças entre os branches.

`# git checkout master`

`# ls`

2. Visualize as diferenças entre os branches.

`# git diff master testing`

3. Realize o merge entre os branches.

`# git merge testing`

`# ls`

### GIT diff

Este comando é utilizado para verificar diferenças entre arquivos, commits, entre commit e working tree, etc.

### GIT merge

O comando é utilizado para mesclar dois objetos no GIT. 

Veja mais infos na doc oficial: [GIT](https://git-scm.com/)




