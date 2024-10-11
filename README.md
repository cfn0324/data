# 人工智能分类数据
运行以下代码来获取数据
```py
import pandas as pd
import requests
from io import BytesIO

url = "https://github.com/cfn0324/data/raw/refs/heads/main/data.xls"
response = requests.get(url)
response.raise_for_status()
data = pd.read_excel(BytesIO(response.content),sheet_name=None,header=None)
train = data["train"]
test = data["test"]

print(train)
print(test)
```