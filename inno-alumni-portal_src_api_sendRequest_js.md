# Technical Documentation. Source: inno-alumni-portal/src/api/sendRequest.js

## Overview

The provided codebase includes a utility function, `sendRequest`, designed for asynchronous HTTP requests. It utilizes the `isomorphic-unfetch` library for cross-environment HTTP requests and incorporates the `notify` utility for displaying notifications.

## Dependencies

Make sure to import the required dependencies at the beginning of your project:

```javascript
import "isomorphic-unfetch"; // Importing isomorphic-unfetch for cross-environment HTTP requests
import notify from "../utils/notify"; // Importing the notify utility for displaying notifications
```

## Configuration

Retrieve environment variables or set default values for `PORT` and `ROOT_URL`:

```javascript
let { PORT, ROOT_URL } = process.env || {};
PORT = PORT || 9001; // Defaulting to port 9001 if not provided
ROOT_URL = ROOT_URL || `http://127.0.0.1:${PORT}`; // Defaulting to localhost if not provided
```

## HTTP Request Utility Function (`sendRequest`)

### Description

The `sendRequest` function is an asynchronous utility designed for sending HTTP requests. It offers flexibility by allowing the inclusion of various options such as the request method, headers, and body.

### Function Signature

```javascript
async function sendRequest(path, options = {})
```

### Parameters

- `path` (string): The endpoint path for the request.
- `options` (Object): Additional options for the request.
  - `method` (string): HTTP request method (defaulting to "POST" if not specified).
  - `headers` (Object): Request headers.
    - `Remove-Content-Type` (boolean): If present, removes the "Content-Type" header.
    - Default headers:
      - `Content-Type`: "application/json; charset=UTF-8" (if not specified).
  - `body` (string): Request body.

### Example Usage

```javascript
const response = await send
