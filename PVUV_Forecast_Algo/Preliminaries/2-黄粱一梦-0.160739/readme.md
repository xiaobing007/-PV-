# 第三届易观算法大赛——PV,UV流量预测 解决方案
**队伍：黄粱一梦**
**作者：神**

---

**1. 安装需要组件**

运行代码
```python
pip install -r requirements.txt
```

---

**2. 提取趋势周期方程，这里属于原创方法。**

运行代码

```python
pytohn submition_one_dream.py
```

Input: kpi_train.csv
Ouput: submission.csv


思路是把原本数据的趋势和周期性用方程提取出来。然后用来机器学习。
模型使用了lgbm，因为用了函数表示数据，所以没有像普通时序列预测那样开一个窗口。
就直接把函数的1～207的值作为特征，时序列作为目标来训练，因为有四个不同预测对象所以分别设置了参数。
另外对预测结果 pv 小于 uv 的情况作了修正，使得 pv 总能大于 uv，这一点有时意外挺有用的。
还有手动创建了一列工作日假日调休特征，也有很大用处。









