# Tips for Jupyter notebook

## Handling kernels

1 - Inspect kernels:

    jupyter kernelspec list

2 - Delete undesired kernel

    jupyter kernelspec uninstall <unwanted-kernel>

## Jupyter notebook with poetry's

1 - Installation  

    poetry add ipykernel jupyter   

or  (to install a dev package)  

    poetry add --dev ipykernel jupyter   

2 - Kernel's name  

> 2.1 - Bash
  
    poetry run python -m ipykernel install --user --name=$(basename $(pwd))
  
> 2.2 - Fish

    poetry run python -m ipykernel install --user --name=(basename (pwd))

3 - Launch the notebook  

    poetry run jupyter notebook

or logging to a file, instead the terminal  

    poetry run jupyter notebook > jupyterlog 2>&1 &

After 1st step, you could do:

    poetry shell

... and perform commands with no need of "poetry run".

## Jupyter notebook with pipenv

1 - Installation  

    pipenv install ipykernel jupyter 

or  (to install a dev package)  

    pipenv install --dev ipykernel jupyter   

2 - Kernel's name  

> 2.1 - Bash
  
    pipenv run python -m ipykernel install --user --name=$(basename $(pwd))
  
> 2.2 - Fish

    pipenv run python -m ipykernel install --user --name=(basename (pwd))

3 - Launch the notebook  

    pipenv run jupyter notebook

or logging to a file, instead the terminal  

    pipenv run jupyter notebook > jupyterlog 2>&1 &

After 1st step, you could do:

    pipenv shell

... and perform commands with no need of "poetry run".

## Jupyter notebook with django and virtual environment

$env could be poetry or pipenv. same environment where django and jupyter were installed.

1 - Installation  

    $env install jupyter ipython django-extensions  

or  (to install a dev package)

    $env install --dev jupyter ipython django-extensions     

2 - Declare jupyter-notebok on **settings.py**  

        INSTALLED_APPS = [
            ...
            'django_extensions',
        ]  

3 - Migrate  

    $env run python manage.py migrate

4 - Launch the notebook  

    $env run python manage.py shell_plus --notebook

or logging to a file, instead the terminal  

    $env run python manage.py shell_plus --notebook > jupyterlog 2>&1 &

### Check it out

Using it with Django 3.0, need to define on notebook:

    os.environ["DJANGO_ALLOW_ASYNC_UNSAFE"] = "true"

After 1st step, you could do:

    $env shell

... and perform commands with no need of "$env run".

## Documentation and Presentation production

[nbconvert](https://nbconvert.readthedocs.io)

## Estudar

* [ ] <https://medium.com/creditas-tech/fazendo-pull-requests-com-jupyter-notebooks-c88f52316b79>
* [ ] <https://www.datacamp.com/community/tutorials/tutorial-jupyter-notebook>
