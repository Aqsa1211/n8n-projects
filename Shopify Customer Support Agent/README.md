## Tech Stack

![n8n](https://img.shields.io/badge/n8n-Workflow%20Automation-EA4B71?logo=n8n&logoColor=white)
![Shopify](https://img.shields.io/badge/Shopify-Admin%20API-7AB55C?logo=shopify&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-LLM%20%2B%20Embeddings-412991?logo=openai&logoColor=white)
![Retell AI](https://img.shields.io/badge/Retell%20AI-Voice%20Agent-000000?logo=voip&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-Vector%20Store-3ECF8E?logo=supabase&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Google%20Sheets-State%20Storage-34A853?logo=googlesheets&logoColor=white)
![Reamaze](https://img.shields.io/badge/Reamaze-Support%20Inbox-5C6AC4)
![REST API](https://img.shields.io/badge/REST-API-02569B)

# AI Customer Support & Voice Recovery System

An automation system built with n8n that helps Shopify stores:

- Automatically respond to customer emails
- Answer questions using real store policies
- Fetch real order data
- Safely handle refunds with human approval
- Recover abandoned checkouts using AI voice calls

---

# Workflow 1:  AI Customer Support Agent

## What It Does

When a customer sends an email:

1. The system reads the message
2. Classifies the intent (refund, delivery, product question, etc.)
3. Looks up relevant store policies
4. Fetches real Shopify order data (if needed)
5. Drafts an accurate response
6. Sends it — or routes for approval (if it's a refund/return)

---

## Smart Policy & Product Knowledge

Instead of hardcoding rules inside prompts, we upload store knowledge into a vector database.

### Embedded Data Includes:

- Privacy Policy  
- Shipping & Delivery Policy  
- Refund Policy  
- Terms of Service  
- Product catalog (from a Google Sheet)

### Why This Matters

- The AI answers based on **your actual policies**
- No made-up refund rules
- No incorrect shipping timelines
- Accurate product references
- Easy updates (edit the sheet → re-embed → done)

This keeps responses consistent, safe, and reliable.

---

## Real Shopify Order Lookup

When a customer asks about an order:

- The system searches Shopify
- Retrieves order details
- Returns:
  - Items purchased
  - Discounts applied
  - Fulfillment status
  - Shipping info

Responses are based on real data — not guesses.

---

## Refund & Return Safety

Refunds and returns are never automated blindly.

If a message is classified as:
- Refund
- Return

The system:
- Drafts the response
- Requires human approval before sending

This protects revenue and prevents mistakes.

---

## Email Flexibility

This system works with:

- Reamaze API (full conversation control)
- Gmail node in n8n
- IMAP Trigger
- Send Email node

It can run on a helpdesk platform or directly from email.

---

# Workflow #2: Abandoned Checkout Voice Agent

## What It Does

If a customer abandons checkout:

1. The system detects it
2. Generates a one-time customer exclusive discount
3. Logs all data in Google Sheets
4. Places an outbound AI voice call
5. Offers an exclusive incentive valid for 15 min to encourage the customer to proceed with the checkout
6. Sends checkout link + discount via email

---

## Voice Calls (Retell AI)

The outbound calls are created using Retell's phone call API.

We use dynamic variables to personalize the call:

- Customer name
- Customer email
- Discount code
- Checkout URL

This allows real-time personalization inside the voice prompt.

---

## Call → Email Flow

During the call:

- Retell triggers a POST request
- Only the customer email is sent
- n8n receives it
- Matches the customer in Google Sheets
- Retrieves stored discount & checkout link
- Drafts and sends the follow-up email

The email contains the checkout-url with the exclusive discount applied and the discount code, which looks like this:

<img width="559" height="458" alt="image" src="https://github.com/user-attachments/assets/314688d8-1a82-44ff-b5e3-f094e47c6906" />


---

## Google Sheets (Important Layer)

Google Sheets is used to:

- Store customer data
- Map discount codes
- Log calls
- Prevent duplicate outreach
- Control re-contact timing

It acts as the central state system for recovery logic.

---

# Design Principles

- AI answers based on real policies
- Real Shopify data for order replies
- Human approval for financial actions
- No duplicate calls or discounts
- Modular reusable workflows
- Easy to update without rewriting logic

---

# What This Enables

- Faster customer support
- Policy-consistent AI replies
- Order-aware conversations
- Safe refund handling
- Revenue recovery from abandoned carts
- Scalable support without scaling headcount

---

# Setup

1. Import workflows into n8n
2. Connect:
   - Shopify
   - OpenAI
   - Supabase
   - Retell AI
   - Google Sheets
   - Email provider
3. Embed policies & product sheet
4. Activate workflows

---
# 📘 Detailed Tutorial

If you'd like a full technical walkthrough of how this system was built — including:

- Workflow structure in n8n  
- Embedding store policies into Supabase  
- Product data sheet → vector database setup  
- Shopify order lookup logic  
- Human-in-the-loop refund routing  
- Retell voice agent configuration  
- LLM dynamic variables setup  
- Google Sheets mapping strategy  
- POST request tool flow (Retell → n8n)  

You can read the complete step-by-step guide here:

👉 **Full Tutorial on Medium:**  
[Building an AI Customer Support & Voice Recovery System with n8n](https://medium.com/@aqsasif2002)

This article explains the architecture decisions, implementation details, and configuration process in depth.
