# SEC Company Stock Data Viewer

This project provides a single-page responsive HTML application to view common stock shares outstanding data for publicly traded companies, fetched from the SEC's XBRL API. It supports dynamic data loading based on URL parameters.

## Features

-   Fetches `EntityCommonStockSharesOutstanding` data from the SEC API.
-   Filters data for fiscal years greater than 2020.
-   Calculates and displays the maximum and minimum shares outstanding values within the filtered data.
-   Dynamically updates company information and share data based on a CIK provided in the URL.
-   Responsive design using Tailwind CSS.

## Getting Started

### Prerequisites

YouYou need a web browser to open `index.html`. Due to Cross-Origin Resource Sharing (CORS) restrictions, directly fetching data from the SEC API within a browser might require a proxy. The provided `index.html` uses `https://api.allorigins.win/raw?url=` as a generic CORS proxy. For production environments or consistent access, consider setting up a dedicated proxy server (e.g., using Node.js, Python, or a cloud function) that can handle the `User-Agent` header as per SEC guidance.

### Installation

1.  Save the `index.html` and `README.md` files to a local directory.
2.  Ensure `uid.txt` is also in the same directory if you want to access the linked attachment.

### Usage

1.  **Open the application:**
    Open `index.html` in your web browser. By default, it will display data for Cardinal Health (CIK 0000721371).

2.  **View data for a specific company:**
    Append a CIK parameter to the URL to fetch data for a different company. For example, to view data for Apple Inc. (CIK 0000320193):
    `file:///path/to/your/index.html?CIK=0000320193`
    (Replace `file:///path/to/your/` with the actual path where you saved `index.html`).

    The page title, heading, and share data will dynamically update without a full page reload.

## Project Structure

-   `index.html`: The main single-page application, including HTML structure, Tailwind CSS, and JavaScript for data fetching and DOM manipulation.
-   `README.md`: This file, providing project overview and usage instructions.
-   `LICENSE`: The MIT License covering the project.
-   `uid.txt`: An example attachment file (linked within `index.html`).

## SEC Data Guidelines

When making requests to the SEC API, it is crucial to set a descriptive `User-Agent` header. While the browser's `fetch` API has limitations on setting this header directly, a proxy server should ensure this header is properly set. The `User-Agent` should clearly identify your application and include contact information (e.g., `YourAppName/1.0 YourEmail@example.com`).

## Technologies Used

-   HTML5
-   Tailwind CSS (via CDN)
-   JavaScript (ES6+)
-   SEC XBRL API
-   `https://api.allorigins.win/raw?url=` (as a CORS proxy for demonstration)