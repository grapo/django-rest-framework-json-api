
# Getting Started

*Note: this package is named Django REST Framework JSON API to follow the naming
convention of other Django REST Framework packages. Since that's quite a bit
to say or type this package will be referred to as DJA elsewhere in these docs.*

By default, Django REST Framework produces a response like:
``` js
{
    "count": 20,
    "next": "http://example.com/api/1.0/identities/?page=3",
    "previous": "http://example.com/api/1.0/identities/?page=1",
    "results": [{
        "id": 3,
        "username": "john",
        "full_name": "John Coltrane"
    }]
}
```


However, for the same `identity` model in JSON API format the response should look
like the following:
``` js
{
    "links": {
        "first": "http://example.com/api/1.0/identities",
        "last": "http://example.com/api/1.0/identities?page=5",
        "next": "http://example.com/api/1.0/identities?page=3",
        "prev": "http://example.com/api/1.0/identities",
    },
    "data": [{
        "type": "identities",
        "id": 3,
        "attributes": {
            "username": "john",
            "full-name": "John Coltrane"
        }
    }],
    "meta": {
        "pagination": {
          "page": "2",
          "pages": "5",
          "count": "20"
        }
    }
}
```


## Requirements

1. Python >= 2.7
2. Django
3. Django REST Framework >= 2.4

## Installation

From PyPI

    pip install djangorestframework-jsonapi

From Source

    git clone https://github.com/django-json-api/django-rest-framework-json-api.git
    cd django-rest-framework-json-api && pip install -e .

## Running Tests

    python runtests.py

