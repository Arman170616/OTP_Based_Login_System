
# OTP Based Login System

This project is a Django-based login system that uses One-Time Passwords (OTP) for user authentication via mobile phone numbers. The OTPs are sent through SMS using Twilio, adding a layer of security to the login process by verifying users with a unique code.

## Table of Contents

- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Environment Variables](#environment-variables)
- [Usage](#usage) 
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Features

- Mobile phone-based login system with OTP verification
- OTPs sent directly to the user’s mobile number via Twilio SMS
- Simple and user-friendly authentication flow

## Technologies Used

- **Django**: Backend framework for building the web application
- **Twilio**: Service used for sending OTPs via SMS
- **SQLite**: Database used for development (can be swapped for a different DB in production)

## Getting Started

These instructions will help you set up the project locally for development and testing.

### Prerequisites

Ensure you have the following installed:

- Python 3.8+
- Django 3.0+
- Twilio account with API credentials

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Arman170616/OTP_Based_Login_System.git
   cd OTP_Based_Login_System
   ```

2. **Set up a virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # For Windows, use `venv\Scripts\activate`
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

### Environment Variables

Create a `.env` file in the root directory and add the following environment variables:

```plaintext
TWILIO_ACCOUNT_SID=your_twilio_account_sid
TWILIO_AUTH_TOKEN=your_twilio_auth_token
TWILIO_VERIFY_SERVICE_SID=your_twilio_verify_service_sid
```

Replace `your_twilio_account_sid`, `your_twilio_auth_token`, and `your_twilio_verify_service_sid` with your Twilio credentials.

### Database Setup

Run migrations to set up the database:

```bash
python manage.py migrate
```

Create a superuser if needed for admin access:

```bash
python manage.py createsuperuser
```

## Usage

1. **Start the development server**:
   ```bash
   python manage.py runserver
   ```

2. **Request OTP**: Users can enter their mobile number on the login page to request an OTP.

3. **Verify OTP**: Users will receive an OTP via SMS and can enter it to complete the login process.

## Testing the OTP System

### Request OTP

To request an OTP, access the `request_otp_login` endpoint with the phone number as a query parameter:

```bash
GET /accounts/request-otp-login/?phone_number=+8801811302984
```

This will trigger the OTP SMS to be sent to the phone number.

### Verify OTP

After receiving the OTP on your phone, go to the `verify_otp_login` endpoint and provide the phone number and OTP as query parameters:

```bash
GET /accounts/verify-otp-login/?phone_number=+8801811302984&otp_code=123456
```

If the OTP matches, you’ll receive a "Login successful" message; otherwise, an error response.

This setup should handle OTP-based login using mobile numbers with Twilio in Django!
## Contributing

To contribute to this project:

1. Fork the repository.
2. Create a new feature branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to your branch (`git push origin feature/your-feature`).
5. Open a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Contact

For any inquiries, reach out:

- **Author**: Arman
- **Email**: [armanicepust9@gmail.com](mailto:armanicepust9@gmail.com)

Project Link: [https://github.com/Arman170616/OTP_Based_Login_System](https://github.com/Arman170616/OTP_Based_Login_System)

--- 
