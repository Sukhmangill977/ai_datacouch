
# **Data_Couch**

## **Email Training Request Automation**

This project automates the process of handling training requests sent via email. It extracts relevant details, creates a Trello card for tracking, and sends email notifications to both the instructor and the client. The script leverages IMAP for email handling, advanced NLP using Hugging Face Transformers, and the Trello API for task management.

---

## **Features**

- **Email Processing**: Reads unseen emails from Gmail.
- **Advanced Natural Language Processing**:
  - Uses Hugging Face Transformers for accurate extraction of training type, proposed dates, and other details from email content.
  - Fine-tuned models (if required) can handle domain-specific terminology for training requests.
- **Trello Integration**: Creates cards for training requests on a Trello board.
- **Email Notifications**: Sends confirmation emails to both the instructor and the client.

---

## **Technologies Used**

- **Python Libraries**:
  - `imaplib`, `email`: Email handling.
  - `transformers`: For NLP capabilities using Hugging Face.
  - `requests`: API communication with Trello.
  - `smtplib`, `email.mime`: Sending emails.
  - `re`: Regular expressions for data extraction.
  - `dotenv`: Loading environment variables.
- **Trello API**: Task management.
- **Gmail IMAP/SMTP**: Email fetching and sending.

---

## **Advantages of Hugging Face Integration**

- Improved accuracy in extracting structured data from unstructured email text.
- Enhanced support for multilingual and nuanced text processing.
- Scalable solution for various NLP tasks like intent classification, entity extraction, and sentiment analysis.

---

## **Prerequisites**

1. **Python**: Install Python 3.8 or higher.
2. **Environment Variables**: Create a `.env` file in the root directory with the following variables:
   ```env
   EMAIL=<your-email-address>
   PASSWORD=<your-email-password>
   TRELLO_API_KEY=<your-trello-api-key>
   TRELLO_TOKEN=<your-trello-token>
   TRELLO_LIST_ID=<your-trello-list-id>
   BOARD_ID=<your-trello-board-id>
   ```
3. **Hugging Face Model**: Install the Transformers library and download a pretrained model:
   ```bash
   pip install transformers
   ```

---

## **Installation**

1. Clone this repository:
   ```bash
   git clone https://github.com/your-repo/email-training-automation.git
   ```
2. Navigate to the project directory:
   ```bash
   cd email-training-automation
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

---

## **Usage**

1. Update the instructor's email in the script:
   ```python
   INSTRUCTOR_EMAIL = "example@gmail.com"
   ```
2. Specify the Hugging Face model to use:
   ```python
   from transformers import pipeline

   nlp = pipeline("ner", model="dslim/bert-base-NER")  # Example model
   ```
3. Run the script:
   ```bash
   python script_name.py
   ```

---

## **How It Works**

1. **Fetch Emails**:  
   The script connects to the Gmail server and retrieves unseen emails.

2. **Extract Information Using Hugging Face**:  
   The email content is processed using a pretrained model (e.g., `bert-base-cased`) to extract entities like training type, dates, and client details.

3. **Create Trello Card**:  
   Extracted details are used to create a Trello card in the designated board and list.

4. **Send Notifications**:  
   Confirmation emails are sent to the instructor and client.

---

## **Error Handling**

The script handles and prints error messages for:
- Email fetching errors.
- Trello API request failures.
- Hugging Face model loading or inference errors.
- Email sending errors.

---

## **Next Steps**

- Add fine-tuning for domain-specific text processing if needed.
- Enhance logging and monitoring for better debugging and operational tracking.

---

## **Contributing**

Contributions are welcome! Feel free to submit a pull request or create an issue for any bugs or feature requests.

---

## **License**

This project is licensed under the [MIT License](LICENSE).

---

