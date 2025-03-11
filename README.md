# Car Listings Scraper

This project is a web scraper designed to extract car listing data from [mashina.kg](https://mashina.kg). The scraper collects information such as car brand, price, seller details, and additional vehicle configurations, and saves the extracted data in a JSONL file.

## Features
- Scrapes multiple pages of car listings
- Extracts detailed information including price, views, seller details, and vehicle specifications
- Stores the scraped data in `data/dataset.jsonl`
- Uses `BeautifulSoup` for HTML parsing
- Displays progress with `tqdm`

## Prerequisites
Ensure you have the following installed on your system:
- Python 3.x
- `git` (for cloning the repository)

## Installation and Setup
### 1. Clone the repository
```sh
git clone https://github.com/AijanB/parser_cars.git
cd parser_cars
```

### 2. Create a Virtual Environment
Create and activate a virtual environment to manage dependencies.
```sh
python -m venv venv
```
- On macOS/Linux:
  ```sh
  source venv/bin/activate
  ```
- On Windows:
  ```sh
  venv\Scripts\activate
  ```

### 3. Install Dependencies
```sh
pip install -r requirements.txt
```

## Usage
### Step 1: Run `get_links.py` to collect listing URLs
```sh
python get_links.py
```
Enter the number of pages you want to scrape when prompted. The script will generate `data/links.json` containing links to individual car listings.

### Step 2: Run `main.py` to scrape listing details
```sh
python main.py
```
This will process each URL in `data/links.json`, extract relevant details, and store them in `data/dataset.jsonl`.

## Output
The extracted data is stored in `data/dataset.jsonl` in JSON format, where each line represents a separate car listing with details such as:
```json
{
  "brand_": "Toyota Camry",
  "USD_price": "$20,000",
  "KGS_price": "1,800,000 KGS",
  "name": "John Doe",
  "number": "+996 555 123456",
  "views": "1200",
  "heart": "45",
  "comments": "10",
  "link": "https://m.mashina.kg/some-listing",
  "current_time": "2025-03-11 12:00:00"
}
```

## Dependencies
The required Python packages are:
```sh
requests
beautifulsoup4==4.13.3
tqdm
```
They are listed in `requirements.txt`, which can be used to install them easily.

## License

## Author
Aijan Batyrkanova