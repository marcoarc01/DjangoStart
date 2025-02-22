# Starting with Django

Um projeto Django é um aplicativo Web que pode consistir em um ou mais submódulos chamados apps. Para começar, você precisa configurar o ambiente virtual para instalar as dependências e rodar o projeto localmente. Nesta leitura, você aprenderá sobre a estrutura do aplicativo, como criar um aplicativo e como configurar as definições do projeto para incluir o aplicativo.

## Setting up the environment

### Primeiramente, crie um ambiente virtual em sua máquina para que as dependências do projeto sejam isoladas. Inicie o terminal e entre na raiz do seu projeto. Após, execute o seguinte comando:

`python -m venv venv`

Agora, você precisa inicializar o ambiente virtual digitando: (macOS/Linux)

`source venv/bin/activate`

Assim que digitar esse comando no terminal, aparecerá um `(venv)` no início do terminal. Isso mostra que o ambiente está ativo.

### Instalando o Django

Digite o seguinte comando (quando já estiver utilizando o ambiente virtual):

`pip install django`

### Rodar o servidor local

Agora, com o ambiente configurado, rode o servidor de desenvolvimento em Django utilizando:

`python manage.py runserver`

Acesse o projeto no navegador através de [http://127.0.0.1:8000/](http://127.0.0.1:8000/).
