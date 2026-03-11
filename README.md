# Django Inventory Management System

## About the Project

This project is a simple **Inventory Management System built using Django and Django REST Framework**.
It allows users to manage inventory items, suppliers, and access inventory data through both a **web interface** and **RESTful API endpoints**.

The project demonstrates important backend concepts such as **CRUD operations, model relationships, API development, and Django admin management**.

---

## Tech Stack

* Python
* Django
* Django REST Framework
* SQLite
* HTML (Django Templates)

---

## Features

* Add, update, and delete inventory items
* Manage supplier information
* REST API endpoints for inventory data
* Filter inventory items using query parameters
* Django admin dashboard for easy management
* Unit tests for verifying application functionality

---

## Project Structure

```
django-inventory-management/
│
├── inventory/          # Handles inventory models, views, and templates
├── api/                # REST API endpoints and serializers
├── inventory_project/  # Main Django project settings
├── manage.py
├── requirements.txt
└── README.md
```

---

## Requirements

Make sure the following are installed on your system:

### Python

Check Python installation:

```
python --version
```

Download Python if needed:
https://www.python.org/downloads/

### Pip

Upgrade pip:

```
python -m pip install --upgrade pip
```

### Virtual Environment

Install virtualenv:

```
pip install virtualenv
```

---

## Project Setup

### 1. Clone the repository

```
git clone https://github.com/SNTejaswi/django-inventory-management.git
cd django-inventory-management
```

### 2. Create a virtual environment

```
python -m venv venv
```

### 3. Activate the virtual environment

**Windows**

```
venv\Scripts\activate
```

**macOS / Linux**

```
source venv/bin/activate
```

### 4. Install dependencies

```
pip install -r requirements.txt
```

### 5. Apply migrations

```
python manage.py makemigrations
python manage.py migrate
```

### 6. Create a superuser

```
python manage.py createsuperuser
```

---

## Running the Application

Start the development server:

```
python manage.py runserver
```

Open the application in your browser:

Main application:

```
http://localhost:8000/
```

Django admin panel:

```
http://localhost:8000/admin/
```

Use the admin panel to create, update, or delete inventory records.

---

## Models

### Supplier

Represents suppliers associated with inventory items.

Fields:

* name (CharField)

### Inventory

Represents items stored in the inventory.

Fields:

* name (CharField)
* description (CharField)
* note (TextField)
* stock (IntegerField)
* availability (BooleanField)
* supplier (ForeignKey → Supplier)

Each model includes a `__str__` method for readable object representation.

---

## API Endpoints

### Get Inventory Items

```
GET /api/inventory/
```

Returns a list of all inventory items.

Example response:

```json
[
  {
    "id": 1,
    "name": "Item 1",
    "description": "Description for Item 1",
    "note": "Note for Item 1",
    "stock": 10,
    "availability": true,
    "supplier": {
      "id": 1,
      "name": "Supplier A"
    }
  }
]
```

---

### Filter Inventory by Name

```
GET /api/inventory/?name=Item
```

Returns inventory items matching the query parameter.

---

## Testing

Run the test suite:

```
python manage.py test
```

Example test cases include:

* Checking if the inventory list page loads successfully
* Checking if the inventory detail page returns status 200
* Verifying the API inventory endpoint

---

## Future Improvements

* Add JWT authentication
* Build a React frontend dashboard
* Add stock alert notifications
* Export inventory reports
* Add pagination for API responses

---

## Contributing

Contributions are welcome.

1. Fork the repository
2. Create a new branch
3. Commit your changes
4. Submit a pull request
