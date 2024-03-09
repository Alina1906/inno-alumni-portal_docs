# Authentication Module Documentation. Source: inno-alumni-portal/src/contexts/auth-context.js

## Overview

The provided module handles user authentication, offering a comprehensive set of functions for managing authentication state, user sign-in, sign-up, and sign-out. The module utilizes React hooks, including `useEffect`, `useReducer`, and `useRef`, and relies on `PropTypes` for defining prop types. It interfaces with the authentication-related functions from the 'src/api' module, including `getCurrentUser`, `loginRegularUser`, and `registerRegularUser`.

## Dependencies

Ensure you import the necessary dependencies at the beginning of your project:

```javascript
import { createContext, useContext, useEffect, useReducer, useRef } from 'react';
import PropTypes from 'prop-types';
import { getCurrentUser, loginRegularUser, registerRegularUser } from 'src/api';
```

## Enum for Action Types

An enumeration (`HANDLERS`) is provided for action types used within the reducer to manage authentication state transitions.

```javascript
const HANDLERS = {
  INITIALIZE: 'INITIALIZE',
  SIGN_IN: 'SIGN_IN',
  SIGN_OUT: 'SIGN_OUT'
};
```

## Initial State and Reducer

The initial state for the authentication context is defined with properties such as `isAuthenticated`, `isLoading`, and `user`. The `reducer` function handles authentication state transitions based on different action types.

```javascript
const initialState = {
  isAuthenticated: false,
  isLoading: true,
  user: null
};

const reducer = (state, action) => (
  handlers[action.type] ? handlers[action.type](state, action) : state
);
```

## Handlers

Various handlers are defined within the reducer for different action types, such as initializing, signing in, and signing out.

```javascript
const handlers = {
  [HANDLERS.INITIALIZE]: (state, action) => { /* ... */ },
  [HANDLERS.SIGN_IN]: (state, action) => { /* ... */ },
  [HANDLERS.SIGN_OUT]: (state) => { /* ... */ }
};
```

## Authentication Context

The authentication context (`AuthContext`) is created using `createContext` and has an initial value of `undefined`.

```javascript
export const AuthContext = createContext({ undefined });
```

## AuthProvider Component

The `AuthProvider` component manages authentication state and provides authentication-related functions. It takes in `children` as a prop.

```javascript
export const AuthProvider = (props) => { /* ... */ };
```

### AuthProvider Props

- `children` (ReactNode): The child components wrapped by the `AuthProvider`.

## Custom Hook - `useAuthContext`

A custom hook (`useAuthContext`) is provided to access the authentication context and its state and functions.

```javascript
export const useAuthContext = () => useContext(AuthContext);
```

## AuthProvider Functions

### 1. `initialize()`

This function initializes the authentication state, checking session storage for authentication details and dispatching an initialization action.

### 2. `skip()`

Simulates authentication without signing in, storing authentication details in session storage and dispatching a sign-in action.

### 3. `signIn(email, password)`

Signs in a user by calling the `loginRegularUser` API function and updating the authentication state accordingly.

### 4. `signUp(email, name, password, confirmPassword)`

Signs up a new user by calling the `registerRegularUser` API function. Note: The handling of the registration response is to be implemented.

### 5. `signOut()`

Signs out the current user, dispatching a sign-out action.

## Usage

Wrap your application with the `AuthProvider` to manage authentication state across components.

```javascript
<AuthProvider>
  {/* Your application components */}
</AuthProvider>
```

## PropTypes

The `AuthProvider` component expects the following prop:

- `children` (PropTypes.node): The child components wrapped by the `AuthProvider`.

```javascript
AuthProvider.propTypes = {
  children: PropTypes.node
};
```

## Consumer - `AuthConsumer`

To consume the `AuthContext`, use the `AuthConsumer` component.

```javascript
export const AuthConsumer = AuthContext.Consumer;
```
