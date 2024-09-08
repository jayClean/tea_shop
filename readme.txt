# Tea Shop

## Overview

The Tea Shop project is a Django-based web application designed to manage and display various tea products. It includes features for product management, user authentication, and order processing, with integration for Stripe payments, RabbitMQ message brokering, and Celery for asynchronous tasks.

## Features

- User registration and authentication
- Product catalog with detailed information
- Shopping cart functionality
- Order management and processing
- Stripe integration for payment processing
- Asynchronous task handling with Celery
- Message brokering with RabbitMQ
- Admin interface for managing products and orders

## Prerequisites

- Python 3.8 or higher
- Django 4.0 or higher
- SQLite (or any other supported database)
- RabbitMQ server
- Redis server (if used with Celery)

## Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/jayClean/tea_shop.git
   ```

2. **Navigate to the Project Directory**

   ```bash
   cd tea_shop
   ```

3. **Create a Virtual Environment**

   ```bash
   python -m venv venv
   ```

4. **Activate the Virtual Environment**

   - **On Windows:**

     ```bash
     venv\Scripts\activate
     ```

   - **On macOS/Linux:**

     ```bash
     source venv/bin/activate
     ```

5. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

6. **Set Up Environment Variables**

   Create a `.env` file in the root directory and add your environment-specific settings. For example:

   ```env
   SECRET_KEY=your-secret-key
   DEBUG=True
   DATABASE_URL=sqlite:///db.sqlite3
   STRIPE_TEST_KEY=your-stripe-test-key
   STRIPE_LIVE_KEY=your-stripe-live-key
   CELERY_BROKER_URL=amqp://localhost
   CELERY_RESULT_BACKEND=redis://localhost:6379/0
   ```

7. **Run Migrations**

   ```bash
   python manage.py migrate
   ```

8. **Create a Superuser (Admin)**

   ```bash
   python manage.py createsuperuser
   ```

9. **Run the Development Server**

   ```bash
   python manage.py runserver
   ```

   The application will be available at `http://127.0.0.1:8000/`.

10. **Start RabbitMQ and Redis**

    Make sure RabbitMQ and Redis servers are running. You can start them with the following commands:

    - **RabbitMQ:**

      ```bash
      rabbitmq-server
      ```

    - **Redis:**

      ```bash
      redis-server
      ```

11. **Start Celery Worker**

    In a new terminal, activate your virtual environment and start the Celery worker:

    ```bash
    celery -A tea_shop worker -l info
    ```

## Usage

- **User Registration:** Navigate to the registration page to create a new account.
- **Product Browsing:** Browse the product catalog to view available teas.
- **Shopping Cart:** Add products to the cart and proceed to checkout.
- **Payment:** Use Stripe to process payments for orders.
- **Admin Interface:** Access the admin interface at `http://127.0.0.1:8000/admin` to manage products and orders.
- **Async Tasks:** Celery handles background tasks like sending emails or processing payments.

## Contributing

1. **Fork the Repository**
2. **Create a New Branch**

   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make Changes and Commit**

   ```bash
   git add .
   git commit -m "Add your commit message"
   ```

4. **Push to Your Fork**

   ```bash
   git push origin feature/your-feature-name
   ```

5. **Create a Pull Request**

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For any questions or issues, please contact:

- **Name:** Jay Clean
- **Email:** [jayclean@example.com](mailto:jayclean@example.com)
- **GitHub:** [jayClean](https://github.com/jayClean)
