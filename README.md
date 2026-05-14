# Smart Energy Monitoring Web Application

A Next.js-based dashboard for monitoring and visualizing energy generated from piezoelectric tiles.

## Features

- **Real-time Energy Monitoring**: Track energy generation from piezoelectric tiles
- **Interactive Dashboard**: Clean, user-friendly interface with responsive design
- **Data Visualization**: Charts and graphs using Recharts library
- **Backend APIs**: RESTful APIs for data storage and retrieval
- **Real-time Updates**: Simulated live data updates every 30 seconds
- **Time-based Filters**: Daily, weekly, and monthly energy tracking
- **Multi-source Support**: Piezoelectric, solar, and grid energy sources

## Tech Stack

- **Frontend**: Next.js 14, React 18, TypeScript
- **Backend**: Next.js API Routes
- **Styling**: Tailwind CSS
- **Charts**: Recharts
- **Data Storage**: In-memory (for demo purposes)
- **Development**: ESLint, PostCSS

## Phase 2: Data Processing & Real-Time Monitoring

### Backend APIs

The application includes the following RESTful API endpoints:

#### GET /api/energy
Retrieves comprehensive energy statistics including:
- Total energy generated
- Daily, weekly, and monthly generation data
- Consumption breakdown by category
- Real-time data points
- Source breakdown (piezoelectric, solar, grid)

#### POST /api/energy
Adds new energy data records. Request body:
```json
{
  "energy": 15.5,
  "source": "piezoelectric",
  "consumption": {
    "lighting": 3.2,
    "heating": 2.1,
    "appliances": 5.8,
    "other": 1.4
  }
}
```

#### GET /api/energy/realtime
Retrieves the latest real-time energy data points (last 24 hours).

#### POST /api/energy/realtime
Simulates new real-time energy data generation.

#### GET /api/energy/filters?period=daily|weekly|monthly
Retrieves filtered energy data based on the specified time period.

### Real-Time Updates

- **Automatic Updates**: Dashboard refreshes every 30 seconds
- **Simulated Data**: Random energy generation between 5-25 kWh
- **Multi-Source**: Alternates between piezoelectric, solar, and grid sources
- **Data Retention**: Maintains last 24 hours of real-time data

### Dashboard Features

- **Live Status Indicator**: Shows real-time connection status
- **Time Filters**: Interactive buttons for daily/weekly/monthly views
- **Responsive Charts**: Line charts for generation trends, pie charts for source breakdown
- **Consumption Tracking**: Detailed breakdown by lighting, heating, appliances, and other
- **Efficiency Metrics**: Calculated utilization rates

## Getting Started

### Prerequisites

- Node.js 18+
- npm or yarn

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd smart-energy-monitoring
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the development server:
   ```bash
   npm run dev
   ```

4. Open [http://localhost:3000](http://localhost:3000) in your browser.

## Project Structure

```
src/
├── app/
│   ├── api/
│   │   ├── energy/
│   │   │   ├── filters/
│   │   │   │   └── route.ts
│   │   │   ├── realtime/
│   │   │   │   └── route.ts
│   │   │   └── route.ts
│   ├── layout.tsx
│   ├── page.tsx
│   └── globals.css
├── components/
│   └── EnergyDashboardFoundation.tsx
├── services/
│   └── energyDataService.ts
└── types/
    └── energy.ts
```

## API Documentation

### Data Models

#### EnergyData
```typescript
interface EnergyData {
  id: string;
  timestamp: Date;
  energy: number;
  source: 'piezoelectric' | 'solar' | 'grid';
  consumption?: {
    lighting: number;
    heating: number;
    appliances: number;
    other: number;
  };
}
```

#### EnergyStats
```typescript
interface EnergyStats {
  totalGenerated: number;
  dailyGenerated: EnergyData[];
  weeklyGenerated: EnergyData[];
  monthlyGenerated: EnergyData[];
  consumptionOverview: {
    lighting: number;
    heating: number;
    appliances: number;
    other: number;
  };
  realTimeData: EnergyData[];
  sourceBreakdown: {
    piezoelectric: number;
    solar: number;
    grid: number;
  };
}
```

### API Endpoints

All endpoints return JSON responses. Error responses include an `error` field with a descriptive message.

### Error Handling

- **400 Bad Request**: Invalid request parameters
- **500 Internal Server Error**: Server-side processing errors

## Dashboard Features

- **Total Energy Generated**: Displays cumulative energy production
- **Filtered Generation Charts**: Line charts showing energy generation by time period
- **Real-time Production**: Live energy production visualization with auto-refresh
- **Consumption Overview**: Detailed breakdown by category
- **Source Breakdown**: Pie chart showing energy sources (piezoelectric, solar, grid)
- **Efficiency Metrics**: Calculated utilization rates
- **Time Filters**: Interactive filtering for daily/weekly/monthly views
- **Live Status**: Real-time connection indicator

## Data Simulation

The application includes automated data simulation:
- **Real-time Updates**: New data points generated every 30 seconds
- **Random Generation**: Energy values between 5-25 kWh
- **Source Rotation**: Alternates between piezoelectric, solar, and grid sources
- **Data Persistence**: In-memory storage with automatic cleanup (last 1000 records, 24h real-time)

## Future Enhancements

- Database integration (MongoDB/PostgreSQL)
- WebSocket implementation for true real-time updates
- User authentication and role-based access
- Advanced analytics and reporting
- Mobile app development
- IoT device integration
- Predictive analytics using machine learning

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## License

This project is licensed under the MIT License.