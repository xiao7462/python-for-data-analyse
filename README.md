# python_learning_note

# 字符串
 * 字符串格式化

# 列表

# 元组

# 字典

# 字符串正则化

# 函数
 * [ 调用函数时加与不加括号的区别](https://github.com/xiao7462/python_learning_note/blob/master/function/self.ipynb)
 * [函数的默认参数]()
# 面向对象
 * [面向对象简介](https://github.com/xiao7462/python_learning_note/blob/master/OOP/OOP.ipynb)
 * [python中的下划线和双下划线](https://segmentfault.com/a/1190000002611411)
 * [self](https://github.com/xiao7462/python_learning_note/blob/master/OOP/self.ipynb)
 * [\__init\__ ](https://github.com/xiao7462/python_learning_note/blob/master/OOP/__init__.ipynb)
 * [public and private](https://github.com/xiao7462/python_learning_note/blob/master/OOP/public%20and%20private.ipynb)
 
# numpy
## 矩阵索引，切片
## random模块
 * permutation
 * seed
 * uniform 
 * [randint](https://github.com/xiao7462/python-for-data-analyse/blob/master/numpy-pandas/np.random.randint.ipynb)
    基本用法 ： 
    ```
    np.random.randint(1,5,(3,3))   (最低值，最高值，元组（output shape））
    array([[6, 1, 6],
       [4, 5, 7],
       [4, 4, 7]])
    ```
## linalg模块
 * norm


# pandas
### [pd.cut & pd.quct](https://stackoverflow.com/questions/30211923/what-is-the-difference-between-pandas-qcut-and-pandas-cut) cut是根据values来平均划分，而qcut是根据分位数来划分，4分位数，中位数等

### [查看null值](https://github.com/xiao7462/python-for-data-analyse/blob/master/numpy-pandas/ob_null.ipynb)

### pd.groupby
 * [示例](https://github.com/xiao7462/python-for-data-analyse/blob/master/numpy-pandas/groupby.ipynb)
 * 参数as_index作用
  [What is as_index in groupby in pandas?](https://stackoverflow.com/questions/41236370/what-is-as-index-in-groupby-in-pandas)      
  1.当as_index = True时  ， df.loc[] 只能用label来  比如‘bk1'.     

    当as_index = False时 ，df.loc[] 只能用索引  0,1,2，      

    但是都能用 df.iloc[1], 结果一致
### pd.drop 丢掉行或者列 
   * 丢掉列      `df.drop(['lable']，axis = 1,inpalce = True)` axis丢掉列，inplace 是否返回改变df
   * 丢掉行 [why can't pd.drop() by index number row](https://stackoverflow.com/questions/53297189/why-cant-pd-drop-by-index-number-row)
   
### [why sort_values() is diifferent form sort_values().values](https://stackoverflow.com/questions/53292709/why-sort-values-is-diifferent-form-sort-values-values)      
    1.df = df.apply( lambda x: x.sort_values())   会考虑到索引再合并
    2.df.apply(lambda x: x.sort_values().values) 先返回numpy的arrays，再将arrays合并为dataframe
    
### [find maximum value in col C in pandas dataframe while group by both col A and B](https://stackoverflow.com/questions/53385348/find-maximum-value-in-col-c-in-pandas-dataframe-while-group-by-both-col-a-and-b) 
   * `df.groupby(['RT','Similarity','Name'],as_index=False)['Quality'].sum()` 
### [How to replace one col values with another col values in conditions [duplicate]](https://stackoverflow.com/questions/53352585/how-to-replace-one-col-values-with-another-col-values-in-conditions)
   * 通过mask来删选条件  , mask会返回False的object`df['RT'] = df['RT'].mask(df['similarity'] > 0.99, df['patch'])`
   [Pandas mask / where methods versus NumPy np.where](https://stackoverflow.com/questions/51982417/pandas-mask-where-methods-versus-numpy-np-where)









# matplotlib & seaborn
## 基础 
### [subplot & subplots](https://stackoverflow.com/questions/52214776/python-matplotlib-differences-between-subplot-and-subplots) subplot返回axis ,而subplots返回fig,axis. subplots更加方便
 * [Why do many examples use “fig, ax = plt.subplots()” in Matplotlib/pyplot/python](https://stackoverflow.com/questions/34162443/why-do-many-examples-use-fig-ax-plt-subplots-in-matplotlib-pyplot-python)
 * [differences between subplot() and subplots()](https://stackoverflow.com/questions/52214776/python-matplotlib-differences-between-subplot-and-subplots)


## matplotlib颜色 [转载](https://www.cnblogs.com/darkknightzh/p/6117528.html)

## [axes.legend](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.legend.html?highlight=legend#matplotlib.axes.Axes.legend)
  * ax.legend(loc = 1)  改变legend位置 ，常用的loc = {'best'：	0}， {'upper right'：	1}， {'upper left'：	2} 
## sns.countplot
 * [多组feature同时显示countplot](https://github.com/xiao7462/python-for-data-analyse/blob/master/matplotlib-seaborn/countplot_sample.ipynb) 
## scatter
## bar
 * barplot官方[example](https://github.com/xiao7462/python-for-data-analyse/blob/master/matplotlib-seaborn/System%20Monotor.ipynb)
## sns.FacetGrid



# 爬虫

