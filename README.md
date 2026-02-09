# 🚀 Enterprise E-Commerce Platform

## 🏗️ System Architecture

The system follows a modern **Decoupled Architecture**:
- **Frontend**: Single Page Application (SPA) built with Vanilla JS, CSS3 (Glassmorphism), and HTML5.
- **Backend**: Node.js & Express REST API.
- **Security**: JWT Authentication, Role-Based Access Control (RBAC), Password Hashing (Bcrypt), and Helmet protection.
- **Database**: SQLite for portability, with a normalized schema.

---

## 🛠️ Key Modules

### 1. User & Management
- **Security**: Passwords salted and hashed. Tokens valid for 7 days.
- **Roles**: Admin (Super control), User (Customer), and Delivery Agent (Logistics).
- **Audit Logs**: Tracking major actions in the database.

### 2. Order Management
- **Lifecycle**: Pending -> Confirmed -> Packed -> Shipped -> Delivered.
- **Stock Guard**: Real-time stock verification during checkout.
- **PDF Generation**: Ready for invoice integration (using PDFKit).

### 3. Payment System
- **Integration**: Mock payment gateway with Transaction ID generation.
- **Modes**: UPI, Cards, Net Banking, and COD support.
- **Safety**: Atomic transactions (simulated) for payment/order linkage.

### 4. Delivery Management
- **Tracking**: Unique tracking IDs for every shipment.
- **Agent Workflow**: Pickup -> In-Transit -> Delivered.
- **Live Updates**: Order status syncs automatically with delivery milestones.

---

## 📊 Database Schema (ER Summary)

| Table | Purpose |
|-------|---------|
| `users` | Identity management & roles |
| `products` | Inventory catalog |
| `orders` | Transaction headers |
| `order_items` | Line-item details |
| `payments` | Financial records |
| `deliveries` | Logistics & tracking |

---

## 🧪 Testing Scenarios

1. **Customer Flow**:
   - Register -> Login -> Browse Laptop -> Add to Cart -> Checkout (UPI) -> View Order History.
2. **Admin Flow**:
   - Login as `admin@ecommerce.com` -> View Dashboard Stats -> Manage Users -> Update Order Status.
3. **Logistics Flow**:
   - Login as `agent@ecommerce.com` -> View Assigned Deliveries -> Update Status to "Delivered".

---

## 🚀 How to Run

1. `npm install`
2. `node scripts/initDb.js`
3. `node scripts/seedData.js`
4. `npm start`
5. Open `http://localhost:3000`

**Default Credentials:**
- **Admin**: `admin@ecommerce.com` / `Admin@123`
- **User**: `user@ecommerce.com` / `User@123`
- **Agent**: `agent@ecommerce.com` / `Agent@123`
