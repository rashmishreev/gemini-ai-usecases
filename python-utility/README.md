# Email Parser and Cleaner (Python – Colab Friendly)

This project is a Python utility to parse and clean raw email data, especially useful for datasets exported from Gmail using tools like Thunderbird. The focus is on cleaning the email body and extracting meaningful content by removing headers, footers, signatures, and common noise using regular expressions.

---

## 🛠️ Features

- Removes standard headers (`Subject`, `From`, `To`, `Date`)
- Anonymizes email addresses
- Strips out banners, footers, legal disclaimers, and social media links
- Truncates messages after sign-off phrases like "Best regards"
- Eliminates noise and unwanted phrases (e.g., unsubscribe, cookie policies)
- Cleans up whitespace and formatting

---

## 💡 Use Case

This cleaner was developed for a **GenAI application** to:

- Categorize job application emails
- Prepare cleaned inputs for embedding and RAG-based Q&A
- Enable semantic understanding of email content

---

## 🧪 How to Use (in Colab)

1. **Upload Your Dataset:**  
   The dataset should be a CSV file containing an email body column (e.g., `email_body`, `content`, or similar).

2. **Adjust Column Name:**  
   Modify the script to match your column name (e.g., `df["email_body"]`).

3. **Apply the Cleaning Function:**
   ```python
   from cleaner import clean_email_body

   df["cleaned_body"] = df["email_body"].apply(clean_email_body)
