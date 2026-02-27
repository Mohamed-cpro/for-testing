
# 📚 Web Scraping Task – Books to Scrape

This branch contains a web scraping task implemented using a Jupyter Notebook.  
The project extracts book data from the demo website:

🔗 https://books.toscrape.com/catalogue/page-1.html  

<img width="1889" height="997" alt="image" src="https://github.com/user-attachments/assets/ba01d8c2-8ff9-45a3-889a-96c8427ada12" />


The scraped data is then cleaned and saved into a CSV file for further analysis.


---

## 📁 Branch Contents
```
deep-neural-network-Task/
├── scraping_notebook.ipynb # Web scraping implementation
├── data.csv # Extracted data
└── README.md # Documentation
```
---

## 🎯 Objective

- Connect to a target website
- Extract specific data elements
- Clean and structure the data
- Export results into a CSV file

---
## 🌐 Target Website

This project scrapes data from:

**Books to Scrape**  
A demo website built specifically for practicing web scraping techniques.

Data extracted may include:
- 📖 Book Title
- 💷 Price
- ⭐ Rating
- 📦 Availability
- 🔗 Product Link

---

## 🛠️ Technologies Used

- Python 🐍
- Jupyter Notebook
- requests
- BeautifulSoup
- pandas

---

## 🔎 What the Notebook Does

✔️ Sends HTTP request to the website  
✔️ Parses HTML content  
✔️ Extracts required information  
✔️ Cleans the data  
✔️ Saves results into a CSV file  

---

## 🚀 How to Run

1. Clone the repository:
 ```
 git clone https://github.com/Mohamed-cpro/for-testing.git
 ```
   
2. Switch to this branch:
```
git checkout deep-neural-network-Task
```

Install dependencies:
```
pip install requests beautifulsoup4 pandas notebook
```

Run Jupyter Notebook and Open the notebook and run all cells


Output: 
```data.csv```

1. Exploratory Data Analysis (EDA)
Analyze pricing distribution, rating patterns, and availability trends.

2. Data Visualization
Create charts such as price histograms, rating distribution plots, and stock availability insights.

3. Machine Learning Applications:
Price prediction models
Book rating classification
Availability forecasting

4. Business Reporting & Insights
Generate summaries, dashboards, or performance reports based on scraped data.
---------------------
Notes

Make sure you have internet access while running the notebook.

Always respect website terms of service before scraping.

Add headers if required to avoid request blocking.

Author Mohamed







   
