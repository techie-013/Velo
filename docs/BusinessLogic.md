# VELO Business Logic

**Version:** MVP v1.0

**Last Updated:** 24 July 2026

---

# Overview

This document defines the business rules and workflows for the VELO MVP.

It serves as the single source of truth for both frontend and backend development. Any feature implementation must follow the rules defined in this document.

---

# 1. MVP Scope

## Objective

Develop a Minimum Viable Product (MVP) of VELO that enables students to rent bicycles inside the university campus through a web application.

The MVP is intended to validate customer demand and operational feasibility before investing in IoT smart locks, GPS tracking, EV fleet management, and a dedicated mobile application.

---

## Features Included

### Authentication

- Google Login
- Student Registration
- Student ID Verification
- User Session Management

### Dashboard

- View Available Cycles
- Cycle Status
- Pricing
- Guidelines
- Pickup Locations

### Booking

- Select Cycle
- Select Pickup Location
- Select Date
- Select Time Slot
- Booking Summary

### Payment

- Razorpay Test Mode Integration
- Payment Verification
- Booking Confirmation

### Ride

- Display Lock Combination
- Start Ride
- End Ride
- Select Drop Location

### Ride History

- Previous Rides
- Ride Duration
- Payment Details

### Feedback

- Rating
- Comments

### Admin Dashboard

- Manage Users
- Manage Cycles
- View Bookings
- View Revenue
- View Ride History
- Manage Lock Codes

---

# Out of Scope (Future Versions)

The following features are intentionally excluded from the MVP:

- IoT Smart Locks
- QR Unlock
- Bluetooth Unlock
- GPS Tracking
- Live Cycle Tracking
- Wallet System
- Subscription Plans
- Referral Program
- Mobile Application
- Notifications
- EV Charging Management
- AI Recommendations

---

# 2. User Roles

## Student

A student can:

- Login using Google
- Register Student ID
- View available cycles
- Book a cycle
- Make payments
- Start a ride
- End a ride
- View ride history
- Submit feedback

A student cannot:

- Access Admin Dashboard
- Modify lock codes
- View another student's bookings
- Book multiple cycles simultaneously

---

## Administrator

The administrator can:

- Manage users
- Add or update cycles
- Mark cycles under maintenance
- View all bookings
- View payments
- Update lock codes
- Monitor ride history
- View feedback

---

# 3. Booking Rules

A booking can only be created when:

- The selected cycle is available.
- The selected time slot is available.
- The user has no active booking.

Booking Status Lifecycle

Pending

↓

Paid

↓

Active

↓

Completed

OR

Cancelled

---

# 4. Payment Rules

Payment must be completed before:

- Booking confirmation
- Lock code generation
- Ride start

If payment fails:

- Booking is cancelled.
- Cycle becomes available again.

---

# 5. Ride Rules

A ride starts only after:

- Successful payment
- Booking confirmation
- Lock code is displayed

A ride ends when:

- User clicks "End Ride"
- User selects a drop location
- Ride details are stored

---

# 6. Cycle Rules

Each cycle has one status at any given time.

Possible statuses:

- Available
- Booked
- Riding
- Maintenance

Status Flow

Available

↓

Booked

↓

Riding

↓

Available

OR

Maintenance

↓

Available

---

# 7. Lock Code Rules

For the MVP:

- Each confirmed booking receives a temporary lock combination.
- Lock code is displayed only after successful payment.
- Lock code remains valid only for the booking duration.
- Lock combinations are updated manually by the administrator.

Future versions will replace manual lock codes with IoT-based smart locks.

---

# 8. Ride History Rules

Each completed ride stores:

- User
- Cycle
- Ride Start Time
- Ride End Time
- Duration
- Pickup Location
- Drop Location

---

# 9. Feedback Rules

Feedback can only be submitted after a ride is completed.

Each ride can receive one feedback entry consisting of:

- Rating (1–5)
- Comment

---

# 10. Error Handling Rules

If a cycle is unavailable:

Display an appropriate message and suggest another available cycle.

If payment fails:

Allow the user to retry or cancel the booking.

If the user already has an active booking:

Prevent creating another booking.

---

# 11. Security Rules

- Google Authentication is mandatory.
- JWT protects backend APIs.
- Payment verification is performed on the backend.
- Students can only access their own data.
- Administrator routes require admin authorization.

---

# 12. Future Roadmap

Phase 1

Manual Combination Lock

↓

Phase 2

QR-Based Unlock

↓

Phase 3

Bluetooth Smart Lock

↓

Phase 4

GPS Tracking

↓

Phase 5

EV Fleet Integration

↓

Phase 6

Multi-University Deployment

---

# Definition of Success

The MVP is considered successful if a student can:

1. Login using Google.
2. View available cycles.
3. Book a cycle.
4. Complete payment.
5. Receive a lock combination.
6. Start and end a ride.
7. View ride history.
8. Submit feedback.

The administrator should be able to monitor:

- Users
- Cycles
- Bookings
- Revenue
- Ride History
- Feedback