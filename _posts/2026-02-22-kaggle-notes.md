---
date: 2026-02-22 21:58 +0800
title: kaggle learing notes
categories: ["learning-notes"]
---
* Kaggle learning
```python
import pandas as pd
from sklearn.ensemble import RandomForestClassifier
data_path= "train.csv"
train_data = pd.read_csv(data_path)
test_data = pd.read_csv("test.csv")
y = train_data["Survived"]
features = ["Pclass", "Sex", "SibSp", "Parch"]
X = pd.get_dummies(train_data[features])
X_test = pd.get_dummies(test_data[features])
model = RandomForestClassifier(
    n_estimators=100,        # 采用100棵决策树
    max_depth=10,            # 树的深度为10，太高容易过拟合
    random_state=2,
    n_jobs=-1,               # 使用所有CPU核心并行
    verbose=1                # 显示训练进度
)
model.fit(X, y)
predictions = model.predict(X_test)
output = pd.DataFrame({'PassengerId': test_data.PassengerId, 'Survived': predictions})
output.to_csv('submission.csv', index=False)
print("Your submission was successfully saved")
```

* 以上代码为kaggle入门练习：预测Titanic号上的乘客幸存数量，
* 采用random forest模型，是一个machine learning的学习案例
* 学习网站：<a href="https://www.kaggle.com/code/alexisbcook/titanic-tutorial" target="_blank">Titanic Tutorial</a>