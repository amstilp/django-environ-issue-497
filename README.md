# django-environ-issue-497

Reproducible example for [django-environ issue #497](https://github.com/joke2k/django-environ/issues/497)

# Steps to show the bug:

```
git clone https://github.com/amstilp/django-environ-issue-497.git
cd django-environ-issue-497
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python manage.py shell
```

In the django shell:

```
from django.conf import settings
print(settings.SECRET_KEY)
```

The secret key should be `test-#secret-key-with-a-hash-in-it`, but in `settings.SECRET_KEY` it is truncated after the hash characfter to `test-`.


# Environment setup

I've seen this on both python 3.8 and 3.9. I used python 3.9 for this repo/example.
