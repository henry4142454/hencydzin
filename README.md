import requests
# Replace 'YOUR_DROPBOX_LINK' with your actual Dropbox link (last part should be
'?dl=1'). dropbox_link =
'https://www.dropbox.com/scl/fi/hqtphbi3whiebjee4gzv5/Sales_25bccb9e870b1866
7796173ca059c98f.csv?rlkey=oshkvc59ga01ll8t2f0ozsc0a&st=srehu8l3&dl=1' # Send a GET request to download the file
response = requests.get(dropbox_link)
# Save the content to a local CSV file (optional)
with open('file.csv', 'wb') as f:
f.write(response.content)
# Read the CSV file into a Pandas DataFrame
df = pd.read_csv('file.csv')
# Display the DataFrame
print(df)
1. # Calculate the sum of sales for each product
total_sales_by_product = df.groupby('Product')['Total Sales'].sum()
print(total_sales_by_product)
2. # Determine the best-selling product
best_selling_product = total_sales_by_product.idxmax()
best_sales_value = total_sales_by_product.max()
print(best_sales_value)
print(best_selling_product)
3. total_sales_by_date = df.groupby('Date')['Total Sales'].sum()
best_selling_day = total_sales_by_date.idxmax()
best_sales_value_day = total_sales_by_date.max()
print(best_sales_value_day)
print(best_selling_day)
4. Date Product Quantity Unit Price Total Sales 0 2024-01-01 Widget A 5 10.99 54.95 1
2024-01-01 Gadget B 3 25.50 76.50 2 2024-01-02 Widget A 7 10.99 76.93 3
2024-01-02 Gizmo C 2 15.75 31.50 4 2024-01-03 Gadget B 4 25.50 102.00 5
2024-01-03 Gizmo C 6 15.75 94.50 6 2024-01-04 Widget A 10 10.99 109.90 7
2024-01-04 Gadget B 2 25.50 51.00 8 2024-01-05 Gizmo C 8 15.75 126.00 9
2024-01-05 Widget A 6 10.99 65.94 10 2024-01-06 Gadget B 5 25.50 127.50 11
2024-01-07 Widget A 9 10.99 98.91 12 2024-01-08 Gizmo C 3 15.75 47.25 13
2024-01-09 Widget A 12 10.99 131.88 14 2024-01-10 Gadget B 7 25.50 178.50 15
2024-01-11 Gizmo C 5 15.75 78.75 16 2024-01-12 Widget A 8 10.99 87.92 17
2024-01-13 Gadget B 4 25.50 102.00 18 2024-01-14 Gizmo C 9 15.75 141.75 19
2024-01-15 Widget A 11 10.99 120.89 20 2024-01-16 Gadget B 6 25.50 153.00 21
2024-01-17 Gizmo C 7 15.75 110.25 22 2024-01-18 Widget A 13 10.99 142.87 23
2024-01-19 Gadget B 5 25.50 127.50 24 2024-01-20 Gizmo C 10 15.75 157.50 25
2024-01-21 Widget A 7 10.99 76.93 26 2024-01-22 Gadget B 8 25.50 204.00 27
2024-01-23 Gizmo C 4 15.75 63.00 28 2024-01-24 Widget A 9 10.99 98.91 29
2024-01-25 Gadget B 3 25.50 76.50 30 2024-01-26 Gizmo C 11 15.75 173.25 31
2024-01-27 Widget A 6 10.99 65.94 32 2024-01-28 Gadget B 7 25.50 178.50 33
2024-01-29 Gizmo C 5 15.75 78.75 34 2024-01-30 Widget A 14 10.99 153.86 35
2024-01-31 Gadget B 4 25.50 102.00 36 2024-02-01 Gizmo C 8 15.75 126.00 37
2024-02-02 Widget A 10 10.99 109.90 38 2024-02-03 Gadget B 6 25.50 153.00 39
2024-02-04 Gizmo C 9 15.75 141.75 40 2024-02-05 Widget A 7 10.99 76.93 41
2024-02-06 Gadget B 5 25.50 127.50 42 2024-02-07 Gizmo C 12 15.75 189.00 43
2024-02-08 Widget A 8 10.99 87.92 44 2024-02-09 Gadget B 7 25.50 178.50 45
2024-02-10 Gizmo C 6 15.75 94.50 46 2024-02-11 Widget A 15 10.99 164.85 47
2024-02-12 Gadget B 4 25.50 102.00 48 2024-02-13 Gizmo C 10 15.75 157.50 49
2024-02-14 Widget A 11 10.99 120.89 50 2024-02-15 Gadget B 8 25.50 204.00
