-- Data Exploration using BigQuery
-- Tujuan: Untuk menganalisis penjualan, kinerja produk, perilaku pelanggan, dan efisiensi operasional di berbagai cabang Walmart. 
-- Analisis ini akan memberikan wawasan yang dapat digunakan untuk meningkatkan strategi penjualan dan operasional.

-- Cabang dan kota mana yang memiliki penjualan tertinggi dan terendah?
SELECT 
  Branch,
  City,
  SUM(Total) AS total_revenue
FROM 
  `walmart.sales`
GROUP BY 1,2
ORDER BY 3 DESC;

-- Mengidentifikasi seberapa banyak Product line terjual dan pendapatan yang dihasilkan
SELECT 
  `Product line`,
  SUM(Quantity) AS total_quantity_sold,
  SUM(Total) AS total_revenue
FROM 
  `walmart.sales`
GROUP BY 1
ORDER BY 3 DESC;

-- Mengidentifikasi tipe pelanggan yang paling sering melakukan pembelian dan nilai rata-rata pembelian mereka.
SELECT 
  `Customer type`,
  COUNT(*) AS total_purchases,
  AVG(Total) AS average_purchase_value
FROM 
  `walmart.sales`
GROUP BY 1
ORDER BY 2 DESC;

-- Menentukan metode pembayaran yang paling sering digunakan.
SELECT 
  Payment,
  COUNT(*) AS payment_count
FROM 
  `walmart.sales`
GROUP BY 1
ORDER BY 2 DESC;

-- Mengidentifikasi pola penjualan berdasarkan waktu dalam sehari dan hari dalam seminggu
-- Menentukan penjualan berdasarkan waktu dalam sehari
SELECT 
  EXTRACT(HOUR FROM `time`) AS hour_of_day,
  SUM(Total) AS total_revenue
FROM 
  `walmart.sales`
GROUP BY 1
ORDER BY 1

-- Menentukan penjualan berdasarkan hari dalam seminggu
SELECT 
  EXTRACT(DAYOFWEEK FROM `date`) AS day_of_week,
  SUM(Total) AS total_revenue
FROM 
  `walmart.sales`
GROUP BY 1
ORDER BY 1

-- Menganalisis pendapatan kotor dan margin kotor per cabang dan per produk.
-- Menentukan pendapatan kotor dan margin kotor per cabang
SELECT 
  Branch,
  SUM(`gross income`) AS total_gross_income,
  AVG(`gross margin percentage`) AS average_gross_margin_percentage
FROM 
  `walmart.sales`
GROUP BY 1
ORDER BY 2 DESC;

-- Menentukan pendapatan kotor dan margin kotor per produk
SELECT 
  `Product line`,
  SUM(`gross income`) AS total_gross_income,
  AVG(`gross margin percentage`) AS average_gross_margin_percentage
FROM 
  `walmart.sales`
GROUP BY 1
ORDER BY 2 DESC;


-- Mengidentifikasi produk dengan rating tertinggi dan terendah.
SELECT 
  `Product line`,
  AVG(Rating) AS average_rating
FROM 
  `walmart.sales`
GROUP BY 1
ORDER BY 2 DESC;

-- Mengidentifikasi perbedaan perilaku pembelian antara pria dan wanita.
SELECT 
  Gender,
  COUNT(*) AS total_purchases,
  SUM(Total) AS total_spent,
  AVG(Total) AS average_purchase_value
FROM 
  `walmart.sales`
GROUP BY 1
ORDER BY 2 DESC;

-- Mengidentifikasi banyak masing masing product line terjual untuk tiap gender 
SELECT 
  `Product line`,
  Gender,
  SUM(Quantity) AS product_sold
FROM 
  `walmart.sales`
GROUP BY 1,2
ORDER BY 3 DESC;

-- Mengidentifikasi kontribusi pajak (VAT) per cabang dan per produk.
SELECT 
  Branch,
  SUM(`Tax 5%`) AS total_VAT
FROM 
  `walmart.sales`
GROUP BY 1
ORDER BY 2 DESC;

-- Menentukan kontribusi pajak per produk
SELECT 
  `Product line`,
  SUM(`Tax 5%`) AS total_VAT
FROM 
  `walmart.sales`
GROUP BY 1
ORDER BY 2 DESC;

