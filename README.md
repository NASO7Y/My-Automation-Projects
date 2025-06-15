# My-Automation-Projects

-------------------------------------------------------------------------------------------


## (1) 📩 Sheet Auto Responder
![Sheet Responder Workflow](Email_Sender/Sheet_Responder.png)
This project automates the process of reading user data from a Google Sheet, generating an AI-based response using a large language model (LLM), and sending that response via Gmail — while also logging the reply back to a Google Sheet.

### ⚙️ Workflow Overview

The automation is executed when the user manually triggers the workflow. The steps are as follows:

First i have the **Trigger Event** which means that The workflow starts when clicking **"Execute workflow"**.
this step takes me to **Read Google Sheet** to Read the data from my**Google Sheet**.
After that it goes to **Generate Response (LLM)** step when The data is passed to a **Basic LLM Chain** using the **Google Gemini Chat Model** to generate a relevant, human-like reply.

which takes me to the **Wait Delay** 
what is that ? it's A 30-second delay (`Wait`), the purpose i did it is to introduced to simulate thinking time or ensure asynchronous processing ( to delusion the customar that this is a human work not an automation).

**The final step is splited into half**

**Send Email (Gmail)**  
   The AI-generated response is sent via **Gmail** from my account `ahmed.noshy2004@gmail.com` to the intended recipient.

and also **Log to Google Sheet**  
   A copy of the response is also appended to another Google Sheet (`Google Sheets1`) for logging and tracking purposes.


-------------------------------------------------------------------------------------------

