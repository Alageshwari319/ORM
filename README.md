# Ex02 Django ORM Web Application
# Date:20/09/2024
# AIM
To develop a Django application to store and retrieve data from a bank loan database using Object Relational Mapping(ORM).

# ENTITY RELATIONSHIP DIAGRAM

![ER diagram](https://github.com/user-attachments/assets/fc9c4ceb-c330-4999-a95b-834da7716bb7)

## DESIGN STEPS
## STEP 1:
Clone the problem from GitHub

## STEP 2:
Create a new app in Django project

## STEP 3:
Enter the code for admin.py and models.py

## STEP 4:
Execute Django admin and create details for 10 books


# PROGRAM
```
from django.contrib import admin
from .models import Loan

@admin.register(Loan)
class LoanAdmin(admin.ModelAdmin):
    list_display = ('loan_id', 'customer_name', 'loan_type', 'loan_amount', 'interest_rate', 'tenure_years', 'issue_date')
    search_fields = ('customer_name', 'loan_type')

from django.db import models

class Loan(models.Model):
    loan_id = models.AutoField(primary_key=True)  # Primary key
    customer_name = models.CharField(max_length=100)
    loan_type = models.CharField(max_length=50, choices=[
        ('personal', 'Personal Loan'),
        ('home', 'Home Loan'),
        ('education', 'Education Loan'),
        ('vehicle', 'Vehicle Loan'),
    ])
    loan_amount = models.DecimalField(max_digits=10, decimal_places=2)
    interest_rate = models.DecimalField(max_digits=5, decimal_places=2)
    tenure_years = models.IntegerField()
    issue_date = models.DateField()

    def __str__(self):
        return f"{self.customer_name} - {self.loan_id}"
```
# OUTPUT

![Screenshot (26)](https://github.com/user-attachments/assets/95f03c72-4f81-443d-ad29-b9bd95bcc52c)
![Screenshot (29)](https://github.com/user-attachments/assets/5507bc22-e959-42d2-82d3-c2582f67b062)
![Screenshot (28)](https://github.com/user-attachments/assets/f4b182bf-ad28-42be-a8df-95af445a386d)


# RESULT
Thus the program for creating a database using ORM hass been executed successfully
