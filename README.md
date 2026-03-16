# Automated Client Assessment and Report Delivery Pipeline

## Problem Solved
Assessment reports were being generated and delivered manually, 
taking hours per client. This system automates the entire process 
from payment to report delivery with zero human involvement.

## How It Works
1. Client completes payment via Stripe
2. System sends confirmation email with Typeform assessment link
3. Client submits the assessment form
4. Claude AI generates a personalized business assessment report
5. Report is converted to PDF automatically
6. Client receives PDF download link via email within minutes

## Workflow Architecture
```
Stripe Webhook → Gmail (send Typeform link)
Typeform Webhook → Extract Answers → Claude API → Format Report → HTML to PDF → Gmail (send report)
```

## Tech Stack
- **Orchestration:** n8n
- **Payment:** Stripe webhooks
- **Form:** Typeform webhooks
- **AI:** Anthropic Claude API (claude-sonnet-4)
- **PDF Generation:** pdfmunk
- **Email:** Gmail
- **Language:** JavaScript (n8n Code nodes)

## Key Features
- Fully automated end-to-end — zero manual steps
- Professional HTML report formatting
- PDF generation and secure cloud storage
- Automatic email delivery with download link
- Two separate workflows connected by email

## Sample Output
Client receives a multi-page PDF report including:
- Executive Summary
- Challenge Analysis
- Key Recommendations
- Action Plan
- Conclusion

## Business Value
- Eliminates 2-3 hours of manual report generation per client
- Delivers reports within minutes instead of hours
- Scales to unlimited clients without additional staff
