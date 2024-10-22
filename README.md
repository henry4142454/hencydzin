import pandas as pd  
  
# 定义常量  
CSV_FILE_PATH = r'C:\Users\ma177\Desktop\Sales_7847a20feb3241b648d7e38772c91934.csv'  
PRODUCT_COLUMN = 'Product'  
TOTAL_SALES_COLUMN = 'Total Sales'  
DATE_COLUMN = 'Date'  
  
try:  
    # 读取销售数据 CSV 文件  
    sales_data = pd.read_csv(CSV_FILE_PATH)  
      
    # 计算每种产品的总销售额  
    product_sales = sales_data.groupby(PRODUCT_COLUMN)[TOTAL_SALES_COLUMN].sum()  
      
    # 找到最畅销的产品和销售额  
    best_selling_product = product_sales.idxmax()  
    best_selling_amount = product_sales.max()  
      
    # 找到销售额最高的日期和销售额  
    max_sales_row = sales_data.loc[sales_data[TOTAL_SALES_COLUMN].idxmax()]  
    max_sales_date = max_sales_row[DATE_COLUMN]  
    max_sales_amount = max_sales_row[TOTAL_SALES_COLUMN]  
      
    # 输出分析结果  
    print(f'每种产品的总销售额:\n{product_sales}')  
    print(f'\n最畅销的产品是 {best_selling_product}，销售额为 ${best_selling_amount:.2f}')  
    print(f'销售额最高的日期是 {max_sales_date}，销售额为 ${max_sales_amount:.2f}')  
      
except FileNotFoundError:  
    print(f"文件未找到：{CSV_FILE_PATH}")  
except pd.errors.EmptyDataError:  
    print("文件为空或格式不正确")  
except pd.errors.ParserError:  
    print("文件解析错误，请检查CSV格式")  
except Exception as e:  
    print(f"发生了一个错误：{e}")
