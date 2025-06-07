# Google Maps Scraper (No API)

A simple n8n workflow to extract business websites and emails from Google Maps search results without using the official API.

## Usage

1. Set your search term in the Manual Trigger node (e.g., `{ "Search": "dental" }`).  
2. Click **Execute Workflow**.  
3. Results (emails) will be appended to your configured Google Sheet.

## Nodes Overview

- **Manual Trigger**: Kick off the workflow.  
- **HTTP Request**: Fetch Google Maps HTML.  
- **Code: Website Parser**: Extracts valid map links.  
- **Filter** & **Remove Duplicates**: Keep relevant, unique URLs.  
- **Split In Batches** + **HTTP Request1**: Scrape each link for emails.  
- **Code1**: Parse out email addresses.  
- **Split Out** & **Remove Duplicates1**: Deduplicate emails.  
- **Google Sheets**: Append results to a spreadsheet.

## Source

Based on tutorial: https://www.youtube.com/watch?v=OroDNJl-pyc
