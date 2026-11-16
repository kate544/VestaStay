# 🏨 VestaStay

A full-stack hotel booking web application. Guests can search for rooms, pay online and receive email confirmations, while hotel staff manage rooms and bookings from an admin portal.

**Live site:** [kate544.github.io/VestaStay](https://kate544.github.io/VestaStay/)

---

## ✨ Features

**Guest site**

- Search rooms by location and other criteria
- Browse featured rooms with price, bed type and guest capacity
- Book and pay with **M-Pesa** or **card (Paystack)**
- Email notification on successful booking

**Admin / manager portal**

- Role-based login (guest, manager, admin)
- View, update and delete bookings
- Add, edit and delete rooms
- Room status updates automatically: a room with quantity `0` becomes **Sold Out**

---

## 🛠️ Tech Stack

| Layer    | Technology                                |
| -------- | ----------------------------------------- |
| Frontend | React (Create React App), CSS             |
| Backend  | Node.js, Express                          |
| Database | MongoDB Atlas with Mongoose               |
| Payments | Paystack, M-Pesa                          |
| Email    | Nodemailer                                |
| Hosting  | GitHub Pages (frontend), Render (backend) |

---

## 📁 Project Structure

```
VestaStay/
├── Main Backend/   # Express API (server.js), connects to MongoDB
├── backend/        # Additional backend code
├── public/         # Static assets
└── src/            # React frontend
    └── Components/ # Navbar, Hero, FeaturedHotel, Admin, Login, payments...
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18 or later
- A MongoDB Atlas cluster (or a local MongoDB instance)
- An email account that supports SMTP (for example a Gmail app password)

### 1. Clone the repository

```bash
git clone https://github.com/kate544/VestaStay.git
cd VestaStay
```

### 2. Run the backend

```bash
cd "Main Backend"
npm install
```

Create a `.env` file inside `Main Backend` (see the variables below), then start the server:

```bash
npm run start
```

You should see:

```
🚀 VestaStay Server on http://localhost:7000
📧 Email Service Ready
✅ VestaStay Main Database Connected!
```

### 3. Run the frontend

From the project root:

```bash
npm install
npm start
```

The app opens at `http://localhost:3000`.

> The frontend currently calls the deployed API at `https://vestastay.onrender.com`. To develop against your local backend, change that URL to `http://localhost:7000` in `src/App.jsx` (and any other file that calls the API).

---

### Bookings

| Method      | Endpoint            | Description       |
| ----------- | ------------------- | ----------------- |
| GET         | `/api/bookings`     | List all bookings |
| POST        | `/api/bookings`     | Create a booking  |
| PUT / PATCH | `/api/bookings/:id` | Update a booking  |
| DELETE      | `/api/bookings/:id` | Delete a booking  |

### Rooms

| Method      | Endpoint         | Description                             |
| ----------- | ---------------- | --------------------------------------- |
| GET         | `/api/rooms`     | List all rooms                          |
| POST        | `/api/rooms`     | Add a room                              |
| PUT / PATCH | `/api/rooms/:id` | Update a room (status follows quantity) |
| DELETE      | `/api/rooms/:id` | Delete a room                           |

### Room document

```json
{
  "name": "Family Suite",
  "location": "Mombasa",
  "type": "King Bed",
  "price": 25000,
  "numofGuests": 4,
  "quantity": 15,
  "details": "Free Wifi • Breakfast & Dinner Included",
  "image": "<url or base64>",
  "status": "Available"
}
```

`name`, `location`, `type`, `price` and `numofGuests` are required.

---

## 🗺️ Roadmap

- Date-based availability and double-booking prevention
- Reduce room quantity automatically after a confirmed booking
- Booking history for guests
- Image uploads to cloud storage instead of storing images in the database

---

## 👩‍💻 Author

**Kathryn** — [@kate544](https://github.com/kate544) · [Portfolio](https://kate544.github.io/My-Portfolio)

---

## 📄 License

This project is for learning and portfolio purposes.
