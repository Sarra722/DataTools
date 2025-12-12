# README – Python Scripts for Business Data Extraction

## Features
This project contains Python scripts for automatically retrieving business locations, contact details, and website information using the Google Places API, and exporting the data to Excel (.xlsx).

Key features include:

- Search business locations by company name and location
- Retrieve phone numbers, websites, and addresses
- Export results to Excel with headers
- Designed for easy extension with additional scripts in the future

---

## Installation

Clone the repository and create a virtual environment:

```bash
git clone https://your-repo.git
cd your-project
python -m venv venv 
```

### Windows
venv\Scripts\activate
### macOS/Linux
source venv/bin/activate
```bash
pip install requests openpyxl
```

## Environment Variables
The scripts require a Google API Key.

Create a Google Cloud Project and enable Places API.

Create an API key under APIs & Services → Credentials.

Add it to your script:

```bash 
GOOGLE_API_KEY = 'YOUR_API_KEY_HERE' 
```


⚠️ For security, you can also use .env and python-dotenv to load the key.

## Usage/Examples

Edit the companies list and location variable in the script:
```bash
companies = ["NESTLE", "DANONE"]
location = "France"
```

Optionally set the Excel save path:
```bash
save_excel_file(workbook, "C:/Users/Sarra/Desktop/Locations.xlsx")
```

Run the script:
```bash
python script.py
```

## Optimizations
Future improvements may include:

Full pagination support (next_page_token)

Automatic retries and backoff for API rate limits

Input from CSV/Excel for hundreds of companies

Better error handling (try/except)

Logging instead of print statements

Export to database or other formats

## FAQ

- Q: Some sites may have no phone number or website.
A: This depends on publicly available Google Places data.

- Q: Can I search thousands of companies?
A: Yes, but watch Google API quotas and implement throttling.

- Q: Can I use this in production?
A: Yes, but secure your API key and consider optimizations above.

## Authors
Sarra 

https://www.linkedin.com/in/sarra-mahyou-informatique/
