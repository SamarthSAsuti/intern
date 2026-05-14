# Smart Energy Monitoring Web Application

This is a Next.js project for Phase 1 of the Smart Energy Monitoring Web Application. It provides a dashboard to monitor energy generated from piezoelectric tiles.

## Features

- **Total Energy Generated**: Displays the cumulative energy generated.
- **Daily Energy Generation**: Shows the energy generated on the latest day.
- **Energy Consumption Overview**: Displays the total energy consumed.
- **Interactive Charts**: Line chart for daily energy generation and bar chart for energy consumption.

## Tech Stack

- **Frontend**: Next.js with TypeScript
- **Styling**: Tailwind CSS
- **Charts**: Recharts
- **Data**: Mock data simulating piezoelectric energy generation

## Getting Started

1. Install dependencies:
   ```bash
   npm install
   ```

2. Run the development server:
   ```bash
   npm run dev
   ```

3. Open [http://localhost:3000](http://localhost:3000) in your browser to view the dashboard.

## Project Structure

- `app/page.tsx`: Main dashboard page
- `app/layout.tsx`: Root layout
- `app/globals.css`: Global styles with Tailwind

## Mock Data

The application uses static mock data for demonstration. In a real application, this would be replaced with API calls to fetch live data from sensors.

## Deployment

This project can be deployed on Vercel, Render, or AWS as per the requirements.

## License

This project is part of an internship phase and is for educational purposes.
