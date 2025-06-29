# 🏠 Airbnb-clone - Use Case Diagram

This repository contains the use case diagram for an Airbnb-inspired property rental platform. It visually maps the core actors and interactions needed to manage property listings, bookings, payments, and user management.

---

## 📌 Overview

This system allows:

- **Guests** to search for and book properties.
- **Hosts** to list and manage their properties.
- **Admins** to oversee platform operations, users, and payments.

The use case diagram helps stakeholders understand the system’s main workflows and relationships at a glance.

---

## 🗂️ Diagram Sections

### 1️⃣ Admin Dashboard

**Actors:** Admin  
**Use Cases:**

- Admin Login
- Monitor & Manage Users
- Monitor & Manage Listings
- Monitor & Manage Bookings
- Monitor & Manage Payments

**Purpose:** Provide admins with full visibility and control over all activities.

---

### 2️⃣ User Management

**Actors:** Guests, Hosts  
**Use Cases:**

- Start Registration
- Choose Role (Guest/Host)
- Account Verification
- Login (Email or OAuth)
- Update Profile Photo
- Update Contact Info
- Update Preferences

**Purpose:** Allow secure registration, login, and account management for both guests and hosts.

---

### 3️⃣ Property Listings

**Actors:** Hosts  
**Use Cases:**

- Add Listing
- Edit Listing
- Delete Listing

**Purpose:** Enable hosts to create and manage rental properties.

---

### 4️⃣ Search & Filtering

**Actors:** Guests  
**Use Cases:**

- Start Search
- Filter by Location
- Filter by Price
- Filter by Number of Guests
- Filter by Amenities
- View Listings

**Purpose:** Help guests find properties that fit their needs.

---

### 5️⃣ Booking Management

**Actors:** Guests, Hosts  
**Use Cases:**

- Start Booking
- Select Dates
- Validate Availability
- Create Booking
- Confirm Booking
- Cancel Booking
- View Booking Status

**Purpose:** Facilitate the full booking lifecycle.

---

### 6️⃣ Reviews & Ratings

**Actors:** Guests, Hosts  
**Use Cases:**

- Leave Review
- Submit Rating
- Host Responds

**Purpose:** Build trust through feedback and ratings.

---

### 7️⃣ Payments Processing

**Actors:** Guests, Hosts, External Payment Providers  
**Use Cases:**

- Initiate Payment
- Process Payment
- Initiate Payout
- Process Payout

**Purpose:** Enable secure payments for bookings and payouts to hosts.

---

### 8️⃣ Notifications & Integrations

**Actors:** System  
**Use Cases:**

- Send Email Notifications
- Send In-App Notifications
- Integrate with Payment & OAuth Providers

**Purpose:** Keep users informed and integrate with external systems.

---
