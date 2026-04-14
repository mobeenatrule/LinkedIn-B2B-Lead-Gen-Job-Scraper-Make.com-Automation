# LinkedIn-B2B-Lead-Gen-Job-Scraper-Make.com-Automation

WHAT THIS SCENARIO DOES

This scenario runs a fully automated B2B lead generation pipeline. Here is the exact flow:

1. Scrape LinkedIn Jobs
Calls the Apify LinkedIn Jobs Scraper to pull recent postings. Title, location, and time range are fully configurable.

2. Iterate and Filter
Iterates every job and drops any posting whose title contains "recruiter" or "agency," keeping only direct employer leads.

3. Deduplication Check
Searches an existing Google Sheet database by Job ID to skip leads already processed in previous runs.

4. Company Enrichment via Apollo
Searches Apollo for the hiring company by name and matches it using LinkedIn UID to ensure accuracy.

5. Founder / CEO Lookup via Apollo
Queries Apollo People Search scoped to that organization for roles: Founder, Co-Founder, CEO, and Chief Executive Officer.

6. Unlock Contact Details
Uses Apollo's People Match endpoint to retrieve the full contact record including email address.

7. Email Validity Check via Emailable
Verifies the email with SMTP and Accept-All checks enabled.

8. Dual-Route Storage
- Deliverable email → added to the Jobs sheet (clean, outreach-ready leads)
- Non-deliverable or missing email → added to the Raw Leads sheet for manual review or LinkedIn outreach

Columns stored: Job Title, Job ID, Company Name, Founder Name, Email, Job URL, Posted Date, Scraped Date.


WHO SHOULD USE THIS

Freelancers, agencies, or sales teams doing outbound B2B prospecting who want a continuously refreshed, pre-qualified lead list with verified founder emails — without touching LinkedIn manually.


PREREQUISITES

- Apify account with the LinkedIn Jobs Scraper actor
- Apollo.io account
- Emailable account
- Google Sheets with two tabs: Jobs and Raw Leads

<img width="1796" height="624" alt="image" src="https://github.com/user-attachments/assets/0fc8b4fc-11a2-44b3-8627-9deacf475732" />

