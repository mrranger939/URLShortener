# Link Analytics Dashboard - A Mini-SaaS URL Shortener

Link Analytics Dashboard is a full-stack URL shortener with analytics capabilities similar to Bitly. This application allows users to create shortened links and track their performance through a comprehensive dashboard that displays metrics such as clicks, geographic locations, and device information.

## Features

- **User Authentication**
  - Email/password login using JWT
  - Secure user authentication
  - Pre-configured user account for easy testing

- **URL Shortening**
  - Create shortened links with custom aliases (optional)
  - Set expiration dates for links (optional)
  - Automatic short code generation

- **Analytics Dashboard**
  - Table of all created links with key metrics
  - Visual charts showing clicks over time
  - Device and browser breakdown
  - QR code generation for each short link

- **Asynchronous Tracking**
  - Collects data when someone clicks a short URL
  - Logs device type, browser information, and timestamps
  - Real-time analytics updates

## Project Structure

The project follows a client-server architecture:

```
├── client                  # React frontend
│   ├── public              # Static assets
│   ├── src
│   │   ├── assets          # Images and other assets
│   │   ├── components      # React components
│   │   │   ├── auth        # Authentication components
│   │   │   ├── dashboard   # Dashboard components
│   │   ├── App.jsx         # Main application component
│   │   ├── main.jsx        # Application entry point
│   │   ├── styles.css      # Global styles
│   ├── .env                # Frontend environment variables
│   ├── package.json        # Frontend dependencies
│
├── server                  # Node.js backend
│   ├── controllers         # Request handlers
│   ├── middleware          # Express middleware
│   ├── models              # MongoDB models
│   ├── routes              # API routes
│   ├── .env                # Backend environment 
│   ├── package.json        # Backend dependencies
│   ├── server.js           # Server entry point
```

## Tech Stack

- **Frontend**
  - React.js (with Vite)
  - Recharts for data visualization
  - Tailwind CSS for styling
  - QRCode.react for QR code generation

- **Backend**
  - Node.js
  - Express.js
  - MongoDB for database
  - JWT for authentication

## Getting Started

Follow these steps to run the project on your local machine:

### Prerequisites

- Node.js (v14 or higher)
- MongoDB (local installation or Atlas account)
- npm or yarn package manager

### Installation Steps

1. **Clone the repository**

   ```bash
   git clone https://github.com/mrranger939/URLShortener.git
   cd link-analytics
   ```

2. **Setup backend**

   ```bash
   cd server
   npm install
   ```

   Create a `.env` file in the server directory with the following content:

   ```
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/link-analytics
   JWT_SECRET=MohammedShujathNawaz
   BASE_URL=http://localhost:5000
   ```

3. **Setup frontend**

   ```bash
   cd ../client
   npm install
   ```

   Create a `.env` file in the client directory with the following content:

   ```
   VITE_REACT_APP_API_URL=http://localhost:5000
   ```

4. **Start MongoDB**

   If using a local MongoDB installation, make sure MongoDB service is running:

   ```bash
   # On Windows (using MongoDB as a service)
   # This should already be running if installed as a service

   # On macOS/Linux
   mongod --dbpath /path/to/data/directory
   ```

   If using MongoDB Atlas, ensure you've updated the MONGODB_URI in the server `.env` file.

5. **Start the backend server**

   ```bash
   cd server
   node ./server.js
   or
   nodemon ./server.js
   ```

   The server will run on http://localhost:5000

6. **Start the frontend development server**

   ```bash
   cd client
   npm run dev
   ```

   The application will be available at http://localhost:5173

7. **Access the application**

   Open your browser and navigate to http://localhost:5173

   Use the following credentials to log in:
   - Email: intern@dacoid.com
   - Password: Test123  
   or
   - Email: ranger@gmail.com
   - Password: 1234  

## Usage Guide

1. **Login** using the provided credentials
2. **Create a short link** by entering a URL and optional custom alias/expiration date
3. **View your links** in the dashboard table
4. **Access analytics** by clicking on the "Analytics" button for a specific link
5. **Generate QR Codes** for easy sharing of your shortened links
6. **Search and filter** your links using the search box

## Development

- The frontend is built with Vite for fast development
- API requests are configured to connect to the backend server
- MongoDB is used for storing user data, links, and click analytics
- JWT authentication protects routes and ensures secure access

## License

This project is licensed under the MIT License - see the LICENSE file for details.