# Utility Functions Documentation

## API Utilities

The API utilities provide a simple interface for making HTTP requests to the backend.

### Usage

```tsx
import { api } from '@/utils/api';

// GET request
const getData = async () => {
  try {
    const data = await api.get('/tools');
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
};

// POST request
const postData = async () => {
  try {
    const newData = await api.post('/tools', { name: 'New Tool' });
    console.log(newData);
  } catch (error) {
    console.error('Error:', error);
  }
};
```

### Methods

- `api.get(endpoint, options)`: Makes a GET request
- `api.post(endpoint, data, options)`: Makes a POST request
- `api.put(endpoint, data, options)`: Makes a PUT request
- `api.delete(endpoint, options)`: Makes a DELETE request

## Formatting Utilities

Formatting utilities provide common formatting functions.

### Usage

```tsx
import { formatCurrency, formatDate, formatNumber, truncateText } from '@/utils/format';

// Format currency
const price = formatCurrency(1234.56); // $1,234.56

// Format date
const date = formatDate(new Date()); // Oct 1, 2025

// Format number
const views = formatNumber(1500); // 1.5K

// Truncate text
const title = truncateText('Very long title', 10); // Very long...
```

### Functions

- `formatCurrency(amount, currency)`: Formats a number as currency
- `formatDate(date)`: Formats a date as a readable string
- `formatNumber(num)`: Formats a large number with K/M suffixes
- `truncateText(text, maxLength)`: Truncates text with ellipsis

## Storage Utilities

Storage utilities provide a wrapper around localStorage with error handling.

### Usage

```tsx
import { storage } from '@/utils/storage';

// Set item
storage.set('key', { name: 'value' });

// Get item
const data = storage.get('key', defaultValue);

// Remove item
storage.remove('key');

// Clear all
storage.clear();
```

### Methods

- `storage.set(key, value)`: Sets a value in localStorage
- `storage.get(key, defaultValue)`: Gets a value from localStorage
- `storage.remove(key)`: Removes a value from localStorage
- `storage.clear()`: Clears all values from localStorage