# Setup and Usage Instructions

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Initial Setup](#initial-setup)
3. [Available Commands](#available-commands)
4. [Running Scripts](#running-scripts)
5. [Extending the Application](#extending-the-application)
6. [Best Practices](#best-practices)
7. [Documentation](#documentation)
8. [External Resources](#external-resources)

## Prerequisites

### System Requirements

- **Node.js**: Version 14 or higher
- **Package Manager**: npm or yarn
- **Operating System**: macOS, Linux, or Windows
- **Memory**: 2GB RAM minimum

## Initial Setup

### 1. Install Dependencies

1. Open the project in your IDE (VSCode recommended)
2. Install dependencies:
   ```bash
   npm install
   # or
   yarn install
   ```

### 2. Run Development Server

```bash
npm run dev
```

## Available Commands

### Development Commands

Start the development server with hot-reloading:

```bash
npm run dev
```

Build the optimized production version:

```bash
npm run build
```

Run the production server:

```bash
npm run start
```

Run ESLint:

```bash
npm run lint
```

### Running Scripts

The application primarily runs via the Next.js CLI. You can use standard npm scripts to manage the application lifecycle. Use `npm run <script-name>` to execute the desired command.

## Running the Application

### Development Mode

Start the development server with hot-reloading:

```bash
npm run dev
```

The application will be available at [http://localhost:3000](http://localhost:3000)

### Production Build

Build the optimized production version:

```bash
npm run build
```

### Production Server

Run the production server:

```bash
npm run start
```

Make sure to build the project first before running the production server.

## Project Structure

```
nextjs-example/
├── components/
│   └── Person.js          # Person list item component
├── pages/
│   ├── api/
│   │   └── people/
│   │       ├── index.js   # GET /api/people - Returns all people
│   │       └── [id].js    # GET /api/people/:id - Returns person by ID
│   ├── person/
│   │   └── [id].js        # Person detail page
│   └── index.js           # Home page - List of all people
├── data.js                # Static data source (Star Wars characters)
└── package.json
```

## Understanding the Application

### Pages

#### Home Page (`pages/index.js`)

- Displays a list of all Star Wars characters
- Fetches data from `/api/people` using SWR
- Shows loading state while fetching
- Displays error if fetch fails
- Each person is a clickable link to their detail page

#### Person Detail Page (`pages/person/[id].js`)

- Shows detailed information about a specific character
- Uses dynamic routing with `[id]` parameter
- Fetches data from `/api/people/:id` using SWR
- Displays character attributes in a table format

### API Routes

#### GET /api/people

- Returns all Star Wars characters as JSON
- Source: `data.js` file
- Response: Array of person objects

#### GET /api/people/:id

- Returns a single character by ID
- Source: `data.js` file
- Response: Person object or 404 error

### Components

#### Person Component (`components/Person.js`)

- Renders a single person as a list item
- Creates a link to the person's detail page
- Uses Next.js Link component for client-side navigation

### Data Source

The application uses a static data file (`data.js`) containing Star Wars character information:

- ID
- Name
- Height
- Mass
- Hair color
- Skin color
- Eye color
- Gender

## Adding New Data

To add more characters, edit `data.js`:

```javascript
export const people = [
  {
    id: '11',
    name: 'New Character',
    height: '180',
    mass: '80',
    hair_color: 'brown',
    skin_color: 'fair',
    eye_color: 'green',
    gender: 'male',
  },
  // ... existing characters
];
```

## Key Features Demonstrated

### 1. API Routes

Next.js built-in API routes for creating serverless endpoints:

- Simple function-based handlers
- Dynamic route parameters
- JSON responses
- Error handling

### 2. SWR Data Fetching

Stale-While-Revalidate pattern for efficient data fetching:

- Automatic caching
- Revalidation on focus
- Loading and error states
- Optimistic UI updates

### 3. Dynamic Routing

Next.js file-based routing with dynamic parameters:

- `[id].js` creates dynamic routes
- Accessible via `useRouter` hook
- Type-safe parameter access

### 4. Client-Side Navigation

Next.js Link component for seamless navigation:

- Pre-fetching on hover
- No full page reloads
- Smooth transitions

## Customization

### Styling

Add CSS by creating a global stylesheet or using CSS modules:

```javascript
import styles from './styles.module.css';
```

### Database Integration

Replace `data.js` with actual database queries in API routes:

```javascript
export default async function handler(req, res) {
  const people = await db.query('SELECT * FROM people');
  res.status(200).json(people);
}
```

### Environment Variables

Create `.env.local` for environment-specific configuration:

```
DATABASE_URL=your_database_url
API_KEY=your_api_key
```

## Deployment

### Vercel (Recommended)

The easiest way to deploy Next.js applications:

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel
```

### Other Platforms

Build the static version:

```bash
npm run build
```

Then deploy the `.next` folder to your hosting provider.

## Troubleshooting

### Port Already in Use

If port 3000 is occupied, specify a different port:

```bash
npm run dev -- -p 3001
```

### Build Errors

Ensure all dependencies are installed:

```bash
rm -rf node_modules package-lock.json
npm install
```

### API Route Not Found

Verify the file structure in `pages/api/` matches the expected route pattern.

### Extending the Application

1. **Adding API Routes**: Create new files in `pages/api`
2. **Adding Pages**: Create new files in `pages/`
3. **Adding Components**: Add reusable React components to `components/`
4. **Database Integration**: Replace `data.js` with database queries in API routes

## Best Practices

1. **Environment Variables**: Use `.env.local` for local development
2. **Component Reuse**: Abstract common UI patterns into components
3. **Data Fetching**: Prefer SWR for client-side data fetching
4. **Error Handling**: Always return appropriate HTTP status codes from API routes

### Documentation

- [README.md](README.md) - Project overview and architecture
- [Next.js Docs](https://nextjs.org/docs) - Framework documentation
- [SWR Docs](https://swr.vercel.app) - Data fetching documentation

### External Resources

- [React Documentation](https://react.dev)
- [Vercel Deployment Guide](https://vercel.com/docs)
- [Star Wars API (Reference)](https://swapi.dev/)

---

**Last Updated**: June 2026
**Version**: 1.0.0

## Author

- **Or Assayag** - _Initial work_ - [orassayag](https://github.com/orassayag)
- Or Assayag <orassayag@gmail.com>
- GitHub: https://github.com/orassayag
- StackOverflow: https://stackoverflow.com/users/4442606/or-assayag?tab=profile
- LinkedIn: https://linkedin.com/in/orassayag
