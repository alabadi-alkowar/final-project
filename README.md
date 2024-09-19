# Cash control tracking finance web

## main idea :
Cash Control is a web application designed to help users manage their personal finances effectively. It allows users to track their spending and earnings, view their transaction history, and analyze their financial data through various reports and dashboards.


## How It Works

1. **Registration**: Users sign up using their email address.
2. **Main Page**: Displays recent transactions and provides a link to the Add Transaction page.
3. **Dashboard**: Shows the user's current balance and financial statistics.
4. **Add Transaction Page**: Allows users to add transactions, including both spending and earnings.



## Distinctiveness and Complexity

### Distinctiveness

This project stands out by offering comprehensive personal finance management features within a single web application. The following elements contribute to its distinctiveness:
- **Customizable Transactions**: Users can categorize transactions into various types, such as spending or earning, with dynamic category updates based on transaction types.
- **Visualizations and Reports**: Provides financial summaries, detailed reports, and visualizations to help users understand their financial status and trends.
- **User Authentication**: Includes secure user registration and login systems to ensure personalized and private financial tracking.

### Complexity

The project demonstrates technical complexity in several ways:
- **Models and Views**: The application features custom models and views to handle diverse financial transactions, including income, expenses, and other cash flow data.
- **Data Validation**: Implements complex validation logic to ensure that transaction categories match their types.
- **Dynamic Dashboards**: Utilizes aggregation and visualization techniques to present spending and earning statistics effectively.

## Technologies

- **Python**: Django Framework for backend development
- **SQLite**: Database management
- **HTML**: Structuring the web pages
- **CSS**: Styling the web pages
- **JavaScript**: Enhancing interactivity
- **Bootstrap**: Responsive design and layout
- **Django Authentication**: User authentication and management

## Project Structure

### `settings.py`
Contains the configuration settings for the Django project, including database settings, static and media file configurations, and security settings.

### `urls.py`
Defines the URL routing configuration, mapping URLs to their respective views.

### `style.css`
Contains CSS styles for various parts of the Cash Control application, ensuring a consistent and visually appealing design.

### `dashboard.html`
Provides an overview of the user's financial data, including current balance, total income and expenses, spending by category, and savings by month.

### `layout.html`
Provides a consistent layout and navigation across different pages of the site.

### `login.html` and `register.html`
Forms for user authentication and registration, respectively.

### `transaction_form.html`
Page where users can add a new transaction, including details like description, amount, date, type, and category.

### `transaction_history.html`
Displays transaction history with separate sections for spending and earning transactions.

### `transaction_list.html`
Lists all transactions for the logged-in user.

### `admin.py`
Customizes the Django admin interface for managing `Transaction` and `User` models. Includes filters, search fields, and custom display configurations.

### `forms.py`
Defines forms for handling transaction data. Includes custom validation and widgets for improved user experience.

### `models.py`
Defines the `Transaction` model with fields for storing transaction details and includes custom validation methods.

### `views.py`
Contains views for handling various aspects of the application, such as displaying transaction lists, dashboards, and handling user registration and login.

## View Descriptions

### `transaction_list`
- **Purpose**: Displays a list of transactions for the logged-in user.
- **Logic**: Filters transactions based on the current user and renders them in the `transaction_list.html` template.
- **Decorator**: `@login_required` ensures only logged-in users can access this view.

### `dashboard`
- **Purpose**: Shows an overview of spending and earning statistics.
- **Logic**: 
  - Aggregates spending by category and earnings by month.
  - Serializes data to JSON for use in JavaScript.
  - Calculates total income, total expenses, and current balance.
  - Logs the data for debugging purposes.
  - Renders the dashboard in the `dashboard.html` template.
- **Decorator**: `@login_required`.

### `transaction_history`
- **Purpose**: Displays a history of transactions, separated into spending and earning.
- **Logic**:
  - Fetches and orders transactions by date.
  - Filters transactions into spending and earning categories.
  - Renders the history in the `transaction_history.html` template.
- **Decorator**: `@login_required`.

### `add_transaction`
- **Purpose**: Handles the addition of a new transaction.
- **Logic**:
  - If the request method is POST, it validates and saves the transaction form.
  - If the request method is GET, it displays a blank transaction form.
  - Redirects to the dashboard after saving a transaction.
  - Renders the form in the `transaction_form.html` template.
- **Decorator**: `@login_required`.

### `register`
- **Purpose**: Handles user registration.
- **Logic**:
  - Processes POST requests to create a new user if passwords match and the username is unique.
  - Logs in the user after successful registration.
  - Handles errors related to password mismatch or username conflicts.
  - Renders the registration form or displays error messages.
- **Template**: `register.html`.

### `logout_view`
- **Purpose**: Logs out the user and redirects them.
- **Logic**:
  - Logs out the user and redirects to the dashboard.
  - Uses the `reverse` function to generate the URL for the redirect.
- **Decorator**: `@login_required`.

### `login_view`
- **Purpose**: Handles user login.
- **Logic**:
  - Processes POST requests to authenticate the user.
  - Redirects to the transaction list if authentication is successful.
  - Displays an error message if authentication fails.
  - Renders the login form or displays error messages.
- **Template**: `login.html`.


## Installation

1. **Create a Virtual Environment and Install Requirements**
   ```bash
   py -m venv env
   pip install -r requirements.txt
### 2. Make and apply the migrations by running

```bash
python manage.py makemigrations
python manage.py migrate

### 3. Create a superuser

```bash
python manage.py createsuperuser

## 4.Run the server.
```bash
` Python manage.py runserver`

- Create an account, and then you will be taken to the main page.















