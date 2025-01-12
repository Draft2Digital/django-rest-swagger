# Django REST Swagger

How to Make New Release (D2D Version)
-------------------------------------
Update version in `rest_framework_swagger/__init__.py` by changing the last number to be one greater. Example, change

```__version__ = "v2.2.0+d2d.001"```

to

```__version__ = "v2.2.0+d2d.002"```

Commit and push changes, then go to https://github.com/Draft2Digital/django-rest-swagger/releases and click Draft a new release.

Click Choose a tag and put in the same version as is the value in the `__version__` variable (e.g. `v2.2.0+d2d.004`). Publish the release.

In projects that use this, update the version pointed at to be the new version.

[![build-status-badge]][build-status]
[![codecov](https://codecov.io/gh/marcgibbons/django-rest-swagger/branch/master/graph/badge.svg)](https://codecov.io/gh/marcgibbons/django-rest-swagger)
[![pypi-version]][pypi]
[![Dependency Status](https://www.versioneye.com/user/projects/579cb582aa78d50051183c0e/badge.svg?style=flat-square)](https://www.versioneye.com/user/projects/579cb582aa78d50051183c0e)


[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)


#### An API documentation generator for Swagger UI and Django REST Framework

Full documentation: http://marcgibbons.github.io/django-rest-swagger/


## Installation

1. `pip install django-rest-swagger`

2. Add `rest_framework_swagger` to your `INSTALLED_APPS` setting:

    ```python
        INSTALLED_APPS = (
            ...
            'rest_framework_swagger',
        )
    ```

## Rendering Swagger Specification and Documentation

This package ships with two renderer classes:

1. `OpenAPIRenderer` generates the OpenAPI (fka Swagger) JSON schema specification. This renderer will be presented if:
  -  `Content-Type: application/openapi+json` is specified in the headers.
  - `?format=openapi` is passed as query param
2. `SwaggerUIRenderer` generates the Swagger UI and requires the `OpenAPIRenderer`


### Quick Start Example:
```python
from django.conf.urls import url
from rest_framework_swagger.views import get_swagger_view

schema_view = get_swagger_view(title='Pastebin API')

urlpatterns = [
    url(r'^$', schema_view)
]
```

## Requirements
* Django 1.8+
* Django REST framework 3.5.1+
* Python 2.7, 3.5, 3.6


## Testing

- Run `$ tox` to execute the test suite against all supported environments.
- Run `./runtests.py` to run the test suite within the current environment.

## Bugs & Contributions
Please report bugs by opening an issue

Contributions are welcome and are encouraged!

## Special Thanks
Many thanks to Tom Christie & all the contributors who have developed [Django REST Framework](http://django-rest-framework.org/)


[build-status-badge]: https://travis-ci.org/marcgibbons/django-rest-swagger.svg?branch=master
[build-status]: https://travis-ci.org/marcgibbons/django-rest-swagger
[pypi-version]: https://img.shields.io/pypi/v/django-rest-swagger.svg
[pypi]: https://pypi.python.org/pypi/django-rest-swagger
[license]: https://pypi.python.org/pypi/django-rest-swagger/
[docs-badge]: https://readthedocs.io/projects/django-rest-swagger/badge/
[docs]: http://django-rest-swagger.readthedocs.io/
