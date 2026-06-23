# Smart City Traffic Management System

A full-stack **Smart City Traffic Management System** developed to monitor city traffic, analyze traffic density, display live traffic incidents, and provide a real-time digital dashboard for smart city traffic control.

This project combines a modern admin dashboard, MongoDB database, real-time data updates, map visualization, authentication, CSV export, multilingual support, and live traffic data integration using the TomTom Traffic API.

---

## Project Overview

The main purpose of this project is to provide a centralized traffic monitoring platform for smart city environments.

Modern cities face many traffic-related problems such as traffic congestion, roadworks, closed roads, accidents, slow traffic flow, and transportation delays. This project demonstrates how software systems can help monitor, analyze, and manage traffic information from one central dashboard.

The application allows users to view traffic statistics, inspect cities on a real map, monitor live traffic data, manage traffic incidents, and export city traffic data.

---

## Main Features

### Authentication System

The project includes a login system based on JWT authentication.

Only authenticated users can access the main dashboard and protected API routes.

Default test login:

```text
Email: admin@smartcity.com
Password: 123456
```

---

### Dashboard

The dashboard provides a general overview of the traffic system.

It displays:

* Total number of cities
* Average traffic density
* Average speed
* Active incidents
* Global system status
* Traffic trend visualization

This section helps users quickly understand the current traffic situation.

---

### World Map

The project includes a real map interface using OpenStreetMap and Leaflet.js.

Cities are displayed as interactive map markers. Users can click on a marker to inspect city traffic details such as:

* City name
* Country
* Traffic percentage
* Average speed
* AI traffic mode
* Traffic recommendation

This makes traffic data easier to understand visually.

---

### Cities Table

The Cities section displays a global city traffic table.

The table includes:

* City code
* City name
* Country
* Region
* Traffic percentage
* Average speed
* AI traffic mode

Users can search cities, filter by region, and export data as a CSV file.

---

### Live Traffic Data

The Live Traffic section integrates the TomTom Traffic API.

Users can select a city and fetch live traffic information, including:

* Current speed
* Free flow speed
* Current travel time
* Free flow travel time
* Confidence value
* Road closure status
* Live traffic incidents

This feature makes the project more realistic by connecting the system to external live traffic data.

---

### Traffic Incidents

The Incidents section is used to view and manage traffic-related events.

Supported incident examples:

* Roadworks
* Closed roads
* Accidents
* Congestion
* Traffic restrictions

Users can add new incidents, and the data is stored in MongoDB.

---

### Real-Time Updates

The project uses Socket.IO to provide real-time updates.

Traffic data can update dynamically without manually refreshing the page. This gives the dashboard a more realistic smart city monitoring experience.

---

### Multilingual Support

The interface supports three languages:

* English
* Turkish
* German

Users can switch the application language from the interface.

---

### CSV Export

The system includes CSV export functionality.

Users can export city traffic data and open it in spreadsheet tools such as Microsoft Excel or Google Sheets.

---

## Technologies Used

### Backend

* Node.js
* Express.js
* MongoDB
* Mongoose
* JWT Authentication
* Socket.IO
* TomTom Traffic API
* dotenv
* Helmet
* CORS
* Morgan

### Frontend

* HTML5
* CSS3
* JavaScript
* Leaflet.js
* OpenStreetMap
* Responsive dashboard design

### Database

* MongoDB

---

## Project Structure

```text
SmartCity_TomTom_Live_Pro/
│
├── backend/
│   ├── config/
│   │   └── db.js
│   │
│   ├── middleware/
│   │   └── auth.js
│   │
│   ├── models/
│   │   ├── User.js
│   │   ├── City.js
│   │   └── Incident.js
│   │
│   ├── routes/
│   │   ├── auth.js
│   │   ├── cities.js
│   │   ├── incidents.js
│   │   ├── export.js
│   │   └── tomtom.js
│   │
│   ├── seed/
│   │   └── seed.js
│   │
│   ├── services/
│   │   ├── simulation.js
│   │   └── tomtomService.js
│   │
│   ├── .env.example
│   ├── package.json
│   └── server.js
│
├── frontend/
│   ├── index.html
│   ├── style.css
│   └── app.js
│
└── README.md
```

