- [x] Update HISTORY
- [x] Update README and check formatting with http://rst.ninjs.org/
- [x] Make sure any new files are included in MANIFEST.in
- [x] Update version number in `explorer/__init__.py`
- [x] Update any package dependencies in `setup.py`
- [x] Commit the changes:
```
git add .
git commit -m "Release 1.0.0"
```

- [x] Build & test the source distribution:
```
python setup.py build
mktmpenv
cd django-sql-explorer
cd dist
tar xzvf django-sql-explorer-x.x.tar.gz
cd django-sql-explorer-x.x/
python setup.py install
python -m django startproject explorertest
cd explorertest/explorertest/
emacs urls.py
>> from django.urls import path, include
>> path('explorer/', include('explorer.urls')),
emacs settings.py
>> add 'explorer' to installed apps
>> EXPLORER_CONNECTIONS = {'Default': 'default'}
>> EXPLORER_DEFAULT_CONNECTION = 'default'
cd..
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
>> log in and try it! http://127.0.0.1:8000/explorer/
deactivate
```

- [x] Release on PyPI:
```
python setup.py release
```

- [x] Test that it pip installs:
```
mktmpenv
pip install my_project
deactivate
```

- [x] Tag the last git commit with the version number:
```
python setup.py tag
```

  Put the same message as in HISTORY.rst.
- [x] Push: `git push`
- [x] Push tags: `git push --tags`
- [x] Check the PyPI listing page (https://pypi.python.org/pypi/django-sql-explorer) to make sure that the README, release notes display properly.
