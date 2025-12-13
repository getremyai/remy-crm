# Remy CRM

A single-page restaurant sales CRM built with React for tracking commercial activity and managing the sales pipeline.

## Features

### Dashboard
- **Quick Notes** - Rapidly add notes to any restaurant from the dashboard
- **Key Metrics** - Total restaurants, live clients, pipeline count, overdue actions, and lost deals
- **Next Contacts** - Priority list of upcoming follow-ups with overdue highlighting
- **Pipeline Funnel** - Visual breakdown of leads across funnel stages with conversion rates

### Pipeline Management
- **Kanban Board** - Drag-and-drop cards between stages to update deal status
- **11 Pipeline Stages**: Identified → Call 1 Scheduled → Call 1 Done → Call 2 Scheduled → Call 2 Done → Proposal Sent → Accepted → Trial → Live Client / Lost / Passive
- **Stage Aging** - Visual indicators for deals exceeding target time in stage
- **6-Month Revenue Forecast** - Stacked bar chart with confidence bands (Commit 85%, Best Case 50%, Pipeline 25-40%)
- **Weighted Pipeline Value** - Probability-adjusted deal values based on stage conversion rates
- **Filters** - Filter by table count, next contact date, trial date, or overdue status

### Restaurant Management
- **Full Restaurant Profiles** - Name, group/chain, contact info, website, postcode, table count
- **Booking System Tracking** - OpenTable, Resy, SevenRooms, TheFork, ResDiary, Quandoo, Tablein, etc.
- **Target Monthly Fee** - Track expected revenue per restaurant (auto-calculates annual contract value)
- **Trial Date Tracking** - Monitor trial periods
- **Integrations & Channels** - Track POS integrations and communication channels
- **Notes History** - Timestamped notes with full history

### Contact Management
- **Separate Contact Database** - Contacts exist independently and can be linked to multiple restaurants
- **Contact Details** - Name, role, email, phone, mobile, LinkedIn
- **Many-to-Many Relationships** - Link contacts to multiple restaurants and vice versa
- **Contact Notes** - Separate notes history per contact

### Data Persistence
- **Google Sheets Backend** - All data synced to Google Sheets via Apps Script
- **Real-time Sync** - Changes saved immediately to the cloud
- **Refresh** - Pull latest data from Google Sheets

## Tech Stack
- **React 18** (via CDN)
- **Babel** (in-browser JSX transformation)
- **Google Apps Script** (backend API)
- **Google Sheets** (database)

## Setup

1. Create a Google Sheet with two tabs: `Restaurants` and `Contacts`
2. Deploy the Google Apps Script (see script configuration in the app)
3. Update `GOOGLE_SCRIPT_URL` in `index.html` with your deployed script URL
4. Open `index.html` in a browser or deploy to any static hosting

## Pipeline Stage Configuration

| Stage | Target Days | Conversion Rate |
|-------|-------------|-----------------|
| Identified | 14 | 15% |
| Call 1 Scheduled | 7 | 25% |
| Call 1 Done | 7 | 30% |
| Call 2 Scheduled | 7 | 35% |
| Call 2 Done | 7 | 40% |
| Proposal Sent | 21 | 50% |
| Accepted | 7 | 85% |
| Trial | 20 | 85% |
| Live Client | - | 100% |
| Lost | - | 0% |
| Passive | - | 0% |
