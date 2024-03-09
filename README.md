# IU Alumni Project

## Project Overview

The IU Alumni project is a comprehensive system designed to assist university students in managing events, elective course registration, attendance tracking, and pass requests for various university-related purposes.

### Features

- **Event Management:** Keep track of university events and stay updated on upcoming activities.
- **Elective Course Registration:** Easily register for elective courses within the university.
- **Attendance Tracking:** Manage and track attendance for various university events.
- **Pass Requests:** Alumni users can request passes to enter the university for different purposes.

## Demo

Check out our [Demo Video](https://youtu.be/PwiZH98iqJ8) for a visual walkthrough of the IU Alumni project.

## How to Use

1. **Customer Complaints:** Users can submit complaints directly through the Telegram group mentioned on the website.
2. **Users Data Management:** Admins have the ability to accept or deny requests from users with feedback (providing reasons, for example).
3. **Pass Order:** Alumni users can request a pass to enter the university for different purposes directly from the main page of the website.
4. **Elective Courses Participation Requests:** Alumni users can request to attend elective courses held in the university at the time they are applying.

## Frameworks and Technology

- **Backend:** Python FastAPI
- **Frontend:** Next.js
- **Containerization:** Docker
- **Database:** PostgreSQL

## How to Run

### Alumni Portal Backend

#### Using Python

1. Open a shell/command line in the backend folder (preferably after activating a Python virtual env).
2. Install the required Python packages:

    ```bash
    pip install -r requirements.txt
    ```

3. Run the Python script:

    ```bash
    python3 main.py
    ```

#### Using Docker

- Build the Docker image (tag name can be customized):

    ```bash
    docker build -t alumni-backend .
    ```

- Run the Docker container (you can map the port locally as desired):

    ```bash
    docker run -p 8000:8000 -d alumni-backend
    ```

### Inno-alumni-portal Frontend

#### How to Run Locally

1. Open a shell/command line in the frontend folder.
2. Install all required packages locally using npm:

    ```bash
    npm install
    ```

3. Build the project for production:

    ```bash
    npm run build
    ```

4. Start the project in development mode:

    ```bash
    npm start
    ```

Now, you can access the IU Alumni portal locally and explore its features. Feel free to contribute to the project, and if you encounter any issues, check the respective README files in the frontend and backend folders for detailed instructions.
