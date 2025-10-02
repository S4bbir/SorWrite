# Custom Hooks Documentation

## useAuth

A hook that provides access to the authentication context.

### Usage

```tsx
import { useAuth } from '@/hooks/useAuth';

const MyComponent = () => {
  const { user, login, logout, register, isAuthenticated } = useAuth();
  
  // Use the auth functions and state
};
```

### Returns

- `user`: Current authenticated user object or null
- `login(email, password)`: Function to log in a user
- `logout()`: Function to log out the current user
- `register(name, email, password)`: Function to register a new user
- `isAuthenticated`: Boolean indicating if a user is authenticated

## useFetch

A hook for making HTTP requests with automatic loading and error states.

### Usage

```tsx
import { useFetch } from '@/hooks/useFetch';

const MyComponent = () => {
  const { data, loading, error } = useFetch('/api/tools');
  
  if (loading) return <div>Loading...</div>;
  if (error) return <div>Error: {error}</div>;
  if (!data) return <div>No data</div>;
  
  return <div>{/* Render data */}</div>;
};
```

### Parameters

- `url`: The URL to fetch data from
- `options` (optional): Fetch options

### Returns

- `data`: The fetched data or null
- `loading`: Boolean indicating if the request is in progress
- `error`: Error message or null

## useQuery

A hook that provides access to the query context.

### Usage

```tsx
import { useQuery } from '@/hooks/useQuery';

const MyComponent = () => {
  const { queries, addQuery, removeQuery, updateQuery } = useQuery();
  
  // Use the query functions and state
};
```

### Returns

- `queries`: Array of research queries
- `addQuery(query)`: Function to add a new query
- `removeQuery(id)`: Function to remove a query by ID
- `updateQuery(id, updates)`: Function to update a query by ID

## useTheme

A hook that provides access to the theme context.

### Usage

```tsx
import { useTheme } from '@/hooks/useTheme';

const MyComponent = () => {
  const { theme, toggleTheme } = useTheme();
  
  // Use the theme state and functions
};
```

### Returns

- `theme`: Current theme ('light' or 'dark')
- `toggleTheme()`: Function to switch between light and dark themes