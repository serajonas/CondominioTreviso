### Condominio Treviso
# Condominio Treviso
<!---Esses são exemplos. Veja https://shields.io para outras pessoas ou para personalizar este conjunto de escudos. Você pode querer incluir dependências, status do projeto e informações de licença aqui--->
![Python](https://img.shields.io/badge/Python-14354C?style=for-the-badge&logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
<br>
<img src="logo.png" alt="Logo do Condominio Treviso">
> Uma aplicação web de condominio chamada CondominioTreviso desenvolvida durante o curso de Python no Senac Americana. A aplicação listará condominio e clicando em cada nome de receita você pode ver a receita completa.
### Lista de tarefas
Segue a lista de tarefas a serem desenvolvidas no projeto:
- [X] Pré-requisitos
    - [X] Instalar o Python
    - [X] Instalar Visual Studio Code
- [X] Criar e ativar o ambiente virtual
```
python -m venv .\venv\
venv\Scripts\activate
```
- [X] Instalar o Django
```
python -m pip install django==3.2
```
- [X] Criar o projeto CondominioTreviso
```
django-admin.py startproject CondominioTrevisoProject CondominioTrevisoProj
```
- [X] Subir o servidor e testar o projeto
```
entrar na pasta do projeto
cd CondominioTrevisoProj
executar o projeto no servidor
python manage.py runserver
```
- [X] Alterar o idioma do projeto para `pt-br`
    - Abrir o arquivo `settings.py` e na linha 106 trocar `en-us` para `pt-br`
- [X] Alterar o timezone do projeto para `America/Sao_Paulo`
- [X] Criar o app condominio
```
* preciso estar dentro da pasta do projeto (CondominioTrevisoProj)
python manage.py startapp condominio
```
- [X] Registrar o app condominio
```
no arquivo settings.py adicionar o app condominio na lista de apps 
INSTALLED_APPS[
    ...
    'condominio',
]
```
- [X] Configurar a rota inicial(index)
    - Dentro da pasta condominio(app) criar o arquivo `urls.py`
    - no arquivo `urls.py` 
        ```python
            from django.urls import path
            from . import views
            urlpatterns = [
                path('', views.index, name='index')
            ]
        ```
- [X] Criar a view para a rota inicial
    - Dentro da pasta condominio(app) abrir o arquivo `views.py` 
    ```python
        from django.shortcuts import render
        from django.http import HttpResponse
        def index(request):
            return HttpResponse("<h1>Seja bem vindo</h1>")
    ```
- [X] Registrar a rota inicial
    - Dentro da pasta CondominioTrevisoProj(app) abrir o arquivo `urls.py`
    ```python
    from django.contrib import admin
    from django.urls import path, include
    urlpatterns = [
        path('admin/', admin.site.urls),
        path('',include('condominio.urls')),
    ]
    ```
- [ ] Criar o arquivo index.html

## 📝 Licença
Esse projeto está sob licença. Veja o arquivo [LICENÇA](LICENSE.md) para mais detalhes.
[⬆ Voltar ao topo](#nome-do-projeto)<br>
