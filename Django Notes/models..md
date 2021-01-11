# models.


# DjCom
Ecommerce website using Django

## Django reference note


                $ django-admin startproject ${ProjectName}
                $ cd ${ProjectName}
                $ python3 manage.py runserver 
                $ python3 manage.py startapp ${AppName}
                
# Models
    
Single source of truth. Instead of handling databases with bare commands. ORM(Object Relational Mapper) is used.

                class MyTable(models.Model): # inherit from models.Model
                    myField1 = models.TextField()
                    .
                    .
                    .
                    # https://docs.djangoproject.com/en/3.1/ref/models/fields/#field-types
Once Model is created Two commands are necessary

                $ python manage.py makemigrations
                $ python manage.py migrate

**makemigrations** : generate the ```SQL``` commands. It is way of propogating changes , that is made to a model. 

1. When making migrations for nth time where n != 1. There is a possiblity that new field is added. On that case , there is also a possiblity that there are data corresponding to previous set of fields(which lacks the data for our newly added field). Make migrations makes sure that , the newer field addition is accounted for previous data too.
    
        can set null= true
            models.BooleanField(null=True) # previous data will have a new Field data set as true

        or 
            models.BooleanField(default=True) # previous data will have a new BooleanField with default value of True

**migrate** : execute ```SQL``` commands


## Some Global Field Arguments ( applies to all the fields )

To apply : 

        models.${FieldType}(blank=true)

1. set ```blank=True``` : Makes the field as not required
2. set ```null=True``` : previous data will have a new field with data set as null
3. set ```default= Data``` : default data if newer one not provided 


## Adding models to admin site

`admin.py`

    from models import ${Model}
        

       admin.site.register(${Model})

