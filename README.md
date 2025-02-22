# Starting with Django

Um projeto Django é um aplicativo Web que pode consistir em um ou mais submódulos chamados apps.
Para começar, você precisa configurar o ambiente virtual para instalar as dependências e rodar o projeto localmente.
Nesta leitura, você aprenderá sobre a estrutura do aplicativo, como criar um aplicativo e como configurar as definições do projeto para incluir o aplicativo.

## Setting up the environment

### Primeiramente, crie um ambiente virtual em sua maquina para que as dependência do projeto sejam isoladas.
Inicie o terminal e entre na raiz do seu projeto, apos, execute o seguinte comando: 

'''python -m venv venv

Agora, você precisa inicializar o ambiente virtual digitando:
(macOS/linux)
'source venv/bin/activate'

assim que digitar esse comando no terminal aparecera um (venv) no inicio do terminal, isso mostra que o ambiente esta ativo

### Instalando o django

digite o seguinte comando (quando ja estiver utilizando o ambiente virtual):
'''pip install django

### rodar o servidor local

agora com o ambiente configurado, rode o servidor de desenvolvimento em django utilizando:

'''python manage.py runserver

Acesse o projeto no navegador através de http://127.0.0.1:8000/.
