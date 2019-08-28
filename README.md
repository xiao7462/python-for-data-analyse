# python 学习过程中的一些问题记录
目录    
-[环境搭建](#环境搭建)      
-[python_learning_note](#python_learning_note)        
-[numpy](#numpy)  
-[pandas](#pandas)  
-[matplotlib-seaborn](#matplotlib-seaborn)  
-[爬虫](#爬虫)  



# 环境搭建
 * [windows搭建jupyter-notebook](https://github.com/xiao7462/python-for-data-analyse/blob/master/anaconda.md)
 * [服务器搭建jupyter-notebook 并远程链接](https://github.com/xiao7462/python-for-data-analyse/blob/master/linux_anaconda.md)



<br>
<br>
<br>

# python_learning_note

## <a name="1">字符串</a>
 1. 字符串格式化


## 字符串正则化

## 函数
 1. [ 调用函数时加与不加括号的区别](https://github.com/xiao7462/python_learning_note/blob/master/function/self.ipynb)
 2. [函数的默认参数]()
 3. enumberate() -- 作用于一个可遍历的对象，同时返回key 和values
  ```
  >>> list(enumerate(seasons, start=1))       # 下标从 1 开始
[(1, 'Spring'), (2, 'Summer'), (3, 'Fall'), (4, 'Winter')]
  
  >>>seq = ['one', 'two', 'three']
>>> for i, element in enumerate(seq):
...     print i, element
... 
0 one
1 two
2 three
  
  ```
  

## 面向对象
 1. [面向对象简介](https://github.com/xiao7462/python_learning_note/blob/master/OOP/OOP.ipynb)
 2. [python中的下划线和双下划线](https://segmentfault.com/a/1190000002611411)
 3. [self](https://github.com/xiao7462/python_learning_note/blob/master/OOP/self.ipynb)
 4. [\__init\__ ](https://github.com/xiao7462/python_learning_note/blob/master/OOP/__init__.ipynb)
 5. [public and private](https://github.com/xiao7462/python_learning_note/blob/master/OOP/public%20and%20private.ipynb)
 

<br>
<br>
<br>


# numpy
* 显示全部array   输入`np.set_printoptions(threshold=np.inf)`

* 数据加载
 1. npz file 加载 `data = np.load(file.npz)`     # 有时直接的load 网页数据无法下载，可以通过其他方式下载到本地再加载
   > 这是data是有一个npz class ,不能直接的去看里面的内容
   ```
   # 查看data里面的数据
   >>> npx.files
   >>> ['y','x']
   >>> npz.f.x   or npz['x']
   >>> array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])  #得到里面的array
   ```

* 矩阵索引，切片




* random模块
 1. permutation
 2. seed
 3. uniform 
 4. [randint](https://github.com/xiao7462/python-for-data-analyse/blob/master/numpy-pandas/np.random.randint.ipynb)
    基本用法 ： 
    ```
    np.random.randint(1,5,(3,3))   (最低值，最高值，元组（output shape））
    array([[6, 1, 6],
       [4, 5, 7],
       [4, 4, 7]])
    ```
* linalg模块
 1. norm


       
       
       


<br>
<br>
<br>

# pandas

* dataframe获取列名 
 1. df.columns.values
 2. list(df)
 

* df.values 返回df的值， np.arrays


* [pd.cut & pd.quct](https://stackoverflow.com/questions/30211923/what-is-the-difference-between-pandas-qcut-and-pandas-cut) cut是根据values来平均划分，而qcut是根据分位数来划分，4分位数，中位数等


* [查看null值](https://github.com/xiao7462/python-for-data-analyse/blob/master/numpy-pandas/ob_null.ipynb)

* pd.groupby
 1. [示例](https://github.com/xiao7462/python-for-data-analyse/blob/master/numpy-pandas/groupby.ipynb)
  参数as_index作用
  [What is as_index in groupby in pandas?](https://stackoverflow.com/questions/41236370/what-is-as-index-in-groupby-in-pandas)            
    > 当as_index = True时  ， df.loc[] 只能用label来  比如'bk1'.      

    > 当as_index = False时 ，df.loc[] 只能用索引  0,1,2，      

    但是都能用 df.iloc[1], 结果一致
 2.  [agg vs filter vs transform](https://github.com/xiao7462/python-for-data-analyse/blob/master/numpy-pandas/agg-filter-transform.ipynb) [链接](https://pythonforbiologists.com/when-to-use-aggregatefiltertransform-in-pandas/)     

   ```
   df.groupby('day')['total_bill'].mean()
df.groupby('day').filter(lambda x : x['total_bill'].mean() > 20)
df.groupby('day')['total_bill'].transform(lambda x : x/x.mean())
   ```          
  >    if we want to get a single value for each group -> use aggregate()    
      if we want to get a subset of the input rows -> use filter()    
      if we want to get a new value for each input row -> use transform()    




* pd.drop 丢掉行或者列 
   1. 丢掉列      `df.drop(['lable']，axis = 1,inpalce = True)` axis丢掉列，inplace 是否返回改变df
   2. 丢掉行 [why can't pd.drop() by index number row](https://stackoverflow.com/questions/53297189/why-cant-pd-drop-by-index-number-row)      
      `df.drop(df.index[[0, 2]])` or `df.drop(df.index[[np.arange(0,2)]])`
   
 [why sort_values() is diifferent form sort_values().values](https://stackoverflow.com/questions/53292709/why-sort-values-is-diifferent-form-sort-values-values)      
    1.df = df.apply( lambda x: x.sort_values())   会考虑到索引再合并
    2.df.apply(lambda x: x.sort_values().values) 先返回numpy的arrays，再将arrays合并为dataframe
    
 [find maximum value in col C in pandas dataframe while group by both col A and B](https://stackoverflow.com/questions/53385348/find-maximum-value-in-col-c-in-pandas-dataframe-while-group-by-both-col-a-and-b) 
   1. `df.groupby(['RT','Similarity','Name'],as_index=False)['Quality'].sum()` 
 [How to replace one col values with another col values in conditions [duplicate]](https://stackoverflow.com/questions/53352585/how-to-replace-one-col-values-with-another-col-values-in-conditions)
   2. 通过mask来删选条件  , mask会返回False的object`df['RT'] = df['RT'].mask(df['similarity'] > 0.99, df['patch'])`
   [Pandas mask / where methods versus NumPy np.where](https://stackoverflow.com/questions/51982417/pandas-mask-where-methods-versus-numpy-np-where)

[链接](https://pythonforbiologists.com/when-to-use-aggregatefiltertransform-in-pandas/)    
      if we want to get a single value for each group -> use aggregate()    
      if we want to get a subset of the input rows -> use filter()    
      if we want to get a new value for each input row -> use transform()    




* np.c_ : 将array转换为列向量， 并将所有的列向量合并
```
Examples
--------
>>> np.c_[np.array([1,2,3]), np.array([4,5,6])]
array([[1, 4],
       [2, 5],
       [3, 6]])
>>> np.c_[np.array([[1,2,3]]), 0, 0, np.array([[4,5,6]])]
array([[1, 2, 3, 0, 0, 4, 5, 6]])
```








<br>
<br>
<br>

# matplotlib-seaborn

 
* [subplot & subplots](https://stackoverflow.com/questions/52214776/python-matplotlib-differences-between-subplot-and-subplots) subplot返回axis ,而subplots返回fig,axis. subplots更加方便
  [Why do many examples use “fig, ax = plt.subplots()” in Matplotlib/pyplot/python](https://stackoverflow.com/questions/34162443/why-do-many-examples-use-fig-ax-plt-subplots-in-matplotlib-pyplot-python)
  [differences between subplot() and subplots()](https://stackoverflow.com/questions/52214776/python-matplotlib-differences-between-subplot-and-subplots)


* matplotlib颜色 [转载](https://www.cnblogs.com/darkknightzh/p/6117528.html)

* [axes.legend](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.legend.html?highlight=legend#matplotlib.axes.Axes.legend)
  1. ax.legend(loc = 1)  改变legend位置 ，常用的loc = {'best'：	0}， {'upper right'：	1}， {'upper left'：	2} 
* sns.countplot
 1. [多组feature同时显示countplot](https://github.com/xiao7462/python-for-data-analyse/blob/master/matplotlib-seaborn/countplot_sample.ipynb) 
* scatter
* bar
 1. barplot官方[example](https://github.com/xiao7462/python-for-data-analyse/blob/master/matplotlib-seaborn/System%20Monotor.ipynb)
* sns.FacetGrid

* [sns.distplot  ](https://seaborn.pydata.org/generated/seaborn.distplot.html?highlight=dist#seaborn.distplot)
 1. 参数bins 代表用多少个长方形 ，bins= False表示直接用kernel 分布曲线



<br>
<br>
<br>

# 爬虫

