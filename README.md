# Primer ejemplo de uso de PLY
## Instalación de python
Ver los primeros minutos del siguiente [video](https://youtu.be/AdUZArA-kZw) para la instalación en windows. Para más información visita la pagina [oficial](https://www.python.org/).

## Comandos
* Instalación de flask: `pip install flask`
* Ejecución del proyecto: `python main.py`

## Instrucciones para usar ply
* Descargar el [comprimido](https://www.dabeaz.com/ply/) y descomprimir el contenido. De este solo se necesitará la carpeta 'ply'. Copiarla y pegarla en el directorio raiz del proyecto. 
* Para utilizarlo, debe especificar por medio de funciones la estructura del analizador lexico y sintactico. Apoyarse de los siguientes ejemplos: [1](https://ericknavarro.io/2020/02/10/24-Mi-primer-proyecto-utilizando-PLY/) y [2](https://ericknavarro.io/2020/03/15/26-Interprete-sencillo-utilizando-PLY/)


## Tutoriales uso de flask
* [Flask #1 - How to make websites with Python](https://youtu.be/mqhxxeeTbu0)
* [Flask #2 - HTML Templates](https://youtu.be/xIgPMguqyws)
* [Flask #3 - Adding Bootstrap and Template Inheritance](https://youtu.be/4nzI4RKwb5I)
* [Flask #4 - HTTP Methods (GET/POST) & Retrieving Form Data](https://youtu.be/9MHYHgh4jYc)

## Otra alternativa...
[Django](https://youtu.be/MbpROY52R7w)


# Desplegar aplicacion en Heroku
[Referencia](https://realpython.com/flask-by-example-part-1-project-setup/)

## Instalación de heroku-cli
Primero debes crear tu cuenta en [Heroku](https://signup.heroku.com/). Luego te indica como instalar el el cli. 

## Entorno virtual

* `python -m venv venv`
* `venv\Scripts\activate.bat`  --> ... o arrastrar el activate.bat a la consola
* `pip install flask` --> en este paso me refiero a instalar todas las dependencias faltantes. Ejecuta `python main.py` para ver todas las faltantes
* `python -m pip install gunicorn==20.0.4`  --> instalamos gunicorn. Este es un WSGI para servir nuestra aplicación.
* `python -m pip freeze > requirements.txt`  --> este comando crea el archivo con todas las dependencias
* Luego creamos el .gitignore y agregamos el nombre de los elementos a ignorar, entre ellos `venv` y `__pycache__`.
* Luego creamos un archivo llamado `Procfile`, y le añadimos `web: gunicorn main:app` para indicarle que debe de servir. En este caso busca el archivo main y el modulo app
* `git add .` para que agrege todos los cambios realizados
* `git commit -m "Add Heroku deployment files"`  confirmamos los cambios
* `heroku create ejemplo-python-201701048` con este comando se crea una aplicación en heroku. Tomar en cuenta que el nombre debe ser en minusculas. Este comando también crea un `remote` llamado heroku, que es donde vamos a publicar nuestra app. 
* `git push heroku master` Este comando lleva los cambios realizados al remoto llamado heroku
* `heroku open` para abrir tu app. 
