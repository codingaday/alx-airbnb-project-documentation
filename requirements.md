# 📄 Backend Requirement Specifications

This document outlines the detailed functional requirements for the **User Authentication**, **Property Management**, and **Booking System** modules. Each section includes API endpoints, input/output formats, validation rules, and performance expectations.

---

## 🔐 1. User Authentication

### 🔧 Endpoints

| Method | Endpoint            | Description                   |
| ------ | ------------------- | ----------------------------- |
| POST   | /api/auth/register/ | Register a new user           |
| POST   | /api/auth/login/    | Authenticate and return token |
| POST   | /api/auth/logout/   | Invalidate user session       |
| GET    | /api/auth/profile/  | Get logged-in user's profile  |
| PUT    | /api/auth/profile/  | Update user profile info      |

### 📥 Input Specifications

#### POST /register/

```json
{
  "email": "user@gmail.com",
  "password": "P@ssw0rd123",
  "username": "user_101"
}
```

### 📤 Output (on success)

```json
{
  "id": 1,
  "email": "user@gmail.com",
  "username": "user_101",
  "token": "jwt-token-string"
}
```

### ✅ Validation Rules

- `email`: must be unique, valid format.
- `password`: minimum 8 characters, at least one uppercase, one number.
- `username`: required, must be unique.

### ⚙️ Performance Criteria

- Authentication response within **300ms**.
- Token-based auth using JWT.
- Rate limiting (e.g., 5 login attempts per minute).

---

## 🏠 2. Property Management

### 🔧 Endpoints

| Method | Endpoint              | Description                             |
| ------ | --------------------- | --------------------------------------- |
| POST   | /api/properties/      | Create a new property listing           |
| GET    | /api/properties/      | List all properties                     |
| GET    | /api/properties/{id}/ | Retrieve details of a specific property |
| PUT    | /api/properties/{id}/ | Update an existing listing              |
| DELETE | /api/properties/{id}/ | Delete a listing                        |

### 📥 Input Specifications

#### POST /properties/

```json
{
  "title": "Modern Studio in Lagos",
  "description": "Close to the beach, WiFi included",
  "price_per_night": 50000.0,
  "location": "Lekki, Lagos",
  "images": ["image1.jpg", "image2.jpg"]
}
```

### 📤 Output (on success)

```json
{
  "id": 101,
  "host_id": 1,
  "title": "Modern Studio in Lagos",
  "location": "Lekki, Lagos",
  "price_per_night": 50000.0
}
```

### ✅ Validation Rules

- `title`: required, max 100 characters.
- `price_per_night`: must be a positive float.
- `images`: list of valid image URLs/files.

### ⚙️ Performance Criteria

- Retrieval of property listings under **500ms**.
- Support pagination and filtering by location, price, etc.
- Indexed search fields: location, price, availability.

---

## 🧾 3. Booking System

### 🔧 Endpoints

| Method | Endpoint            | Description              |
| ------ | ------------------- | ------------------------ |
| POST   | /api/bookings/      | Create a new booking     |
| GET    | /api/bookings/      | List user bookings       |
| GET    | /api/bookings/{id}/ | Retrieve booking details |
| DELETE | /api/bookings/{id}/ | Cancel/delete a booking  |

### 📥 Input Specifications

#### POST /bookings/

```json
{
  "property_id": 101,
  "check_in": "2025-07-10",
  "check_out": "2025-07-15"
}
```

### 📤 Output (on success)

```json
{
  "booking_id": 5001,
  "user_id": 1,
  "property_id": 101,
  "total_price": 250000.0,
  "status": "confirmed"
}
```

### ✅ Validation Rules

- `check_in` < `check_out`.
- Booking dates must be available.
- User cannot double-book overlapping dates.

### ⚙️ Performance Criteria

- Booking request processed in under **400ms**.
- Ensure data consistency using database transactions.
- Prevent race conditions using locking or atomicity.

---

## 🔐 Security Considerations (Applies to All Modules)

- All endpoints protected via JWT authentication.
- Sensitive fields (password, tokens) are hashed/encrypted.
- Input sanitation to prevent SQL injection or XSS attacks.
- Rate limiting for endpoints like `/login/` and `/bookings/`.

---
