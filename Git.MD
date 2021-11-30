# Credencias 

Configurando credenciais

```
$ git config --global user.name "Fulano de Tal"
$ git config --global user.email fulanodetal@exemplo.br
```
Testando Suas Configurações
```
$ git config --list
```
Listar as pastas
```
ls 
```
(voltar um diretório)
```
cd .. 
```
(nome da pasta) - criar novos diretórios/pastas
```
mkdir 
```
(Verifica o status do repositório)
```
git status 
```
(Trackear o que não foi trackeado, inserir tudo)
```
git add -A 
```
(Para commitar) / git commit -am
```
git commit -m 
```
(lista de commits)
```
git log 
```
(--soft / --mixed / --hard)
```
git reset
```
(Mudar a branch atual)
```
git checkout 
```
(Checar o que houve nas alterações) / git diff --name-only / git diff //nome do arquivo// (vê apenas a alteração feita naquele arquivo)
```
git diff 
```
```
git checkout HEAD -- "diff" //nome do arquivo// (retroceder até a posição)
```
```
git push origin
```
```
git pull origin
```

## Inicializando um repositorio 

Inicializa o versionamento no respectivo diretório:
```
git init
```
Verifica o status do repositorio:
```
git status
````
Adicionando todos os arquivos para serem commitados:
```
git add . / git add -A
```
Commitando arquivos:
```
git commit -m "Frase do que fez"
```
Visualizando relatório de commits:
```
git log // todos os commits
git log --oneline // exibe log com hash e título do commit
```
Adicionando um repositório remoto:
```
git remote add origin https://github.com/User/Repository.git
```
Enviando as modificações para o repositório remoto:
```
git push origin
```
Puxando alterações do repositório remoto:
```
git pull origin
```
Trabalhando com branches:
```
git checkout -b nome-branch
```
Aplicando merge em branches:
```
git merge nome-branch // precisa estar na branch de destino
```
Visualizando todas as branches existentes no repositório:
```
git branch
```
Deletando uma branch local:
```
git branch -D nome-branch
git branch -d nome-branch
```
Deletando uma branch remota:
```
git push origin :nome-branch
```
Deletando todas branch que não se encontram no repositório remoto:
```
git branch --merged ##
git branch -r | egrep -v -f /dev/fd/0 <(git branch -vv | grep origin | grep -v "master") | xargs git branch -d
```
Deletando todos branches no repositório local (exceto a master):
```
git branch | grep -v "master" | xargs git branch -D
```

