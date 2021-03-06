# atlas-utils之根据Closed_OTU表预测功能多样性：melt

### 一、atlas-utils: melt介绍

**功能描述：**

`atlas-utils melt`  根据`Closed-OTU` 表以及对应的功能丰度矩阵,对功能空间进行预测。

**命令行接口：**

    $ atlas-utils melt
    
    Usage: atlas-utils melt [options] <feature-matrix> <otutab>
    
    Options:
      -r  round value to nearest intege;

**可选参数：**

      -r   四舍五入为整数；

### 二、使用场景实例及其用法

**使用场景经典案例：**

1. 16S 扩增子测序数据功能预测

**示例演示：**


    $ zcat ko.txt.gz | head -n 10 | cut -f 1,2,3,4,5,6,7,8,9


    #OTU_IDs        K01365  K01364  K01361  K01360  K01362  K02249  K05841  K05844
    4378163 0.0     0.0     0.0     0.0     0.0     0.0     0.0     1.0
    4411390 0.0     0.0     0.0     0.0     0.0     0.0     0.0     1.0
    3789144 0.0     0.0     0.0     0.0     0.0     0.0     0.0     0.0
    1105    0.0     0.0     0.0     0.0     0.0     0.0     0.0     0.0
    674943  0.0     0.0     0.0     0.0     2.0     0.0     0.0     0.0
    824190  0.0     0.0     0.0     0.0     2.0     0.0     0.0     0.0
    1111848 0.0     0.0     0.0     0.0     2.0     0.0     0.0     0.0
    4016971 0.0     0.0     0.0     0.0     2.0     0.0     0.0     0.0
    1111584 0.0     0.0     0.0     0.0     3.0     0.0     0.0     0.0


    $ cat otu_table.txt | head


    #OTU ID E01L    E01S    N01L    N01S    S01L    S01S
    564806  10      14      0       2       0       0
    145801  7974    429     4       265     1       233
    339087  4386    49      162     563     329     186
    370287  197     13      47      45      36      6
    4449244 10138   4       0       104     2       61
    513445  984     159     23      676     117     127
    351231  40      55      35      1029    768     2876
    191487  2979    1058    79      145     369     2178
    176034  1785    114     15      77      28      198


**示例文件：**

**运行命令：**

根据`Closed-OTU` 表以及对应的功能丰度矩阵,对功能空间进行预测


    $ atlas-utils melt ko.txt.gz otu_table.txt | head


    #sample E01L    E01S    N01L    N01S    S01L    S01S
    K01365  0       0       0       0       0       0
    K01364  0       0       0       7       0       0
    K01361  82      217     4       830     3       524
    K01360  0       0       0       0       0       0
    K01362  65070   17296   8108    28591   50635   117304
    K02249  3       6       0       0       2       3
    K05841  4       113     1       12      4       32
    K05844  2747    1335    102     558     1127    157
    K05845  6094    2956    160     2643    1928    1812



本文材料为 **BASE** (**B**iostack **A**pplied bioinformatic **SE**ies ) 课程 **Linux Command Line Tools for Life Scientists** 材料， 版权归 **上海逻捷信息科技有限公司** 所有。

Last Update: 2020-09-11 11:56 AM