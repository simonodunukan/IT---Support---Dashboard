# System Architecture

## Overview

IT Support Dashboard is a web based ticketing system for managing IT support requests.

## Technology Stack

- **Frontend:** HTMLS, CSS3, Vanilla JavaScript
- **Backend:** Python 3.x with Flask framework
- **Database:** SQLite (development), PostgreSQL (production)
- **Deployment:** AWS (EC2 + RDS)
- **Version Control:** Git/GitHub

## Database Schema

### Tickets Table
- id (Primary Key, Auto-increment)
- title (Text, 200 chars max)
- description (Text)
- status (Text: Open/In Progress/Resolved)
- priority (Text: Low/Medium/High)
- created_at (Timestamp)
- updated_at (Timestamp)
- user_email (Text)

### Knowledge Articles Table
- id (Primary Key, Auto-increment)
- title (Text)
- solution (Text)
- category (Text)
- created_at (Timestamp)

## User Flows

### Submit Ticket Flow
1. User visits /submit-ticket
2. Fills out form (email, title, description, priority)
3. Clicks "Submit"
4. Backend validates data
5. Ticket saved to database
6. User sees confirmation message

### View Tickets Flow
1. User visits /view-tickets
2. Backend queries database for all tickets
3. Tickets displayed in chronological order
4. User can filter by status or priority

## Security Considerations

- Input validation on all forms
- SQL injection prevention (using ORM)
- XSS protection (escaped output)
- Rate limiting on submission endpoint

## Future Enhancements

- User authentication (login system)
- Email notifications when ticket status changes
- File attachments for tickets
- Admin dashboard for support staff
- Ticket assignment system
- Analytics/reporting
