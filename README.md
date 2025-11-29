# COMP 3123 - Assignment 2 - Frontend

### By Eduard Kosenko, 101480050

## Libraries Used

- **React** (v19.2.0) - UI library
- **Redux Toolkit** (v2.11.0) - State management
- **React Router DOM** (v7.9.6) - Client-side routing
- **Material-UI** (v7.3.5) - Component library
- **Axios** (v1.13.2) - HTTP client

## Project Structure

```
src/
 api/                    # API layer with Axios client & interceptors
 redux/
    store.js
    slices/             # userSlice.js, employeeSlice.js
 components/
     routes/             # Login, Signup, Employee pages
     shell/              # Main layout, navigation
     breadcrumbs/        # Pretty utility for current location display
```

## Exception Handling

### API Client (client.js)
- **Request Interceptor**: Adds JWT token to all requests from localStorage
- **Response Interceptor**: Handles 401 errors by clearing token and redirecting to login

### Redux Thunks (employeeSlice.js)
- **Validation Errors**: Extracts express-validator field errors into object mapping
- **General Errors**: Returns error message from backend or fallback message

### Components
- **Field-level errors**: Displayed via TextField `helperText` and `error` props
- **General errors**: Alert component with dismiss functionality
- **Loading states**: CircularProgress