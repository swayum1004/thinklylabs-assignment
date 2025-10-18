🤖 n8n Cybersecurity Outreach Agent
This is an automated sales and outreach agent built in n8n. The workflow finds companies that had a data breach in 2023, identifies key security contacts (like a CISO or Head of Security), infers their email address, and drafts a personalized outreach email.

This project was built to demonstrate workflow automation, data enrichment, and AI-powered content generation using only free-tier APIs.

✨ Features
Finds Breached Companies: Uses the Serper API to find a list of companies that experienced a data breach in 2023.

Enriches Contacts: Searches for relevant security leaders (CISO, Head of Security) at each company.

AI-Powered Operations: Leverages Google Gemini for all AI tasks:

Extraction: Cleans and structures data from raw search results.

Inference: Infers a contact's most likely email address based on their name and company domain.

Generation: Drafts a personalized, non-salesy outreach email.

Saves to Google Sheets: Appends all collected data (company, domain, contact name, title, inferred email, and draft) to a Google Sheet for review.

⚙️ How It Works (Workflow Steps)
The workflow follows a clear, sequential logic:

Find Breach Articles: (HTTP Request) Searches Serper for articles on 2023 data breaches.

Extract Companies: (Gemini) Reads the search results and outputs a clean JSON array of company names.

Split Out: Loops through the list of companies one by one.

Wait: Pauses for a few seconds to avoid API rate limits.

Find Company Domain: (HTTP Request) Searches for the company's official domain.

Find Security Contact: (HTTP Request) Searches LinkedIn for a CISO or Head of Security at the company.

Extract Contact Details: (Gemini) Parses the search snippet to get the contact's full name and title.

Infer Email Address: (Gemini) Predicts the contact's email address and a confidence score.

Draft Outreach Email: (Gemini) Writes the final, personalized email.

Append to Sheet: (Google Sheets) Saves all the generated data into a new row.

🛠️ Technology Stack
Automation: n8n

AI Model: Google Gemini

Data Sourcing: Serper API

Database: Google Sheets
