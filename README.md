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
    
    # Adiciona o repositório remoto
    git remote add origin git@github.com:wasgba/"$repositorio".git
    
    # Adiciona os arquivos e faz o primeiro commit
    git add .
    git commit -m "Primeiro repositório criado com a automatização"
    
    # Faz o push para o repositório no GitHub
    git push -u origin main
    
    echo "Repositório '$repositorio' foi configurado e enviado para o GitHub com sucesso!"
else
    echo "Operação cancelada. O repositório não foi criado."
fi
Solicitação do nome do repositório: O script pede para o usuário digitar o nome do repositório que deseja criar.

Orientação para criar o repositório no GitHub: Ele instrui o usuário a ir até o GitHub e criar o repositório manualmente com o nome fornecido.

Confirmar se o repositório foi criado: O script pergunta se o repositório foi criado no GitHub. Se o usuário digitar yes, ele prossegue com a criação do repositório local e o envio para o GitHub. Caso contrário, ele informa que a operação foi cancelada.

Criação do repositório local e envio para o GitHub: Se o repositório foi criado, o script faz o seguinte:

Cria a pasta do repositório localmente.
Inicializa o repositório Git com git init.
Cria um arquivo README.md com o nome do repositório.
Adiciona o repositório remoto com a URL do GitHub.
Faz o commit inicial e envia os arquivos para o GitHub com git push.