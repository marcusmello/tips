# Tips for Jupyter notebook

## Jupyter notebook on pipenv's kernel

1 - Installation  

    pipenv install ipykernel jupyter 
    
or  

    pipenv install --dev ipykernel jupyter   

to install a dev package  

2 - Kernel's name  

    pipenv run python -m ipykernel install --user --name=$(basename $(pwd))

3 - Launch the notebook  

    pipenv run jupyter notebook

or logging to a file, instead the terminal  

    pipenv run jupyter notebook > jupyterlog 2>&1 &

    
## Jupyter notebook on on django's kernel

1 - Installation  

    pipenv install jupyter ipython django-extensions  
    
or  

    pipenv install --dev jupyter ipython django-extensions     

to install a dev package  

2 - Declare jupyter-notebok on **settings.py**  

        INSTALLED_APPS = [
            ...
            'django_extensions',
        ]  

3 - Migrate  
    
    pipenv run python manage.py migrate

4 - Launch the notebook  

    pipenv run python manage.py shell_plus --notebook

or logging to a file, instead the terminal  

    pipenv run python manage.py shell_plus --notebook > jupyterlog 2>&1 &

### Check it out

Using it with Django 3.0, need to define on notebook:

    os.environ["DJANGO_ALLOW_ASYNC_UNSAFE"] = "true"
