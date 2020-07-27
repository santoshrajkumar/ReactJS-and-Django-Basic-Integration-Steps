# How to Integrate React App with Django
- This repo will let you know the basic integration steps.

### 1 Download and install node.js and restart your machine to get it acvtivated.

### 2 create the react app inside the base directory. Recommended is to create the app somewhere using the following command & copy it inside the base directory of the Django App:
```command
npx create-react-app react app
```
### 3 Goto inside the directory of the reactapp and build it using the following command:
```command
npm run build
```
### 4 Changes in the setttings.py file are written below:

```python
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [
            os.path.join(BASE_DIR, 'reactapp/build'),          #This is the templates directory
        ],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]

```
```python
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'reactapp/build/static'),
]

```

### 5 changes in the urls.py file:

```python
from django.contrib import admin
from django.urls import path

from django.views.generic import TemplateView  #added line

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', TemplateView.as_view(template_name = 'index.html')), #index path
]


```

### Your react app is now integrated to the Django app. Now runserver & goto the local host address to see it.
