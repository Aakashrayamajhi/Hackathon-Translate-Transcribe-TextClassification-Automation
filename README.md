# n8n Complaint Classification Workflow

This repository contains an n8n workflow that classifies complaints into multiple categories and returns a structured JSON response for each complaint.

## Workflow Overview

The workflow performs the following steps:

1. **Receive Complaint:**  
   Incoming POST requests are received via the `Webhook` node with complaint data.

2. **Preprocess Complaint:**  
   The `AI Agent` node translates and normalizes the text to ensure it is in English.

3. **Classify Complaint:**  
   The `Text Classifier` node categorizes complaints into:
   - Electricity
   - Road
   - Water
   - Transportation
   - Police
   - Fire
   - Cyber
   - Waste
   - Hospital

4. **Format Structured JSON:**  
   Category-specific agents (e.g., `electricity agent`) format the complaint into a structured JSON, including the authority type.

5. **Send Response:**  
   The structured complaint is sent back to the caller via `Respond to Webhook` nodes.

## Example Input
```json
{
  "text": "There is a power outage since morning",
  "complaintId": "12345"
}
