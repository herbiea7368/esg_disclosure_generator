# ESG Disclosure Generator for SMEs  
**Brand: Vidler & Co**  
MVP build — August 2025

---

## Overview  

The ESG Disclosure Generator is a SaaS tool that helps SMEs produce **jurisdiction-compliant ESG disclosures** (EU CSRD/ESRS, UK TCFD/SRS, US California SB-253/261, etc.).  

- **Problem:** SMEs face growing ESG reporting obligations but lack resources and budget for enterprise tools like Diligent or EcoVadis.  
- **Solution:** Guided intake → rules engine → jurisdiction-specific report generator (PDF, Word, JSON/XBRL).  
- **Business Model:** Freemium entry → paid tiers ($29–499+/mo).  
- **Branding:** UX/UI styled after [Vidler & Co](https://www.vidlerco.com/) (dark, minimalist, premium).  

---

## Core Features (MVP)  

1. **Jurisdiction Selector & Rules Engine**  
   - EU CSRD/ESRS, UK TCFD/SRS, US (CA SB-253/261), MENA exchanges, Asia (SGX, HKEX, India BRSR, Malaysia NSRF).  
   - Feature flags for regulatory changes (e.g., EU “omnibus” simplification).  

2. **Guided Data Intake**  
   - Governance, risk, workforce, policies.  
   - GHG Scopes 1–2 actuals, Scope 3 per 15 categories (estimation methods + data quality grading).  

3. **Report Generator**  
   - PDF/Word reports branded Vidler & Co.  
   - JSON/XBRL exports for machine-readability.  

4. **Freemium → Paid Path**  
   - Free ESG readiness checker.  
   - Paid plans unlock full compliance reports, benchmarking, and integrations.  

---

## Tech Stack  

**Frontend**  
- [Next.js](https://nextjs.org/)  
- [TailwindCSS](https://tailwindcss.com/)  
- Branding alignment: dark theme, muted palette, serif/sans typography  

**Backend**  
- [FastAPI](https://fastapi.tiangolo.com/) (Python) *or* [NestJS](https://nestjs.com/) (Node.js)  
- PostgreSQL for structured ESG data  
- Rules Engine service (JSON schema based)  

**Document Generation**  
- Jinja/Handlebars templates → PDF/Word via Pandoc/DocSpring  
- JSON → XBRL mapper for ESRS tagging  

**Hosting & Compliance**  
- EU cloud (AWS Frankfurt / Azure West Europe)  
- GDPR: encryption at rest, explicit consent, data minimisation  

---

## No-Code MVP Option (4–6 weeks)  

- Airtable or Google Sheets for data storage  
- Retool or Bubble for UI  
- DocSpring for PDF generation  
- Stripe for billing  

---

## Development Timeline  

- **Weeks 1–2:** Wireframes, rules engine logic, JSON schema  
- **Weeks 3–4:** Intake form + jurisdiction selector  
- **Weeks 5–6:** Report generator (PDF/Word)  
- **Weeks 7–8:** Scope 3 workflows + XBRL JSON export  
- **Week 9:** Freemium checker + Stripe billing  
- **Week 10:** Beta launch (UK/EU SMEs)  

---

## Setup (for developers)  

1. **Clone the repo**  
   ```bash
   git clone https://github.com/vidlerco/esg-disclosure-generator.git
   cd esg-disclosure-generator

