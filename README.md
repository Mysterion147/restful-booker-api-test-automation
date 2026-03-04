![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)

# Restful-Booker API Automation Suite

This project features a comprehensive automated testing suite for the **Restful-Booker API**. It demonstrates a robust CRUD lifecycle, security validation, and advanced error-handling scenarios.

## Project Goals
* Automate the end-to-end flow of booking management.
* Implement dynamic data persistence using Postman Environment Variables.
* Validate API resilience through negative testing and edge-case discovery.

## 🛠️ Tech Stack
* **Tool:** Postman
* **Scripting:** JavaScript (Postman Sandbox)
* **Reporting:** Postman Collection Runner

## 📂 Suite Structure
1. **01 - Health Check**: Verifies if the service is up.
2. **02 - Authentication**: Generates a dynamic `token` for protected routes (PUT/PATCH/DELETE).
3. **03 - Booking Management**: 
    * **POST**: Creates a booking and stores the `bookingId` and `lastName`.
    * **GET**: Retrieves data to ensure persistence.
    * **PUT/PATCH**: Validates full and partial updates using auth headers.
    * **DELETE**: Cleans up the generated data.
4. **04 - Negative Scenarios**: Validates 403 (Unauthorized), 404 (Not Found), and handles the API-specific 405 behavior for redundant deletions.

## 💡 Key Technical Insights
* **Status Code Discovery**: During testing, I identified that the API returns a `405 Method Not Allowed` when attempting to delete a resource that has already been removed, rather than the traditional `404`. This was documented and integrated into the test assertions.
* **Dynamic Variables**: The suite is designed to be "zero-config." All IDs and tokens are passed between requests automatically via environment variables.

## 🚀 How to Run
1. Clone this repository.
2. Import the files from the `/postman` folder into your Postman Workspace.
3. Select the `Restful-Booker-Prod` environment.
4. Open the **Collection Runner** and click **Run Restful-Booker**.