textSearch Demo
===============

textSearch is a single-page demo app for anyone who need to quickly extract key text from document.

What it does
------------
- Accepts pasted content.
- Accepts uploaded TXT, DOCX, and text-based PDF files.
- Extracts any five text:
- Shows the extracted text in a simple table.
- Displays "Not Found" when a clause is missing.
- Lets reviewers manually edit any extracted value.
- Shows an AI Explanation for each clause explaining why it was or was not identified.
- Logs key demo events to the browser console:
  - contract_uploaded
  - terms_extracted
  - clause_validated
  - ai_rewrite_requested
- Shows an Impact tab with metrics, tracked events, and a visible disclaimer.

Files in this folder
--------------------
- index.html: The app page.
- readme.txt: This guide.

How to run it
-------------
Option 1: Open the app directly
1. Open index.html in a web browser.
2. Paste contract text or upload a supported file.
3. Click "Extract Clauses."

Option 2: Run a local preview server
1. Open a terminal in this folder.
2. Run:

   python3 -m http.server 8000

3. Open this URL in a browser:

   http://127.0.0.1:8000/index.html

4. Paste contract text or upload a supported file.
5. Click "Extract Clauses."

Demo script
-----------
1. Open textsearch.
2. Click "Load Sample."
3. Provide 5 text you want to search.
4. Point out that all five target texts are extracted into the table.
5. Click "Clear."
6. Paste a short contract snippet that only includes one or two text.
7. Click "Extract Clauses."
8. Point out that missing clauses display "Not Found."
9. Click "AI Explanation" under a clause name to show the reasoning for that result.
10. Hover over an extracted value and click "Edit Value."
11. Change the text in the editor, then click "Save" to update the table.
12. Click "Validate" on a found clause to update the validation and accuracy metrics.
13. Click "AI Rewrite" on a found clause to log rewrite usage and shorten the displayed clause text.
14. Open the "Impact" tab.
15. Show the headline metrics, simple metrics, tracked events, and disclaimer.
16. Upload a DOCX, TXT, or text-based PDF contract to show the file upload workflow.

Sample text for a quick demo
-------------------------------------
Master Services Agreement

1. Term. This Agreement begins on July 1, 2026 and continues for an initial term of twelve months. The Agreement renews for successive one-year periods unless either party gives notice at least thirty days before the end of the then-current term.

2. Payment. Customer will pay Provider the fees listed in each statement of work. Provider may invoice monthly, and all undisputed amounts are due within thirty days after Customer receives an invoice.

3. Termination. Either party may terminate this Agreement for material breach if the breach remains uncured thirty days after written notice. Customer may terminate any statement of work for convenience on sixty days' written notice.

4. Limitation of Liability. Except for excluded claims, each party's aggregate liability arising out of this Agreement will not exceed the fees paid or payable under the applicable statement of work during the twelve months before the claim.

5. Indemnification. Provider will defend, indemnify, and hold harmless Customer from third-party claims alleging that the services infringe intellectual property rights.

Missing clause demo text
------------------------
Consulting Agreement

Payment. Client will pay invoices within 15 days.

Termination. Either party may terminate on written notice.

Expected result:
- Term: Not Found
- Payment: Found
- Termination: Found
- Liability Cap: Not Found
- Indemnity: Not Found

Supported uploads
-----------------
- TXT files
- DOCX files
- PDFs with selectable text

Important limitation
--------------------
Scanned image PDFs usually do not contain selectable text. Those files need OCR before ClauseLens can extract clauses from them.

Notes for demoing
-----------------
- The app runs entirely in the browser.
- No contract text is sent to a server by this demo.
- The extraction and explanation logic is rule-based and meant for demo purposes, not legal advice or a final contract review.
- The Impact tab assumes manual review takes 20 minutes and uses validated clauses as the accuracy proxy.
