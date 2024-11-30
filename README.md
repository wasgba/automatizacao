#!/bin/bash

# Solicita o nome do novo repositório
echo "Qual o nome do seu repositório?"
read repositorio

# Pergunta para o usuário se o repositório foi criado no GitHub
echo "Por favor, crie um repositório no GitHub com o nome '$repositorio'."
echo "Depois, digite 'yes' se o repositório foi criado ou 'no' para sair."

# Aguarda a resposta do usuário
read resposta

if [ "$resposta" == "yes" ]; then
    # Cria a pasta do projeto e entra nela
    mkdir -p ~/meu_projetos/"$repositorio"
    cd ~/meu_projetos/"$repositorio"
    
    # Inicializa o repositório Git
    git init
    
    # Cria um arquivo de exemplo
    echo "# $repositorio" > README.md

    # Solicita o link do repositório no GitHub (exemplo: https://github.com/wasgba/nome-do-repositorio.git)
    echo "Por favor, informe o link do seu repositório no GitHub (exemplo: https://github.com/wasgba/$repositorio.git):"
    read link_repositorio
    
    # Adiciona o repositório remoto do GitHub
    git remote add origin "$link_repositorio"
    
    # Adiciona os arquivos ao repositório local
    git add .
    
    # Faz o primeiro commit
    git commit -m "Primeiro repositório criado com a automatização"
    
    # Envia para o GitHub
    git push -u origin main
    echo "Repositório '$repositorio' foi configurado e enviado para o GitHub com sucesso!"
else
    echo "Operação cancelada. O repositório não foi criado."
fi
  

<!-- manual de uso do script
O script pede o nome do repositório.
O script pergunta se o repositório foi criado no GitHub.
Se o repositório foi criado, o script:
Cria a pasta do projeto.
Inicializa o repositório Git.
Cria o arquivo README.md.
Solicita o link do repositório GitHub.
Adiciona o repositório remoto com o link fornecido.
Faz o primeiro commit e envia os arquivos para o GitHub.
Se o repositório não foi criado, o script cancela a operação.
-->
# bom dia 