# ImplicitFlow-TorchRec
# 项目介绍
这个项目是一个基于隐式反馈的推荐系统，使用PyTorch实现了两个不同的模型：ImplicitFeedbackModel和AnotherImplicitFeedbackModel。这两个模型分别处理了点击历史、新闻数据和用户预测数据，并通过训练来学习用户、新闻和类别之间的嵌入关系，以预测用户对新闻的兴趣。
# 数据读取与合并
项目首先通过Pandas库读取了三个CSV文件：click_history.csv、news.csv和user_predict.csv。然后，使用merge操作将click_history和news表格合并，仅保留'user_id'、'news_id'和'category'列。随后，为合并后的数据添加了一个名为'label'的列，并设定值为1。
# 模型架构
项目定义了两个PyTorch模型：ImplicitFeedbackModel和AnotherImplicitFeedbackModel。这两个模型都包含用户、新闻和类别的嵌入层，以及全连接层。模型通过学习这些嵌入关系，从而能够预测用户是否对某个新闻感兴趣。
# 模型训练
数据被分批处理，每个批次的大小为4。在每个批次中，模型使用BCEWithLogitsLoss作为损失函数，Adam作为优化器进行训练。通过多次迭代，模型学习了用户、新闻和类别之间的复杂关系。
# 模型评估
模型在训练过程中通过AUC和准确率来评估性能。训练后，模型被保存，并在用户预测数据上进行推荐。推荐结果被与用户的实际点击历史进行比较，以评估推荐系统的效果。
# 项目文件结构
- click_history.csv: 包含用户点击历史的CSV文件。
- news.csv: 包含新闻数据的CSV文件。
- user_predict.csv: 包含用户预测数据的CSV文件。
- model_weights1.pth: 存储了ImplicitFeedbackModel模型的训练权重的文件。
- model_weights2.pth: 存储了AnotherImplicitFeedbackModel模型的训练权重的文件。
- recommendation_system.ipynb: 包含了完整的项目代码和训练推荐系统的Jupyter Notebook文件。
- README.md: 项目的说明文档。

# 项目链接
CSDN：https://blog.csdn.net/m0_46573428/article/details/136059200
# 后记
如果觉得有帮助的话，求 关注、收藏、点赞、星星 哦！
