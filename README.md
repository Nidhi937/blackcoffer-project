# blackcoffer-project
### Instructions Documentation

#### 1. Explaining the Approach

The solution is designed to extract text data from articles, analyze the textual content, and compute various linguistic and sentiment metrics, saving the results into an Excel file.

- Data Input:
  - The program reads an input Excel file (`Input.xlsx`) that contains article `URL_ID` and `URL` columns.
  
- Text Extraction:
  - For each URL, the content is fetched using the `requests` library.
  - BeautifulSoup parses the HTML to extract the title and main content of the article.

- Text Analysis:
  - The extracted text undergoes analysis to compute metrics like positive/negative sentiment scores, polarity, subjectivity, readability (e.g., Gunning Fog Index), word count, and personal pronouns.
  - The analysis leverages libraries like NLTK and VADER (Sentiment Analysis).

- Output:
  - All input data and computed metrics are combined into a DataFrame.
  - The results are saved into an output Excel file (`Output_Data.xlsx`).

---

#### 2. How to Run the `.py` File

##### Prerequisites:
- Install Python 3.7 or later.
- Ensure internet access for downloading NLTK resources and fetching articles from URLs.
- Upload required files to Google Drive or place them in the appropriate local directory.

##### Step-by-Step Execution:
1. Set Up Environment:
   - Install dependencies using `pip`:
     ```bash
     pip install nltk openpyxl requests beautifulsoup4
     ```

2. Download NLTK Resources:
   - In your script, NLTK resources like `punkt`, `stopwords`, and `vader_lexicon` will be downloaded automatically.

3. Prepare Input File:
   - Ensure the input Excel file (`Input.xlsx`) contains the columns:
     - `URL_ID`: Unique identifier for each article.
     - `URL`: The web address of the article.

4. Upload Files to Google Drive:
   - Place the `Input.xlsx` file in Google Drive under the path:
     `/My Drive/Input.xlsx`

5. Run the Script:
   - Execute the Python script in Google Colab or your local environment. For Colab:
     - Copy the script into a Colab notebook cell and run it.
     - Ensure Google Drive is mounted (`drive.mount()`).

6. Check the Output:
   - The results will be saved to:
     `/My Drive/Colab Notebooks/Text_Analysis/Output_Data.xlsx`

---

#### 3. Dependencies Required

The solution depends on the following Python libraries:

1. Core Libraries:
   - `os` and `pandas`: For file handling and data manipulation.
   - `requests`: For fetching web pages.
   - `BeautifulSoup` (from `bs4`): For parsing HTML.

2. NLTK Libraries:
   - `punkt`: Tokenizer for sentences and words.
   - `stopwords`: For filtering common words.
   - `vader_lexicon`: Pre-built lexicon for VADER sentiment analysis.

3. Installation Commands:
   - Use the following commands to install all dependencies:
     ```bash
     pip install nltk openpyxl requests beautifulsoup4
     ```

4. Environment Setup:
   - If running in Google Colab, ensure Google Drive is mounted for saving output files:
     ```python
     from google.colab import drive
     drive.mount('/content/drive')
     ```

---

