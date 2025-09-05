# Atividade de Versionamento Git/GitHub

## Introdução
Esta atividade tem como objetivo aplicar conceitos de controle de versão com Git e GitHub,
demonstrando a criação de repositórios locais e remotos, rastreamento de arquivos, criação de
branches, merge e resolução de conflitos.

## Registro dos Comandos Executados
```bash
# Configuração do usuário Git
git config --global user.name "Gabriel Santos dos Reis"
git config --global user.email "gabriel@example.com"

# Criar pasta e repositório local
mkdir atividade-versionamento
cd atividade-versionamento
git init

# Criar arquivo index.txt inicial
echo "<HTML>
<HEAD><TITLE>ATIVIDADE DE VERSIONAMENTO</TITLE></HEAD>
<BODY>
<H1> TÍTULO1 </H1>
</BODY>
</HTML>" > index.txt

# Verificar status e adicionar arquivo
git status
git add index.txt

# Primeiro commit
git commit -m "Primeira versão do index.txt"

# Conectar ao repositório remoto no GitHub
git remote add origin https://github.com/seuusuario/atividade-versionamento.git
git branch -M main
git push -u origin main

# Criar branch feature1
git checkout -b feature1

# Alterar index.txt na branch feature1
echo "<HTML>
<HEAD><TITLE>ATIVIDADE DE VERSIONAMENTO</TITLE></HEAD>
<BODY>
<H1> GIT </H1>
</BODY>
</HTML>" > index.txt

# Adicionar e commitar alterações na feature1
git add index.txt
git commit -m "Alteração para GIT na branch feature1"
git push -u origin feature1

# Voltar para a branch main
git checkout main

# Alterar index.txt na branch main
echo "<HTML>
<HEAD><TITLE>ATIVIDADE DE VERSIONAMENTO</TITLE></HEAD>
<BODY>
<H1> VERSIONAMENTO </H1>
</BODY>
</HTML>" > index.txt

# Adicionar e commitar alterações na main
git add index.txt
git commit -m "Alteração para VERSIONAMENTO na branch main"
git push

# Merge da branch feature1 na main
git merge feature1
# Aqui ocorrerá conflito
# Resolução manual do conflito no index.txt:
echo "<HTML>
<HEAD><TITLE>ATIVIDADE DE VERSIONAMENTO</TITLE></HEAD>
<BODY>
<H1> VERSIONAMENTO E GIT </H1>
</BODY>
</HTML>" > index.txt

# Adicionar e commitar resolução do conflito
git add index.txt
git commit -m "Resolução de conflito entre main e feature1"
git push
