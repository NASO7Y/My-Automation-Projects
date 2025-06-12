# My-Automation-Projects


## (1) 📩 Sheet Auto Responder
![Sheet Responder Workflow](Email_Sender/Sheet_Responder.png)
This project automates the process of reading user data from a Google Sheet, generating an AI-based response using a large language model (LLM), and sending that response via Gmail — while also logging the reply back to a Google Sheet.

### ⚙️ Workflow Overview

The automation is executed when the user manually triggers the workflow. The steps are as follows:

1. **Trigger Event**  
   The workflow starts when clicking **"Execute workflow"**.

2. **Read Google Sheet**  
   Reads data (e.g., user input or form responses) from a predefined **Google Sheet**.

3. **Generate Response (LLM)**  
   The data is passed to a **Basic LLM Chain** using the **Google Gemini Chat Model** to generate a relevant, human-like reply.

4. **Wait Delay**  
   A 30-second delay (`Wait`) is introduced to simulate thinking time or ensure asynchronous processing.

5. **Send Email (Gmail)**  
   The AI-generated response is sent via **Gmail** from the account `ahmed.noshy2004@gmail.com` to the intended recipient.

6. **Log to Google Sheet**  
   A copy of the response is also appended to another Google Sheet (`Google Sheets1`) for logging and tracking purposes.

## 🧠 Technologies Used

-------------------------------------------------------------------------------------------
- **Google Sheets** – for reading user queries and logging responses.
- **Google Gemini Chat Model** – for generating intelligent responses.
- **Gmail API** – for sending automated emails.
- **Basic LLM Chain** – integration pipeline between input and the LLM.
- **Wait Node** – introduces a 30-second delay before sending the email.
