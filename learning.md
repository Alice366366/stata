# learning
## 1.如何将数据导入excel
  import excel "D:\download\STATA\data\multiple time data-1220",  firstrow
### 将工作路径下的excle文档导入stata，且第一行为变量名称
  destring no third_employment_ratio ,replace
### 将字符型数据数值化，便于后续处理
### 但是出现报错contains nonnumeric characters; no replace
  tab third_employment_ratio if regexm(third_employment_ratio,"[^0-9.]")
### 对数据进行检查，应该是excel存储时候出了问题，思考如何解决
