# AuthGuard Component Documentation. Source: inno-alumni-portal/src/guards/auth-guard.js

## Overview

The `AuthGuard` component is designed to safeguard routes based on the user's authentication status. It redirects unauthenticated users to the login page and permits the rendering of its children for authenticated users. This component relies on React hooks, including `useEffect`, `useRef`, and `useState`, as well as Next.js's `useRouter` and `PropTypes` for type validation. It interacts with the authentication context through the `useAuthContext` hook.

## Dependencies

Ensure you import the necessary dependencies at the beginning of your project:

```javascript
import { useEffect, useRef, useState } from 'react';
import { useRouter } from 'next/router';
import PropTypes from 'prop-types';
import { useAuthContext } from 'src/contexts/auth-context';
```

## AuthGuard Component

```javascript
export const AuthGuard = (props) => { /* ... */ };
```

### AuthGuard Props

- `children` (ReactNode): The children components to render if authenticated.

### AuthGuard Usage

Wrap the components or routes you want to protect with the `AuthGuard` component:

```javascript
<AuthGuard>
  {/* Your protected components or routes */}
</AuthGuard>
```

## useEffect and Next.js Router Initialization

The `useEffect` hook is utilized to perform the authentication check on component mount. The `useRouter` hook from Next.js is initialized for routing purposes.

```javascript
const router = useRouter();
const { isAuthenticated } = useAuthContext();
const ignore = useRef(false);
const [checked, setChecked] = useState(false);
```

## Authentication Check

The authentication check is performed when the component mounts. If the user is not authenticated, the component redirects to the login page. If authenticated, it sets the `checked` state to true.

```javascript
useEffect(
  () => {
    if (!router.isReady) {
      return;
    }

    if (ignore.current) {
      return;
    }

    ignore.current = true;

    if (!isAuthenticated) {
      router
        .replace({
          pathname: '/auth/login',
          query: router.asPath !== '/' ? { continueUrl: router.asPath } : undefined
        })
        .catch(console.error);
    } else {
      setChecked(true);
    }
  },
  [router.isReady]
);
```

## Rendering Logic

The component renders null until the authentication check is complete. Once checked, it renders the specified children components.

```javascript
if (!checked) {
  return null;
}

return children;
```

## PropTypes

The `AuthGuard` component expects the following prop:

- `children` (PropTypes.node): The children components to render if authenticated.

```javascript
AuthGuard.propTypes = {
  children: PropTypes.node
};
```
