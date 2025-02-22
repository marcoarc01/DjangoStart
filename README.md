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

## Iniciando

para iniciar o projeto digite:
`django-admin startproject DjangoHello`
Quando um projeto Django é criado com o comando startproject, ele cria uma pasta de contêiner. O Django coloca um script manage.py e a pasta do pacote do projeto na pasta externa.

A opção de comando startapp do script manage.py cria uma estrutura de pastas padrão para o aplicativo com esse nome.
Veja como eu crio o `DjangoApp` na pasta `DjangoHello`

`python manage.py startapp DjangoApp`

Uma pasta com o nome do aplicativo é criada dentro da pasta principal. Ela tem alguns scripts Python.

## Estrutura 
```
DjangoHello
│   db.sqlite3 
│   manage.py 
│ 
├───DjangoApp 
│   │   admin.py 
│   │   apps.py 
│   │   models.py 
│   │   tests.py 
│   │   views.py 
│   │   __init__.py 
│   │ 
│   └───migrations 
│           __init__.py 
│ 
└───DjangoHello 
    │   asgi.py 
    │   settings.py 
    │   urls.py 
    │   wsgi.py 
    │   __init__.py
```

## views.py
No Django, uma visualização é uma função definida pelo usuário que é chamada quando o despachante de URL do Django identifica a URL de solicitação do cliente e a combina com um padrão de URL definido no arquivo urls.py.

O arquivo de visualizações criado automaticamente está vazio no início.

Vamos adicionar uma função de visualização chamada index() nele, salvando o seguinte trecho.

```
from django.http import HttpResponse 
def index(request): 
    return HttpResponse("Hello, world.")
```

## urls.py
O pacote do projeto tem um arquivo com esse nome que define os padrões de URL para o projeto.

Em linhas semelhantes, o senhor precisa fornecer o mecanismo de roteamento de URL para o aplicativo.

A pasta do aplicativo não tem um arquivo com esse nome quando é criada. Por isso, você precisa criar um.

Salve o seguinte snippet como urls.py na pasta DjangoApp.

```
from django.urls import path 
from . import views 

urlpatterns = [ 
    path('', views.index, name='index'), 
]
```
Depois voce precisa atualizar a lista `urlpatterns` no urls.py da pasta do `DjangoHello` com o seguinte codigo:

```
from django.contrib import admin 
from django.urls import include, path 

urlpatterns = [ 
    path('app/', include('DjangoApp.urls')), 
    path('admin/', admin.site.urls), 
]
```
##models.py
É onde os modelos de dados do aplicativo são definidos. Por padrão, está vazio. Cada modelo é uma classe Python baseada em django.db.models.Model e será migrado para o banco de dados como uma tabela. Por enquanto, deixe o arquivo sem alterações, pois você aprenderá a trabalhar com modelos em uma etapa posterior.

## tests.py
É onde os testes para o aplicativo são escritos. Por enquanto, deixe o arquivo inalterado, sem modificá-lo.

## settings.py 
Finalizando, é preciso atualizar a lista `INSTALLED_APPS` adicionando o nome : `'DjandoApp',` no final da lista.

## Finalizando

Após realizar todas etapas acima visite o seu localhost no navegador digitando localhost:8000/app/
e verá o Hello, World escrito na pagina
