# GSynergy Challange(PySpark on Google Colab)

## 📌 Challange Overview
This Challange processes sales transactions using PySpark and generates ER Diagram

## 🛠 How to Run
1. Open [Google Colab](https://colab.research.google.com/).
2. Upload the given gsynergy_challange.ipynb file in the colab.
3. Run "shift + enter" to execute the pipeline.

## 📂 File Structure
- `gsynergy_challange.ipynb` - Executes the full pipeline.
- `data_path = "/content/sample_data/data"` - Contains raw transaction files.


## 🚀 Features
✔ Data validation  
✔ Incremental processing  
✔ Aggregation for reports
✔ Incremental data

## 🚀 ER Diagram Code :
Table product_category {
  category_id BIGINT [primary key]
  category_name VARCHAR
}

Table product_subcategory {
  subcategory_id BIGINT [primary key]
  category_id BIGINT [ref: > product_category.category_id]
  subcategory_name VARCHAR
}

Table product_brand {
  brand_id BIGINT [primary key]
  subcategory_id BIGINT [ref: > product_subcategory.subcategory_id]
  brand_name VARCHAR
}

Table product {
  sku_id BIGINT [primary key]
  brand_id BIGINT [ref: > product_brand.brand_id]
  product_name VARCHAR
}

Table store {
  pos_site_id BIGINT [primary key]
  region VARCHAR
  state VARCHAR
  city VARCHAR
  store_name VARCHAR
}

Table time {
  fsclwk_id BIGINT [primary key]
  year INT
  month INT
  week INT
}

Table fact_sales {
  transaction_id BIGINT [primary key]
  pos_site_id BIGINT [ref: > store.pos_site_id]
  sku_id BIGINT [ref: > product.sku_id]
  fsclwk_id BIGINT [ref: > time.fsclwk_id]
  price_substate_id INT
  type VARCHAR
  sales_units INT
  sales_dollars FLOAT
  discount_dollars FLOAT
}

2. paste the above given code in the given link  **https://dbdiagram.io/d**

Thank You
S Manoj
