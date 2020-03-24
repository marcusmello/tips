# Cheat Sheet Django commands  

## Check django version  

    python -m django --version

## Create project  

### With <project_name> subfolder

    django-admin startproject <project_name>  

### Without <project_name> subfolder

    django-admin startproject <project_name> .

## Create a django application

    python manage.py startapp <application>

## Jupyter notebook on Django's kernel

    pipenv install jupyter ipython django-extensions  
    
    settings.py
        
        INSTALLED_APPS = [
            ...
            'django_extensions',
        ]
    
    pipenv run python manage.py migrate

    pipenv run python manage.py shell_plus --notebook

## Found PID of a background runserver
    
    ps auxw | grep runserver

## Change ‘Django administration’ text

- Create the template
```tree
├── django_root_folder
│       └── admin
│           └── base_site.html
```

- On 'base_site.html' put this content
```html
    {% extends "admin/base.html" %}
    
    {% block title %}{{ title }} | {{ site_title|default:_('Django site admin') }}{% endblock %}
    
    {% block branding %}
    <h1 id="[YOUR_NAME_ID]"><a href="{% url 'admin:index' %}">{YOUR-WELLCOME TEXT}</a></h1>
    {% endblock %}
    
    {% block nav-global %}{% endblock %}
```
