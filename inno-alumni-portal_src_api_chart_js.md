# Technical Documentation. Sourse: inno-alumni-portal/src/api/chart.js

## Overview

The provided code comprises the `chart.js` module, which creates a styled component called `Chart`. This component is styled using the `styled` API from Material-UI (`@mui/material/styles`). The code also employs dynamic importing through the `next/dynamic` package to import the `ApexChart` component from 'react-apexcharts'.

## Dependencies

Ensure you import the required dependencies at the beginning of your project:

```javascript
import dynamic from 'next/dynamic'; // Importing dynamic from 'next/dynamic' for dynamic component importing
import { styled } from '@mui/material/styles'; // Importing styled from '@mui/material/styles' for component styling
```

## Dynamic Component Import

The `ApexChart` component is dynamically imported from 'react-apexcharts' for improved efficiency. This is facilitated using the `next/dynamic` package, with `ssr` set to `false` to prevent server-side rendering. The loading option renders nothing while the component is loading.

```javascript
const ApexChart = dynamic(() => import('react-apexcharts'), {
  ssr: false, // Preventing server-side rendering
  loading: () => null // Rendering nothing during component loading
});
```

## Styled Component - `Chart`

The `Chart` component is created as a styled component using the `styled` API from Material-UI. It extends the `ApexChart` component, inheriting its functionalities while being styled according to the specified design.

```javascript
export const Chart = styled(ApexChart)``;
```
