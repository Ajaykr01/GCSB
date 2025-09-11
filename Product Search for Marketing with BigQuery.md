## ⚠️ Disclaimer

This script and guide are provided for the educational purposes to help you understand the lab services and boost your career. Before using the script, please open and review it to familiarize yourself with Google Cloud services. Ensure that you follow 'Qwiklabs' terms of service and YouTube’s community guidelines. The goal is to enhance your learning experience, not to bypass it.

## ©Credit

DM for credit or removal request (no copyright intended) ©All rights and credits for the original content belong to Google Cloud Google Cloud Skill Boost website 🙏

### 1. Load CSV data into BigQuery:
```sh
bq load --source_format=CSV --skip_leading_rows=1 --autodetect products.products_information gs://qwiklabs-gcp-04-2ca0d3863f4c-bucket/products.csv
```

### 2. Create a search index
```sh
bq query --use_legacy_sql=false 'CREATE SEARCH INDEX product_search_index ON products.products_information(ALL COLUMNS)'
```

### 3. Run Search Query
```sh
bq query --use_legacy_sql=false 'SELECT * FROM products.products_information WHERE SEARCH(products_information, "22 oz Water Bottle")'
```
