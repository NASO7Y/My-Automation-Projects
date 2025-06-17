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
## (2) 📡  Auto Scraper
![Auto Scraper workflow](Auto_Scraper/Auto_Scraper.png)

This project automates the process of scraping country data (Country Name, Country Population, Country Area, Country Capital) from a website, for example I used [Scrapethis](https://www.scrapethissite.com/pages/simple/) then 
processing it, and updating a Google Sheet — all triggered manually.

The dataset was scraped and stored in [ScrapedDataset](Auto_Scraper/countries.xlsx)

### ⚙️ Workflow Overview

The automation begins when the user manually triggers the workflow. The steps are as follows:

First, the **Trigger Event** initiates the process by clicking **"Execute workflow"**. This leads to the **HTTP Request step**, performing a GET request to scrape data from the website
Next, the **HTML step** parses the retrieved web content. This is followed by the Code step, where the data is processed to extract  [Country Name, Country Population, Country Area, and Country Capital].

-- I COULD JUST USED ( SPLIT OUT ) BUT I WANTED TO TEST MY JAVASCRIPT CODE ABILITY😂 

The final step is to Update **Google Sheet**, where the scraped data (up to 250 items) is appended to a Google Sheet for storage and tracking

-------------------------------------------------------------------------------------------

## (3) 💼 Job Applying Agent
![Job_Applying_Agent](Job_Applying_Agent/Job_Applying_Agent.png)

This project automates the process of handling daily job application messages, filtering relevant job offers based on personal qualifications, generating tailored job applications, and sending them via email to the respective companies.

### ⚙️ Workflow Overview
I subscribed in a Jobs service which gives me a message daily that contains job applications,
The automation is triggered when a message containing the word “job” in the title arrives. The steps are as follows:

The first step is executed when the message containing the word **“job”** in the title arrives.

 After that, I created an **edit field** to clean and split the jobs into arrays, every array is linked to an individual job offer.  
 
The array goes directly to the **split out** step to change the array into a proper schema that can be fed into the LLM chain. The first LLM model has my own personal, Technical data and filters the jobs based on my data into 2 categories:   

`1- useful job offers \> match my skills and qualifications`   

`2- not useful job offers \> doesn’t match my skills and qualifications`


After that, it goes to the filter to keep the **useful job offers** and neglect the not useful job offers.

when the data that comes out is only useful now, it goes to `LLM Chains` to create the job application for the companies, **It gathers info about the company and generate it**,   
**and also creates the right schema of the Email that’ll be sent to the companies**.   

The final step is feeding the data that comes from the final node into the email to send the job applications to the **useful job offer**  
