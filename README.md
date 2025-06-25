# -Google_-Image_-Downloader-
PROJECT CATEGORY
# Google Images Search with Python

This project demonstrates how to use the Python package `google_images_search` to automatically search and download images from Google using a query. It includes package installation, setting up API credentials, and writing a simple function to fetch images.

---

## 🔧 Prerequisites

To successfully use this tool, you must have:

- A working Python 3.6+ environment
- Access to Google Custom Search Engine (CSE) and Google Cloud API key
- Internet access for image download

---

## 📦 Installation Steps

To install the required package, run the following command in your Colab or local Python environment:

```bash
!pip install google_images_search
This will also install all necessary dependencies such as:

google-api-python-client

Pillow

requests

python-resize-image

Utility packages like colorama, click, termcolor, pyfiglet

🔐 API Key and CSE Setup
Before using the tool, you need two credentials:

Google Developer API Key

Go to: https://console.cloud.google.com/

Create a new project

Enable the Custom Search API

Generate an API key

Google Custom Search Engine (CSE) ID

Go to: https://programmablesearchengine.google.com/

Create a search engine (select to search across the entire web)

Copy your CSE ID

Replace the placeholders in code with:

python
Copy
Edit
gis = GoogleImagesSearch('YOUR_API_KEY', 'YOUR_CSE_ID', validate_images=True)
🔍 Performing Image Search
Function Breakdown
python
Copy
Edit
def search(keyword, imageNumber):
    _search_params = {
        'q': keyword,
        'num': imageNumber,
    }

    gis.search(search_params=_search_params, path_to_dir='./images/')
keyword: The term to search on Google (e.g., "motorbike")

imageNumber: Number of images to download

_search_params:

'q': Query string for the search

'num': Number of results to return

path_to_dir: Local directory to store the downloaded images (e.g., ./images/)

Example Usage
python
Copy
Edit
search('motorbike', 10)
This will search for 10 images of motorbikes and save them in a folder called images.

📁 Output Directory
All images will be saved to the specified folder.

Ensure the folder exists or will be created automatically.

🧪 Features of google_images_search
Image validation: Option to check if downloaded image is valid (validate_images=True)

Flexible queries: Support for multiple search filters (e.g., size, color, type)

Directory management: Easy saving of images locally

📌 Notes
This package relies on Google APIs, which may have usage quotas.

If you're using this in Google Colab, make sure you have authenticated access and the /images directory exists.

Be respectful of copyright when downloading and using images.

📚 References
Google Images Search PyPI

Google Custom Search JSON API Docs

📞 Troubleshooting
403 Error: Ensure your API key and CSE ID are valid and enabled.

Empty Image Directory: Check that your CSE is configured to search the entire web and not just specific sites.

Rate Limit: Free usage is limited—consider requesting quota increase from Google if needed.

