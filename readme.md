# Reddit Resume Image Scraper

A Python-based web scraper to automatically download resume images from Reddit posts. This script searches for posts related to resumes (e.g., computer science resumes from India) in the [r/resumes](https://www.reddit.com/r/resumes) subreddit and downloads images from these posts.

## Features
- Scrapes Reddit posts with resumes based on a search query.
- Downloads images (supported formats: `.jpg`, `.jpeg`, `.png`, `.webp`) from the posts.
- Saves images in a folder named `downloaded_images`.
- Avoids processing the same post more than once.

## Prerequisites

Make sure you have the following installed:

- Python 3.x
- Chrome browser
- [ChromeDriver](https://googlechromelabs.github.io/chrome-for-testing/) (Ensure the version matches your Chrome version)
- The following Python libraries:
  - `requests`
  - `selenium`

You can install the required libraries using `pip`:

```bash
pip install requests selenium
```

## Usage

1. Clone this repository:

    ```bash
    git clone https://github.com/tejasmistry45/Reddit_Resume_Image_Scraper.git
    cd Reddit_Resume_Image_Scraper
    ```

2. Ensure you have `chromedriver` installed and it matches your installed version of Google Chrome. You can download `chromedriver` from [here](https://googlechromelabs.github.io/chrome-for-testing/).

3. Run the script:

    ```bash
    python scrape_images.py
    ```

   The script will open a Chrome browser window, perform a search for resumes in the `r/resumes` subreddit (specifically for the query "computer science resume india"), and download the images to the `downloaded_images` folder.

## How It Works

1. The script opens the specified Reddit search URL using Selenium.
2. It waits for the search results to load and then processes each post's link.
3. For each post, it opens the link in a new browser tab, waits for the image to load, and then downloads the first image it finds in the post.
4. The images are saved in the `downloaded_images` folder with a unique naming convention (`image1.jpg`, `image2.png`, etc.).
5. After processing each post, the script closes the browser tab and moves on to the next one.
6. The process continues until all posts in the search results have been processed.

## Supported Image Formats
- `.jpg`
- `.jpeg`
- `.png`
- `.webp`

## Folder Structure

```
Reddit_Resume_Image_Scraper/
│
├── scrape_images.py            # Python script to scrape and download images
├── downloaded_images/          # Folder where images will be saved
└── README.md                   # This file
```

## Notes
- Ensure that your `chromedriver` is in your system's PATH or provide the path to it in the script.
- This script uses Selenium WebDriver for Chrome, so you must have Google Chrome installed.

## License
This project is open source and available under the MIT License.

## Acknowledgements
- The script uses Selenium and requests to interact with the web and download images.
- Reddit's terms of service and API policies should be followed when scraping their website.
```

# How to Customize
- Search Query: You can modify the `search_url` in the script to change the search query or subreddit.
- Image Formats: Add or remove image formats from the `supported_extensions` list if you want to support more image types.
