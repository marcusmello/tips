# Tips for Jupyter notebook

## Jupyter notebook on pipenv's kernel

1 - Installation
    pipenv install ipykernel jupyter 
    
ou  
    pipenv install --dev ipykernel jupyter to install a dev package  

2 - Kernel's name
    pipenv run python -m ipykernel install --user --name=$(basename $(pwd))

3 - Launch the notebook, logging to a file, instead the terminal
    pipenv run jupyter notebook > jupyterlog 2>&1 &
  
    

    
## Jupyter notebook on on django's kernel

    pipenv install jupyter ipython django-extensions  
    
    settings.py
        
        INSTALLED_APPS = [
            ...
            'django_extensions',
        ]
    
    pipenv run python manage.py migrate

    pipenv run python manage.py shell_plus --notebook

### Observação

Ao usar o Django 3.0, é preciso definor no jupter:

    os.environ["DJANGO_ALLOW_ASYNC_UNSAFE"] = "true"