---

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/smart-city-traffic-management-system.git
```

### 2. Open the project folder

```bash
cd smart-city-traffic-management-system/backend
```

### 3. Install backend dependencies

```bash
npm install
```

---

## Environment Variables

Create a `.env` file inside the `backend` folder.

Example:

```env
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/smartcity_global_maps_pro
JWT_SECRET=change_this_secret
TOMTOM_API_KEY=YOUR_TOMTOM_API_KEY_HERE
```

Important:

Do not upload your real `.env` file to GitHub.

Only upload `.env.example`.

Your real TomTom API key must stay private.

---

## MongoDB Setup

Make sure MongoDB is running on your computer.

Then seed the database:

```bash
npm run seed
```

This will insert sample users, cities, and traffic data.

Default login:

```text
admin@smartcity.com
123456
```

---

## Run the Project

Inside the `backend` folder, run:

```bash
npm run dev
```

or:

```bash
node server.js
```

Then open the application in your browser:

```text
http://localhost:5000
```

---

## API Endpoints

### Authentication

```text
POST /api/auth/login
```

Used for user login and JWT token generation.

---

### Cities

```text
GET /api/cities
```

Returns city traffic data.

Supports search and region filtering.

---

### Incidents

```text
GET /api/incidents
POST /api/incidents
```

Used for listing and adding traffic incidents.

---

### CSV Export

```text
GET /api/export/cities.csv
```

Exports city traffic data as a CSV file.

---

### TomTom Traffic API

```text
GET /api/tomtom/status
GET /api/tomtom/flow/:cityCode
GET /api/tomtom/incidents/:cityCode
GET /api/tomtom/flow-tile/:z/:x/:y.png
```

These routes are used for live traffic data, traffic incidents, and traffic map layer integration.

---

## How the System Works

1. The user logs into the system.
2. The backend checks the login credentials.
3. A JWT token is created after successful login.
4. The frontend stores the token and uses it for protected API requests.
5. MongoDB stores users, cities, and incidents.
6. Socket.IO sends real-time traffic updates to the frontend.
7. Leaflet.js displays cities on the map.
8. TomTom API provides live traffic flow and incident data.
9. The dashboard updates traffic values dynamically.
10. Users can export city traffic data as CSV.

---

## Use Case

This project can be useful for:

* Smart city traffic monitoring
* Municipality traffic control systems
* Urban planning dashboards
* Transportation management platforms
* Traffic incident tracking
* Real-time traffic visualization
* Academic software engineering projects
* Full-stack portfolio projects

---

## Screens / Main Pages

### Dashboard

Displays general traffic statistics and system overview.

### World Map

Shows city markers on a real map with traffic information.

### Cities

Displays city traffic data in a searchable and filterable table.

### Live Traffic

Fetches live traffic data and traffic incidents from TomTom API.

### Incidents

Displays and manages traffic-related incidents.

---

## Key Benefits

* Centralized traffic monitoring
* Real-time traffic updates
* Live external traffic data integration
* Map-based visualization
* Incident tracking
* MongoDB data storage
* Secure login system
* CSV export support
* Multilingual interface
* Professional dashboard design

---

## Future Improvements

Possible future improvements include:

* Route optimization
* AI-based traffic prediction
* PDF report export
* Excel report export
* Advanced charts and analytics
* Admin user management
* Role-based access control
* Notification system
* Mobile application version
* Cloud deployment

---

## Security Note

The TomTom API key must not be exposed publicly.

Before uploading to GitHub:

* Keep `.env` private
* Upload only `.env.example`
* Add `.env` to `.gitignore`
* Do not commit real API keys

Recommended `.gitignore`:

```gitignore
node_modules/
.env
.DS_Store
npm-debug.log
```

---

## Author

Developed by **Fatih Yaylacı**

Computer Engineering Student

---

## License

This project is developed for educational and portfolio purposes.
