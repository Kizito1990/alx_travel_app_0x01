# 🛫 ALX Travel App 0x03

A Django-based travel booking application extended with **Celery** and **RabbitMQ** for background task management.  
This version introduces **asynchronous email notifications** to confirm bookings without blocking the main application flow.  

---

## 🚀 Features
- User can create and manage travel bookings.
- Booking confirmation emails are sent asynchronously using **Celery workers**.
- **RabbitMQ** is used as the message broker.
- Django REST Framework (DRF) provides API endpoints for bookings.
- Configurable email backend (console, SMTP, or third-party like Gmail/SendGrid).

---

## 📂 Project Structure
alx_travel_app_0x03/
│
├── alx_travel_app/
│ ├── init.py # Initializes Celery app
│ ├── settings.py # Django + Celery configuration
│ ├── urls.py # Project URLs
│ ├── wsgi.py
│ ├── asgi.py
│ ├── celery.py # Celery configuration file
│
├── listings/
│ ├── init.py
│ ├── models.py # Booking model
│ ├── serializers.py # Booking serializer
│ ├── views.py # Triggers Celery task on booking
│ ├── tasks.py # Celery email task
│ ├── admin.py
│ ├── apps.py
│ └── migrations/
│
├── manage.py
├── README.md
├── requirements.txt # Project dependencies

## 🛠️ Tech Stack
- **Backend Framework**: Django 5.x
- **API Framework**: Django REST Framework
- **Task Queue**: Celery 5.x
- **Broker**: RabbitMQ
- **Database**: SQLite (default, configurable)
- **Email**: Django Email Backend



📌 API Endpoints
Method	Endpoint	Description
GET	/bookings/	List all bookings
POST	/bookings/	Create a new booking
GET	/bookings/1/	Retrieve a specific booking
PUT	/bookings/1/	Update a booking
DELETE	/bookings/1/	Delete a booking