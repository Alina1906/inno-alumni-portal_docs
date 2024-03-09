# withAuthGuard Higher Order Component Documentation. Source: inno-alumni-portal/src/hocs/with-auth-guard.js

## Overview

The `withAuthGuard` Higher Order Component (HOC) is designed to wrap another component with authentication guarding. It ensures that the wrapped component is only rendered if the user is authenticated. This HOC leverages the `AuthGuard` component from the `auth-guard` file.

## Dependencies

Ensure you import the `AuthGuard` component at the beginning of your project:

```javascript
import { AuthGuard } from 'src/guards/auth-guard';
```

## withAuthGuard HOC

```javascript
export const withAuthGuard = (Component) => (props) => (
  <AuthGuard>
    <Component {...props} />
  </AuthGuard>
);
```

### Parameters

- `Component` (React.ComponentType): The component to be wrapped with authentication guarding.
- `props` (object): The props to be passed to the wrapped component.

### Usage

Wrap your desired component using the `withAuthGuard` HOC:

```javascript
const WrappedComponent = withAuthGuard(MyComponent);
```

or

```javascript
const EnhancedComponent = withAuthGuard((props) => <MyComponent {...props} />);
```

### Example

```javascript
const AuthenticatedMyComponent = withAuthGuard(MyComponent);

// In your render function or JSX
<AuthenticatedMyComponent {...otherProps} />
```

The `withAuthGuard` HOC ensures that `MyComponent` will only render if the user is authenticated.

```plaintext
Note: Ensure that the `AuthGuard` component is imported before using the `withAuthGuard` HOC.
```
