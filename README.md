# Configuração inicial do Git
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

# Conectar repositório local ao remoto
git remote add origin https://github.com/seuusuario/atividade-versionamento.git
git remote -v   # listar conexões remotas

# Publicar na branch main
git branch -M main
git push -u origin main

# Criar uma nova branch feature1
git checkout -b feature1

# Alterar index.txt na branch feature1
echo "<HTML>
<HEAD><TITLE>ATIVIDADE DE VERSIONAMENTO</TITLE></HEAD>
<BODY>
   <H1> GIT </H1>
</BODY>
</HTML>" > index.txt

# Adicionar e commitar na feature1
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

# Adicionar e commitar na main
git add index.txt
git commit -m "Alteração para VERSIONAMENTO na branch main"
git push

# Buscar atualizações do repositório remoto (simulando outro programador)
git pull origin main

# Fazer merge da branch feature1 na main
git merge feature1
# -> Conflito será detectado

# Resolver conflito manualmente no index.txt:
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
