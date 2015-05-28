# Django REST Framework MongoDB Filters

## Installation

Clone the project from github.

```
git clone git@github.com:theofilis/djangorestframework-mongo-filters.git
```

## Example

```python
from django.contrib.auth.models import User
from myapp.serializers import UserSerializer
from rest_framework_mongo_filter import filters
from rest_framework import generics


class UserListView(generics.ListAPIView):
    queryset = User.objects.all()
    serializer = UserSerializer
    filter_backends = (filters.SearchFilter,)
    search_fields = ('username', 'email')

```