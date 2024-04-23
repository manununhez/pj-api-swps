# Google Sheets Express API

This Express API allows you to fetch data from and post data to Google Sheets.

## Prerequisites

Before running this API, ensure you have the following:

- Node.js installed on your machine
- Google Cloud Platform account with the Google Sheets API enabled
- `.env` file configured with the required environment variables (`PORT`, `REACT_APP_CLIENT_EMAIL`, `REACT_APP_PRIVATE_KEY`, `REACT_APP_GSHEET_SCOPE`, `REACT_APP_GSHEET_SPREADSHEET_ID`)

## Installation

1. Clone this repository to your local machine.
2. Navigate to the project directory.
3. Install dependencies using `npm install`.

## Usage

1. Start the Express server using `npm start`.
2. The server will be listening on port `5000` by default. You can change the port by setting the `PORT` environment variable.
3. Use the following endpoints:

   - `GET /v4-get`: Fetch data from Google Sheets.
     - Query Parameters:
       - `spreadSheetName`: The name of the Google Sheets spreadsheet.
       - `column`: Column range to retrieve data from.
       - `row`: Row range to retrieve data from.

   - `POST /v4-post`: Post data to Google Sheets.
     - Request Body:
       ```json
       {
         "spreadSheetName": "Sheet1",
         "column": "A:B",
         "row": "2",
         "submissionValues": [
           ["value1", "value2"],
           ["value3", "value4"]
         ]
       }
       ```

## Notes

- Ensure that the necessary permissions are granted to the service account associated with the JWT client.
- Handle authentication securely by storing sensitive information such as private keys in environment variables.
- This API uses CORS to allow cross-origin requests from any domain. Ensure proper security measures are in place.
- For detailed API documentation, refer to the inline comments in the code.

