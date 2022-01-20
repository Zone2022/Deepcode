# KNN算法

> 基于癌症检测项目对于KNN算法的理解


```Python
import csv
//读取csv文件中的数据

with open('Prostate_Cancer.csv','r')as file:
    reader=csv.DictReader(file)

   datas=[row for row in reader]

/*分组*/
 n=len(datas)//3

 test_set=datas[0:n]
 train_set=datas[n:]

 print(test_set)

#KNN
#距离
def distance(d1,d2):
    res=0

    for key in ("radius","texture","perimeter","area","smoothness","compactness","symmetry","fractal_dimension"):
        res+=(float(d1[key])-float(d2[key]))**2

        return res**0.5

        K=5
//关于K值的选取：从选取一个较小的K值开始，不断增加K的值，
然后计算验证集合的方差，最终找到一个比较合适的K值。
        def knn(data):
        res={
            {"result":train['diasgnosis_result'],"distance":distance(data,train)}
            for train in train_set
        }    
//通过调用函数计算预测点与所有点距离（欧氏距离）

        sorted(res,key=lambda item:item['distance'])
//按欧氏距离排序，并返回升序排列的索引

        res2=res[0:K]
//选取距离最小的K个样本

        result={'B':0,'M':0}
//计算类别标签平均出现次数

        #总距离
        sum=0
        for r in res2:
            sum+=r['distance']

            for r in res2:
                result[r['result']]+=1-r['distance']/sum

        if result['B']>result:['M']
         return'B'
        else:
            return 'M'
//返回结果

#测试阶段
correct=0
for test in test_set:
    result=test['diagnosis_result']
    result2=knn(test)

    if result==result2:
        correct+=1

    print(“准确率：{：.2f}%”.format(100*correct/len(test_set)))

```
