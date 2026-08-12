# JC Triana — Collections

Shows which brokers owe money, how long it's been, and opens a ready-to-send
email for each one. **https://mannycosta.github.io/jc-collections/**

## How it's used

1. Export **Reserve Details** from Integra as a PDF
2. Drop it on the page
3. Brokers with loads 30+ days out are listed oldest first
4. Click one → review the email → **Open in Gmail** → send

Nothing sends by itself. Every email is reviewed before it goes.

## What it remembers

Stored in Supabase, so it follows her between the Mac and the iPad:

- **Broker email addresses** — typed once, prefilled forever after
- **When each broker was last emailed** — anyone contacted in the last 7 days is
  dimmed and tagged `recent`, so nobody gets chased twice
- **Every message sent** — searchable under History, with the full text

## Notes

- A load that disappears from a later report is marked paid automatically. Loads
  can also be marked paid by hand from the broker's panel.
- Emails list the 15 oldest loads and summarise the rest — a 60-load wall of text
  reads as a statement, not a chase, and the Gmail link has a length limit.
- The Supabase key in this page is the *publishable* key, which is meant for
  client-side use. It is not the service-role key.
