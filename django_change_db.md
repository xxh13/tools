1. python manage.py dumpdata > datadump.json
2. Change settings.py to your mysql
3. Make sure you can connect on your mysql (permissions,etc)
4. python manage.py migrate --run-syncdb
5. Exclude contentype data with this snippet

>>>from django.contrib.contenttypes.models import ContentType
>>>ContentType.objects.all().delete()
>>>quit()
6. python manage.py loaddata datadump.json
