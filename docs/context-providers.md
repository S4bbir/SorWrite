# Context Providers Documentation

## AuthContext

The AuthContext provides authentication state and functions throughout the application.

### Usage

```tsx
import { useAuth } from '@/context/AuthContext';

const MyComponent = () => {
  const { user, login, logout, register, isAuthenticated } = useAuth();
  
  // Use the auth functions and state
};
```

### API

- `user`: Current authenticated user object or null
- `login(email, password)`: Function to log in a user
- `logout()`: Function to log out the current user
- `register(name, email, password)`: Function to register a new user
- `isAuthenticated`: Boolean indicating if a user is authenticated

## ThemeContext

The ThemeContext provides theme management capabilities.

### Usage

```tsx
import { useTheme } from '@/context/ThemeContext';

const MyComponent = () => {
  const { theme, toggleTheme } = useTheme();
  
  // Use the theme state and functions
};
```

### API

- `theme`: Current theme ('light' or 'dark')
- `toggleTheme()`: Function to switch between light and dark themes

## QueryContext

The QueryContext provides research query management capabilities.

### Usage

```tsx
import { useQuery } from '@/context/QueryContext';

const MyComponent = () => {
  const { queries, addQuery, removeQuery, updateQuery } = useQuery();
  
  // Use the query functions and state
};
```

### API

- `queries`: Array of research queries
- `addQuery(query)`: Function to add a new query
- `removeQuery(id)`: Function to remove a query by ID
- `updateQuery(id, updates)`: Function to update a query by ID