# Learning log

## Step 1: Setup

### Project vs app
- **Summary:** A project is the whole site (settings and root URLs). An app is one feature area (models, admin, views, migrations).
- **Interview:** "The project is the config layer, like the server file in Express where you wire everything up. Apps are feature modules that Django finds by convention once they're in `INSTALLED_APPS`. I used one app, `events`, because all five models are closely linked."
- **Note:** In `startproject config .`, the `.` avoids the nested `config/config/` folder. In the tutorial layout the outer folder is just a container.

### INSTALLED_APPS
- **Summary:** `pip install` makes the code available. `INSTALLED_APPS` tells Django to actually load it.
- **Interview:** "Installing a package and registering it are two separate steps. Django only looks for models, admin and migrations in apps listed in `INSTALLED_APPS`, and that includes my own app. If I forget, `makemigrations` says 'No changes detected'."

### requirements.txt
- **Summary:** `pip freeze` writes every installed package with its exact version, so the environment can be rebuilt with `pip install -r requirements.txt`.
- **Interview:** "pip doesn't record dependencies automatically the way npm uses package.json, so I freeze them into `requirements.txt`. Because it pins exact versions of everything, including Django's own dependencies, it works more like a lockfile."

### Environment variables
- **Summary:** Read env vars with `os.environ.get()` in `settings.py`. A `.env` file needs a package (`python-dotenv` or `django-environ`), just like `dotenv` in Express.
- **Interview:** "In Django, all config lives in `settings.py`, so that's the one place that reads env vars. The rest of the code uses `settings.X`. Env vars are always strings, so `DEBUG` needs an explicit comparison like `== '1'`, because `'False'` is truthy."
