# DataTools
Data tools that can be used by companies to find, clean and analyse data
/ Google Places → Excel Export

// Description
This project automatically searches business locations (e.g., NESTLE, DANONE) in a given location (e.g., France) using the Google Places API.
For each location, it retrieves:

Name

Address

Place ID

Phone number

Website

Then it exports all data to an Excel (.xlsx) file.

Useful for:

B2B prospecting

Enriching a business database

Analyzing company presence by region

Automating local contact searches

// Technologies Used

Python 3

Google Places API (Text Search + Place Details)

requests (HTTP requests)

openpyxl (Excel read/write)

// Installation

/// 1. Clone or download the project

git clone https://your-repo.git
cd your-project


/// 2. Create a virtual environment (recommended)

python -m venv venv
# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate


/// 3. Install dependencies

pip install requests openpyxl


// Configuration — Google API Key

The script uses the Google Places API, which requires an API key.

Steps:

Go to Google Cloud Console: https://console.cloud.google.com/

Create a project (if you haven’t already).

Enable Places API.

Go to APIs & Services → Credentials.

Create an API key.

Copy it.

Insert it into the script:

GOOGLE_API_KEY = 'YOUR_API_KEY_HERE'


⚠️ Never share your API key publicly.

// Usage

Open the Python file.

Modify the companies list:

companies = ["NESTLE", "DANONE"]


Modify the location:

location = "France"


Set the Excel save path:

save_excel_file(workbook, "C:/Users/Sarra/Desktop/Locations.xlsx")


Run the script:

python script.py


// Output

An Excel file will be generated with the columns:

Company	Site Name	Address	Phone Number	Website

Each row corresponds to a site found via Google Places.

// How It Works

/// 1. Search business sites (Text Search API)

find_business_sites(company_name, location)


Sends a request to Google Places

Retrieves all matching places

Extracts name, place_id, and address

/// 2. Get place details (Place Details API)

get_place_details(place_id)


Retrieves phone number, website, full address

/// 3. Create Excel file

create_excel_file()


Creates a new Excel workbook

Adds a sheet named "Business Sites"

Adds header row

/// 4. Add rows & save

sheet.append(row)
save_excel_file(workbook, "path_to_file.xlsx")


// Limitations / Important Notes

Google may charge beyond a certain quota → monitor Cloud Console.

Some locations may have no phone number or website.

The script only retrieves the first page of results (no pagination).

Internet connection is required.

// Possible Improvements

Full pagination support (next_page_token)

Automatic sleep between requests to respect Google rate limits

Error handling with try/except

Export to CSV or database

Read input companies from Excel for hundreds of entries

// Author
Script by Sarra, documented professionally.
Can be adapted for production-ready use if needed.
