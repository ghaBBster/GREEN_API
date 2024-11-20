# Green API Interaction - HTML Page

This project is an interactive HTML page designed to interact with the **Green API**. It allows users to connect to their WhatsApp instance, call various API methods (`GetSettings`, `SendMessage`), and view the responses directly on the page.

## Features
- **Get Settings**: Retrieve the configuration settings of the WhatsApp instance.
- **Send Message**: Send a WhatsApp message to a specified phone number.
- **User-friendly interface**: Easy to use, with an input form and a dedicated area for displaying API responses.

## Requirements
- A **Green API** account with a created instance.
- **API Token** and **Instance ID** for authentication.

## Getting Started

### 1. Set up Green API Instance
1. Go to [Green API](https://green-api.com/) and create a free developer account.
2. After logging in, create a new instance to generate your `idInstance` and `apiTokenInstance`.
3. Scan the QR code to connect your WhatsApp number to the instance.

### 2. Use the HTML Page
1. Download or clone this repository.
2. Open the `index.html` file in your browser.

### 3. Enter Your Instance Credentials
On the webpage:
1. Input the **ID Instance** and **API Token** that you received from Green API.
2. Press **Get Settings** to fetch and view your WhatsApp instance settings.
3. To send a message, enter the phone number (without the `+` symbol) and the message content, then click **Send Message**.

### 4. View API Response
- The response from the Green API will appear in the **API Response** area on the right side of the page.

---

## Usage

- **Get Settings**:
   - Click the `Get Settings` button to retrieve the current settings of your Green API instance. The response will be displayed in the right-hand panel.
  
- **Send Message**:
   - Enter the phone number in the format `1234567890` (without the `+` sign) and the message you wish to send.
   - Click the `Send Message` button. The message will be sent via your Green API instance, and the response will appear in the right-hand panel.


## API Endpoints Used

1. **GetSettings**: Fetches the current settings of your Green API instance.
   - URL format: `https://api.green-api.com/waInstance{idInstance}/GetSettings/{apiTokenInstance}`

2. **SendMessage**: Sends a WhatsApp message to a specified number.
   - URL format: `https://api.green-api.com/waInstance{idInstance}/SendMessage/{apiTokenInstance}`
   - Request Body:
     ```json
     {
       "chatId": "phone_number@c.us",
       "message": "Your message here"
     }
     ```

## API Responses
- **GetSettings**: Displays settings such as instance status, phone number, and more.
- **SendMessage**: Displays success or error information regarding the message.

## Example:

**Request to Send Message**:
```json
{
  "chatId": "1234567890@c.us",
  "message": "Hello, this is a test message!"
}
```

## Sample Response (SendMessage):
```json
{
  "statusCode": 200,
  "message": "Message sent successfully"
}
```
## Troubleshooting
  - Ensure your idInstance and apiTokenInstance are entered correctly.
  - If you're receiving a 400 error, verify that the chatId format is correct. It should be in the form of phone_number@c.us.
  - Check the status of your instance through the GetSettings endpoint to ensure that it is properly connected and activated.
