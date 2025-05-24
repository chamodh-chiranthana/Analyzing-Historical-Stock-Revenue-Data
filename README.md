# Stock Data Analysis and Visualization Project

## Overview

This project analyzes historical stock and revenue data for Tesla (TSLA) and GameStop (GME) using Python. The analysis includes data extraction through API calls and web scraping, followed by data processing and visualization to identify trends and patterns in stock prices and company revenue.

## Project Objectives

- Extract historical stock data using the yfinance library
- Collect quarterly revenue data through web scraping
- Process and clean the extracted data
- Create interactive visualizations comparing stock prices with company revenue

## Technologies Used

- **Python 3.x**
- **Libraries**:
  - pandas: Data manipulation and analysis
  - yfinance: Stock data API integration
  - BeautifulSoup4: HTML parsing and web scraping
  - requests: HTTP requests
  - plotly: Interactive data visualization
  - nbformat: Notebook formatting

## Project Structure

The project is structured in a Jupyter notebook with the following key components:

1. **Data Collection**:

   - Stock price data via yfinance API
   - Quarterly revenue data via web scraping

2. **Data Processing**:

   - Cleaning revenue data (removing $, commas)
   - Handling missing values
   - Formatting dates and data types

3. **Data Visualization**:
   - Historical share price charts
   - Quarterly revenue trends
   - Combined dashboard with interactive features

## Setup Instructions

### Option 1: Using Anaconda (Recommended)

1. **Install Anaconda**:

   - Download from [anaconda.com](https://www.anaconda.com/products/distribution)
   - Follow the installation instructions for your operating system

2. **Launch Jupyter Notebook**:

   ```bash
   jupyter notebook
   ```

3. **Open the notebook file**:

   - Navigate to the `Notebooks` folder and open `Final Assignment-v2.ipynb`

4. **Install required packages** if not already included:
   ```python
   %pip install yfinance
   %pip install bs4
   %pip install nbformat
   %pip install --upgrade plotly
   ```

### Option 2: Using Python and pip

1. **Install Python** from [python.org](https://www.python.org/downloads/)

2. **Install Jupyter and required packages**:

   ```bash
   pip install jupyter
   pip install yfinance pandas requests beautifulsoup4 plotly nbformat
   ```

3. **Launch Jupyter Notebook**:

   ```bash
   jupyter notebook
   ```

4. **Navigate to the notebook file** and open it

## Running the Project

1. Execute cells sequentially using Shift+Enter or the Run button
2. The notebook configures plotly to use iframe rendering:
   ```python
   import plotly.io as pio
   pio.renderers.default = "iframe"
   ```
3. If needed, warnings are suppressed using:
   ```python
   import warnings
   warnings.filterwarnings("ignore", category=FutureWarning)
   ```

## Implementation Details

### 1. Stock Data Extraction

The project uses yfinance to download stock data:

- Creates Ticker objects for Tesla and GameStop
- Extracts maximum available historical data
- Processes data into pandas DataFrames

### 2. Revenue Data Extraction

Web scraping is implemented to gather quarterly revenue data:

- Sends HTTP requests to target webpages
- Parses HTML content with BeautifulSoup
- Extracts tabular data with revenue information
- Structures the data into pandas DataFrames

### 3. Visualization

The project includes a custom function `make_graph()` that:

- Creates dual-panel interactive charts
- Shows stock price history in the upper panel (limited to June 2021)
- Displays quarterly revenue in the lower panel (limited to April 2021)
- Includes interactive features like zooming and tooltips

## Troubleshooting

### Visualization Issues

If visualizations don't render properly:

1. Try changing the plotly renderer:
   ```python
   import plotly.io as pio
   pio.renderers.default = "notebook"  # alternatives: "browser", "colab"
   ```
2. Update plotly to the latest version:
   ```python
   %pip install --upgrade plotly
   ```

### Web Scraping Problems

If web scraping fails:

- Check if the source URLs are still valid
- Inspect if webpage structures have changed
- Adjust the BeautifulSoup selectors accordingly

## Credits

This project was developed as part of the IBM Data Science Professional Certificate program.
