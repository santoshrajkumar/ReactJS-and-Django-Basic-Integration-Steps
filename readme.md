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
### 4 Changes in setttings.py file are written below:

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
