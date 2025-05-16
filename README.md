# HackCSB-2.0

HackCSB 2.0 
 Project Overview
HackCSB 2.0 is not just another hackathon—it's a movement. We are building a robust, scalable, and secure registration system for HackCSB.com using modern web technologies. The system will handle user onboarding, application vetting, and payment—seamlessly integrated and largely automated.
Key Goals
- Build a modern, performant website using Next.js
- Collect registrations via embedded Google Forms
- Use Zapier for workflow automation
- Store applicant data in Firebase Firestore
- Manually verify interest-based answers
- Send ZiNiPay payment links to selected participants
- Ensure secure, scalable, and smooth user experience
Tech Stack Overview
| Category         | Tool / Framework     | Purpose                                |
|------------------|----------------------|----------------------------------------|
| Frontend         | Next.js              | Dynamic and SEO-friendly React framework
| Form Management  | Google Forms         | To collect applicant details
| Automation       | Zapier               | Automate trigger-based workflows
| Database         | Firebase Firestore   | Real-time NoSQL database
| Authentication   | Firebase Auth (opt)  | For admin dashboard login
| Payment          | ZiNiPay              | Payment gateway
| Hosting          | Vercel/Firebase Hosting | Scalable deployment
| Custom Domain    | HackCSB.com          | Registered and configured DNS
System Architecture
User -> HackCSB.com (Next.js) -> Embedded Google Form
      ↘ Zapier Trigger → Firestore
                        ↘ Admin Verification Dashboard (Manual Review)
                            ↘ Approved? → Zapier sends Payment Link via Email/SMS
                                            ↘ Payment via ZiNiPay → Confirmation stored in Firestore
Workflow Breakdown
1. Registration via Google Form:
   - Embedded in /register route
   - Fields: Name, Email, Phone, Background, Experience, Open-ended motivation

2. Zapier Trigger (Zap 1):
   - New submission triggers storage in Firestore and notification to reviewers

3. Manual Verification:
   - Admin dashboard built with Next.js + Firebase

4. Zapier (Zap 2):
   - Approved applicants receive payment link via email/SMS

5. Payment Processing:
   - ZiNiPay handles payment, updates Firestore via webhook or integration
Security Considerations
- Firestore Rules restrict read/write access to admins
- Frontend is read-only for applicant data
- Secure API keys stored via .env and Vercel Secrets
- HTTPS for all communications
Data Schema (Firestore Example)
{
  "applicants": {
    "user_id": {
      "name": "Jane Doe",
      "email": "jane@example.com",
      "answers": {
        "why_join": "I love building things..."
      },
      "status": "approved",
      "paymentLinkSent": true,
      "isPaid": true,
      "timestamps": {
        "submitted": "2025-05-01T10:00:00Z",
        "approved": "2025-05-03T12:00:00Z",
        "paid": "2025-05-04T15:00:00Z"
      }
    }
  }
}
Scalability Plan
- Google Forms and Firestore scale automatically
- Vercel ensures frontend handles high traffic
- Cloud Functions can enhance automation
Milestones & Timeline
| Week | Deliverable                          |
|------|--------------------------------------|
| W1   | Setup Next.js, domain routing        |
| W2   | Embed Form, test Zapier              |
| W3   | Firestore structure & admin panel    |
| W4   | ZiNiPay integration & testing        |
| W5   | Full system testing and deployment   |


**Goals:**
- Educate visitors about HackCSB's mission, vision, and legacy
- Use compelling, hook-style messaging to drive registrations
- Feature testimonials, media highlights (Forbes, UNICEF), and past success stories
- Highlight global expansion, exclusive partnerships, and career-building opportunities
- Clear call-to-action (CTA) buttons to lead users to the registration form

**Key Components:**
- Hero Section: High-impact headline, tagline, and registration CTA
- Why HackCSB: Short, powerful bullets about its impact and uniqueness
- Speaker Showcase: Industry leaders from Google, Microsoft, etc.
- Global Reach: Map or visual of participant spread
- Testimonials: Quotes from past participants, mentors
- FAQ & Support: Quick answers to common questions

The page will be designed in Next.js with responsive UI/UX principles, SEO optimization, and performance considerations for both desktop and mobile users.


