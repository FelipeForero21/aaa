Sure! Here's the updated README.md including the MongoDB URI and API Key setup.

markdown
Copiar código
# DATA CLEAN RIWI TEAM 3 API

## Overview

This API provides functionalities for file management and processing. Users can upload files, perform data sanitization tasks such as removing duplicates, validating formats, and sorting columns, and download the processed files in various formats. The API supports integration with cloud storage for file management and includes comprehensive logging for request tracking. Ensure you authenticate using the API key provided for secure access to the services.

## Features

- File upload and processing
- Data sanitization: remove duplicates, validate formats, sort columns
- Generate and download processed files in various formats (e.g., PDF)
- Cloud storage integration for file management
- Comprehensive logging for request tracking
- API documentation using Swagger

## Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/your-repo/data-clean-riwi-team3-api.git
    cd data-clean-riwi-team3-api
    ```

2. **Install dependencies:**
    ```bash
    npm install
    ```

3. **Set up environment variables:**
    Create a `.env` file in the root directory and add necessary environment variables. Example:
    ```env
    MONGODB_URI="mongodb+srv://elipeforero21:dJybd8CPBjePuhOF@assesment.yugiws4.mongodb.net/"
    API_KEY="añlsidjewefwee"
    ```

4. **Run the application:**
    ```bash
    npm run start
    ```

## API Documentation

The API documentation is available at `/api/doc` once the application is running. You can access it at `http://localhost:3000/api/doc`.

## Endpoints

### Upload File

- **URL:** `/api/v1/file/upload`
- **Method:** `POST`
- **Description:** Upload a file and process it
- **Responses:**
  - `201`: File processed and PDF generated
  - `400`: Bad Request

**Example Request:**

```bash
curl -X POST http://localhost:3000/api/v1/file/upload \
  -H 'Content-Type: multipart/form-data' \
  -F 'file=@/path/to/your/file.csv'
Detailed Explanation
FileController
uploadFile: Handles the file upload, processes the content, saves the data, generates a PDF, and responds with the PDF path.
FileService
getFileFromFileName: Retrieves the file content from the given filename.
extractContentToString: Extracts the content from the file and converts it to a string.
parseCsvContent: Parses the CSV content into a structured format.
generatePdf: Generates a PDF from the parsed CSV content.
PersonService
save: Saves the parsed data into the database.
Running the Application
Start the application:

bash
Copiar código
npm run start
Access the API:
The API will be available at http://localhost:3000/api/v1.

Access the API documentation:
The API documentation will be available at http://localhost:3000/api/doc.

Development
Running in development mode
To run the application in development mode, use the following command:

bash
Copiar código
npm run start:dev
Testing
To run tests, use the following command:

bash
Copiar código
npm run test
Linting
To lint the code, use the following command:

bash
Copiar código
npm run lint
Contributing
Contributions are welcome! Please follow these steps:

Fork the repository
Create a new branch
Make your changes
Submit a pull request
License
This project is licensed under the MIT License.

Contact
For any questions or issues, please contact [your-email@example.com].

css
Copiar código

Make sure to replace `[your-email@example.com]` with your actual contact email address.
