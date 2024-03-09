# Technical Documentation. Source: inno-alumni-portal/src/api/index.js

## Overview

This technical documentation provides detailed explanations of the codebase for user-related functionalities, pass requests, elective courses, and donations. The codebase is organized into modules, each responsible for a specific set of functionalities.

### Modules

1. **User Module (`user.js`):** Manages user-related operations such as user authentication, registration, profile updates, and interactions with InnoSSO.

2. **Pass Request Module (`passRequest.js`):** Handles the creation, retrieval, deletion, and administration of pass requests.

3. **Elective Course Module (`electiveCourse.js`):** Manages elective course-related operations, including retrieving course information, handling requests, and updating courses.

4. **Donation Module (`donation.js`):** Facilitates interactions related to donations, such as retrieving donation information, updating admin donation text, and making donation requests.

## User Module (`user.js`)

### 1. `loginRegularUser({ email, password })`

- **Description:** Initiates the login process for a regular user by submitting a login request with the provided email and password.
- **Parameters:**
  - `email` (string): The email of the user.
  - `password` (string): The password of the user.


### 2. `registerRegularUser({ name, email, password, confirmPassword }, options = {})`

- **Description:** Registers a new regular user by sending a registration request with the user's details.
- **Parameters:**
  - `name` (string): The name of the user.
  - `email` (string): The email of the user.
  - `password` (string): The password of the user.
  - `confirmPassword` (string): The confirmation of the password.
  - `options` (object, optional): Additional options for the request.


### 3. `registerAdminUser({ name, email, password })`

- **Description:** Registers a new admin user by submitting an admin registration request with the admin's details.
- **Parameters:**
  - `name` (string): The name of the admin.
  - `email` (string): The email of the admin.
  - `password` (string): The password of the admin.


### 4. `updateUserInformation(updateInformation)`

- **Description:** Updates the user's information by sending a request with the specified information to be updated.
- **Parameters:**
  - `updateInformation` (object): The information to be updated.


### 5. `updatePasswordInformation(passwordInformation)`

- **Description:** Updates the user's password by sending a request with the new password information.
- **Parameters:**
  - `passwordInformation` (object): The information containing the new password.


### 6. `loginWithInnoSSO(options = {})`

- **Description:** Performs a login using InnoSSO by submitting a request with additional options.
- **Parameters:**
  - `options` (object, optional): Additional options for the request.


### 7. `getCurrentUser({ accessToken })`

- **Description:** Retrieves information about the current user by sending a request with the provided access token.
- **Parameters:**
  - `accessToken` (string): The access token of the user.


### 8. `getAllRegisteredUsers()`

- **Description:** Retrieves information about all registered users.


# Pass Request Module (`passRequest.js`)

## 1. `createPassRequest({ request }, options = {})`

- **Description:** Initiates a new pass request by submitting the necessary details.
- **Parameters:**
  - `request` (object): An object containing the details of the pass request.
  - `options` (object, optional): Additional configuration options for the request.


## 2. `getPassRequestHistory()`

- **Description:** Retrieves the historical data of pass requests.


## 3. `deletePassRequest({ passRequestId })`

- **Description:** Removes a specific pass request based on the provided request ID.
- **Parameters:**
  - `passRequestId` (string): The unique identifier of the pass request to be deleted.


## 4. `getAllPassRequestAdmin()`

- **Description:** Gathers all pass requests for administrative purposes.


## 5. `updatePassRequest({ requestId, data })`

- **Description:** Modifies the details of a pass request identified by the request ID.
- **Parameters:**
  - `requestId` (string): The unique identifier of the pass request to be updated.
  - `data` (object): An object containing the information to be updated.

# Elective Course Module (`electiveCourse.js`)

## 1. `getAllElectiveCourses()`

- **Description:** Fetches details of all available elective courses.

## 2. `getAllElectiveCoursesAdmin()`

- **Description:** Retrieves information about all elective courses for administrative purposes.

## 3. `getBookedElectiveCourses()`

- **Description:** Retrieves information about all booked elective courses.

## 4. `getAllElectiveRequests()`

- **Description:** Retrieves information about all elective course requests.

## 5. `updateElectiveCourse({ courseId, data })`

- **Description:** Updates the details of a specific elective course.
  - `courseId` (string): The ID of the elective course to be updated.
  - `data` (object): The data to be updated.

## 6. `updateElectiveCourseRequest({ requestId, data })`

- **Description:** Updates the status of a specific elective course request.
  - `requestId` (string): The ID of the elective course request to be updated.
  - `data` (object): The data to be updated.

# Donation Module (`donation.js`)

## 1. `getAdminDonationText()`

- **Description:** Retrieves the admin donation text.

## 2. `getAllAlumniDonations()`

- **Description:** Fetches details of all donations made by alumni.

## 3. `upsertAdminDonationText({ donation })`

- **Description:** Updates or inserts the admin donation text.
  - `donation` (object): The donation text to be updated.

## 4. `makeDonationText({ donation })`

- **Description:** Initiates a donation interest with the provided donation text.
  - `donation` (object): The donation text.
