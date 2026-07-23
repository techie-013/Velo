# 🚴 VELO MVP – User & Admin Workflow

## 👤 User Flow

### 1. Login
- User visits the VELO Web App.
- Login using Google Authentication.
- Student verifies identity using:
  - Student ID
  - University Email (optional in future)

---

### 2. Rider Dashboard

The dashboard displays:

- Available Cycles
- Current Pickup Locations
- Pricing
- Available Time Slots
- Ride Guidelines
- Ride History
- Wallet/Payment Status (Future)

---

### 3. Select Cycle

User chooses:

- Cycle 1 / Cycle 2
- Pickup Location
- Preferred Time Slot

System checks availability.

---

### 4. Booking Summary

Display:

- Cycle Number
- Pickup Location
- Selected Time Slot
- Ride Duration
- Pricing
- Security Guidelines

User confirms booking.

---

### 5. Payment

User proceeds to payment using Razorpay.

Supported Methods:

- UPI
- Cards
- Net Banking
- Wallets

---

### 6. Payment Verification

Frontend verifies successful payment.

↓

Backend verifies payment signature from Razorpay.

↓

Booking status becomes:

**CONFIRMED**

---

### 7. Unlock Code Generation

After successful verification:

System displays:

- Cycle Number
- Pickup Location
- Combination Lock Code

Example:

Cycle : VELO-01

Lock Code : 4821

⚠️ Lock code is valid only for the selected booking slot.

The combination code is manually updated by the VELO team once or twice daily during the pilot phase.

---

### 8. Ride Starts

User unlocks the bicycle.

Clicks:

**Start Ride**

System records:

- Ride Start Time
- Booking ID
- Cycle ID
- Rider ID

Ride Status:

ACTIVE

---

### 9. During Ride

User can view:

- Ride Timer
- Emergency Contact
- Ride Guidelines

(Future Features)

- Live GPS
- Battery Status (EV)
- Pause Ride

---

### 10. End Ride

User parks the bicycle at any designated VELO Drop Location.

Clicks:

**End Ride**

Selects:

- TB-6
- TB-7
- Girls Hostel
- Boys Hostel
- SC

Optionally uploads a parking photo (Future).

---

### 11. Feedback

User rates:

⭐⭐⭐⭐⭐

Optional feedback:

- Bicycle Condition
- Suggestions
- Issues Faced

---

### 12. Ride Completed

Ride summary is generated.

Includes:

- Ride Duration
- Amount Paid
- Pickup Location
- Drop Location
- Date & Time

Stored in Ride History.

---

# 🛠 Admin Workflow

## Admin Dashboard

Displays:

- Total Users
- Verified Students
- Total Cycles
- Active Rides
- Completed Rides
- Revenue
- Pending Bookings

---

## Cycle Management

For each cycle:

- Current Status
- Current Location
- Combination Lock Code
- Last Rider
- Ride History

Status:

- Available
- Booked
- Active Ride
- Maintenance

---

## Booking Management

View:

- Rider Details
- Student ID
- Payment Status
- Time Slot
- Pickup Location

Admin can:

- Approve
- Cancel
- Modify

---

## Ride Monitoring

Shows:

- Active Rider
- Ride Start Time
- Selected Drop Location
- Ride Duration

---

## Reports & Analytics

Generate reports for:

- Daily Revenue
- Weekly Revenue
- Monthly Revenue
- Most Used Pickup Location
- Most Used Drop Location
- Peak Booking Hours
- Repeat Customers
- Total Ride Count
- Average Ride Duration

---

## Feedback Dashboard

View:

- Ratings
- Complaints
- Suggestions

Mark issues as:

- Open
- In Progress
- Resolved

---

# 🔄 Future Roadmap

Phase 1 (Pilot)

- Google Login
- Student Verification
- Booking
- Razorpay Integration
- Manual Combination Lock
- Ride History
- Feedback
- Admin Dashboard

Phase 2

- Bluetooth Tracker
- Live Cycle Status
- QR Check-in
- Notifications

Phase 3

- IoT Smart Lock
- QR Scan & Auto Unlock
- GPS Tracking
- EV Integration
- Mobile App
- Digital Wallet
- Loyalty Program
