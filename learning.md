# learning
## 1.如何将数据导入excel 

  cd "D:\download\STATA\working path"
### 首先更改默认工作路径，要不输出的材料找不到 
  
  import excel "D:\download\STATA\data\multiple time data-1220",  firstrow
### 将工作路径下的excle文档导入stata，且第一行为变量名称

  destring first_ratio second_ratio investment post telecommunication ///
first_employment second_employment third_employment, replace
### 将字符型数据数值化，便于后续处理

### 但是出现报错contains nonnumeric characters; no replace

  tab third_employment_ratio if regexm(third_employment_ratio,"[^0-9.]")
### 对数据进行检查，应该是excel存储时候出了问题，进行修正

  export excel "organized data",firstrow(variables) replace
### 将处理好的数据输出成新的Excel保存在修改后的工作路径下

tabstat xxxxxxxxxx, s(N mean sd min max) f(%12.3f) c(s)
logout, save(描述性统计) word replace:	///
tabstat xxxxxxxxxx, s(N mean sd min max) f(%12.3f) c(s)
### 将描述性统计存为word形式
