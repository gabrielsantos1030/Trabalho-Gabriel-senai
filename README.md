# Atividade de Versionamento Git/GitHub

## Introdução
Esta atividade tem como objetivo aplicar conceitos de controle de versão com Git e GitHub,
demonstrando a criação de repositórios locais e remotos, o rastreamento de arquivos, a criação de
branches e a resolução de conflitos durante um merge.

## Registro dos Comandos Executados
```bash
$ git config --global user.name "Gabriel Santos dos Reis"
$ git config --global user.email "gabriel@example.com"
$ mkdir atividade-versionamento
$ cd atividade-versionamento
$ git init
$ echo "<HTML>\n<HEAD><TITLE>ATIVIDADE DE VERSIONAMENTO</TITLE></HEAD>\n<BODY>\n" > index.txt
$ git status
$ git add index.txt
$ git commit -m "Primeira versão do index.txt"
$ git remote add origin https://github.com/seuusuario/atividade-versionamento.git
$ git branch -M main
$ git push -u origin main

# Criando branch feature1
$ git checkout -b feature1
$ echo "<HTML>\n<HEAD><TITLE>ATIVIDADE DE VERSIONAMENTO</TITLE></HEAD>\n<BODY>\n" > index.txt
$ git add index.txt
$ git commit -m "Alteração para GIT na branch feature1"
$ git push -u origin feature1

# Alteração na main
$ git checkout main
$ echo "<HTML>\n<HEAD><TITLE>ATIVIDADE DE VERSIONAMENTO</TITLE></HEAD>\n<BODY>\n" > index.txt
$ git add index.txt
$ git commit -m "Alteração para VERSIONAMENTO na branch main"
$ git push

# Merge e conflito
$ git merge feature1
CONFLICT (content): Merge conflict in index.txt

# Resolução do conflito (conteúdo final do arquivo)
$ git add index.txt
$ git commit -m "Resolução de conflito entre main e feature1"
$ git push

Conclusão
Durante a execução da atividade, foi possível compreender na prática a importância do controle de
versão utilizando o Git e o GitHub. A criação de branches permitiu o desenvolvimento de
alterações paralelas, enquanto o merge evidenciou a ocorrência de conflitos. A resolução manual
do conflito consolidou as duas versões em um resultado final, reforçando a relevância da
colaboração em projetos de software.
