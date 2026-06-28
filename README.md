# GenAI Projects — Multimodal Invoice Q&A

A Streamlit application that answers natural-language questions about uploaded **invoice images** using Google's **Gemini 1.5 Flash** multimodal model. Upload an invoice, ask a question ("What is the total amount?", "Who is the vendor?"), and the model reads the image and responds.

## What it does

- Accepts an image upload (`.jpg`, `.jpeg`, `.png`) through a Streamlit UI.
- Sends the image plus a user prompt to Gemini 1.5 Flash via `google-generativeai`.
- Uses a system prompt that primes the model as an invoice-understanding expert.
- Returns a grounded, image-aware answer.

## Tech stack

| Component | Library |
|---|---|
| LLM | `google-generativeai` (Gemini 1.5 Flash) |
| UI | `streamlit` |
| Image handling | `Pillow` |
| Config | `python-dotenv` |

## Run locally

```bash
pip install -r requirements.txt

# Create a .env file with your key
echo "google_api_key=YOUR_GEMINI_API_KEY" > .env

streamlit run app.py
```

Then open the local URL Streamlit prints, upload an invoice, type a question, and click **Tell me about the image**.

## Notes

This is a focused demo of multimodal prompting (vision + text) for document understanding. The same pattern extends to receipts, forms, and other structured documents.
