# Task 3: Flipkart Product Web Scraper

This project allows users to **search for products on Flipkart**, scrape key details like product name, price, and rating, and **save them to an Excel file**.  
It demonstrates basic **web scraping** using Python and `BeautifulSoup`.

---

## ✔️ Description

- Users enter a product name (e.g., "iPhone 13").
- The script fetches results from Flipkart's search page.
- Extracts the product **title**, **price**, and **rating**.
- Stores the results into `flipkart_products.xlsx`.

## 🧠 Technologies Used

- `requests` – to fetch Flipkart pages  
- `BeautifulSoup` – to parse HTML content  
- `pandas` – to create and save tables  
- `openpyxl` – to write Excel files

---

## 🚀 How to Run

1. Install dependencies:

```bash
pip install requests beautifulsoup4 pandas openpyxl


#Code Overview
Flipkart URL construction
search = input("Enter product: ").replace(" ", "+")
url = f"https://www.flipkart.com/search?q={search}"

#Scraping logic
name_tag = product.find("div", {"class": "_4rR01T"})
price_tag = product.find("div", {"class": "_30jeq3 _1_WHN1"})
rating_tag = product.find("div", {"class": "_3LWZlK"})
#Save to Excel
df = pd.DataFrame({
    'Product Name': names,
    'Price': prices,
    'Rating': ratings
})
df.to_excel("flipkart_products.xlsx", index=False)
