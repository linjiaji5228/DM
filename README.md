# 基于Datwhale数据挖掘第7期组队学习
## 这份数据集是金融数据（非原始数据，已经处理过了），我们要做的是预测贷款用户是否会逾期。表格中 "status" 是结果标签：0表示未逾期，1表示逾期。
## 任务一：对数据进行探索和分析。包括但不限于数据类型的分析、无关特征删除、数据类型转换、缺失值处理。
#### 在做任务一时我用了互信息法删除了一些特征总共剩余52个特征，用随机森林auc达到84.22%
## 任务二：特征工程：包括但不限于IV值和随机森林等进行特征选择。
### 1、分箱计算IV值，IV值用来衡量自变量预测能力，IV值越大，说明自变量的预测能力越强，对因变量的预测贡献越大，变量越重要。
### 2、随机森林进行特征选择，主要用到随机森林的属性feature_imoportances，能够查看各个特征对模型的重要性。
#### 计算IV值，选择介于0.02~0.5之间的IV值，筛选出36个特征，用随机森林取出前20个feature_imoportances重要的变量，最终auc达到81.07%。
## 任务三：模型构建。用逻辑回归、svm和决策树；随机森林和XGBoost进行模型构建，评分方式任意，如准确率等。（不需要考虑模型调参）
### 因样本是不平衡样本，此处主要考虑auc额值。XGBoost的auc0.8332,随机森林的auc0.8248，SVC的auc0.7641,决策树的auc0.7570,逻辑回归的auc0.6843.
