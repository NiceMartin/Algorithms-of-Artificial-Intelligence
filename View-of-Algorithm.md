# Blogs

- https://createmomo.github.io/2018/01/27/Table-of-Contents/
	- crf
	- Activation 
	- Gradient Descent
	- Parameters
	- Rugularization
	- Models
	- Tips
- https://github.com/wepe/MachineLearning


- ### 判别模型和生成模型

  - Reference
    - http://www.cnblogs.com/zhangchaoyang/articles/7100083.html
    - http://www.cnblogs.com/kaituorensheng/p/3379170.html
  - 生成模型：
    - 直接求联合概率p(x,y)，得到p(x,y)后就可以去生成样本。
    - HMM、高斯混合模型GMM、LDA、PLSA、Naive Bayes都属于生成模型。
    - 当我们得到HMM模型后，就可以根据初始状态分布π、状态转移矩阵A和发射矩阵B去生成一个状态序列及相应的观察序列，即拿着生成模型可以去生成样本。
    - LDA（或PLSA）模型也一样，得到文档下的主题分布p(zk|di)及主题下的词分布p(wj|zk)后，上帝就可以去创作文章了。
  - 判别模型：
    - 直接求判别（或者是预测）函数y=(f(x)，或者另一种表达：p(y|x)。
    - 最大熵MaxEnt、人工神经网络ANN、逻辑回归LR、线性判别分析LDA、K-Means、KNN、SVM、决策树都属于判别模型。
    - 最大熵直接去求p(y|x)，它不会浪费功夫去求p(x,y)
    - 同样KNN也不关心样本是如何生成的，它只会对样本进行分类。
  - 由生成模型可以得到判别模型，因为p(y|x)=p(x,y)p(x)，但它有2个缺点：
    - 需要额外地去求p(x)。
    - 样本量不足的情况下p(x)可能求不准。此时预测p(y|x)没有判别模型准。
  - 生成模型也有它的优点：
    - 可以生成样本，反应样本本身的相似度
    - 比如LDA中得到了p(zk|di)就相当于得到了文档向量，可以去计算向量之间的相似度。
  - 当含有隐含变量时，也可以用生成模型，但不能用判别模型。比如HMM、GMM、LDA、PLSA模型都可以用EM算法求解。

- Imitation Learning

  - One Shot Imitation Learning
   	- 这篇论文提出一个比较通用的模仿学习的方法。这个方法在运行时，需要一个完成当前任务的完整演示，和当前状态。假设我要机器人搭方块，那么我给它一个完整的把方块搭好的视频演示，再告诉他当前方块都在哪里。这个模型会用CNN和RNN来处理任务的演示，这样，它就有一个压缩过的演示纲要。模型再用CNN处理当前状态，得到一个压缩过的当前状态信息。利用Attention Model来扫描演示纲要，我们就得到了“与当前状态最有关的演示的步骤”，再将这些信息全部传递给一个决策器。然后输出决策。
    - (不确定)https://github.com/tianheyu927/mil

- 概要：NIPS 2017 Deep Learning for Robotics Pieter Abbeel

  - https://zhuanlan.zhihu.com/p/32089849

- Meta Learning Shared Hierarchies

- DetNet: A Backbone network for Object Detection
  - 本文来自清华大学和 Face++，文章分析了使用 ImageNet 预训练网络调优检测器的缺陷，研究通过保持空间分辨率和扩大感受野，提出了一种新的为检测任务设计的骨干网络 DetNet。
  - 实验结果表明，基于低复杂度的 DetNet59 骨干网络，在 MSCOCO 目标检测和实例分割追踪任务上都取得当前最佳的成绩。

- 今日头条AI实验室主任李航：自然语言的现状和发展 | 北大AI公开课笔记
  - https://c.m.163.com/news/s/S1521443845851.html
  - 合理行动的智能机
  	- Turing Test
  - 人脑如何做语言理解
  	- 词汇
  	- 句法
  	- 语义
  	- 语用
  	- 有几个重要的脑区是和语言密切相关的：布洛卡区域和维尼科区
  	- 比如维尼科区负责词汇，布洛卡区负责句法
  	- 语言理解是非常复杂的，大脑一共有1011 到1015 个神经元，这样复杂的计算系统还是并行处理，我们每个人在做这样复杂的处理
  - attention
  - seq2seq
  - 对话
  	- 多人对话中也是，现在用的最多的是深度强化学习
  	- 谷歌提出的Neural Symbolic Machines模型，特点结合符号处理和神经处理，其框架也是基于分析的模型
  	- 还有华为方舟提出的类似模型（Neural Responding Machine）。
  	- 在多人中，微软提出层次化的深度强化学习Hierarchical Deep Reinforcement Learning。
  	- 对话目标可以分层，展开和复述，将有限状态机变成层次化。学习就可以用层次化甚至强化学习来做这样的东西。
        - 单轮对话
            - 分析 ： 基于分析就是分类问题
            - 检索 ： 检索当成匹配问题
            - 生成 :  生成当做是翻译问题; 这是比较新的系统，目前还不太好做。把问句转化成内部表示，然后再转化为答句
            - 云助手一般是第一种，问答系统一般是第二种，聊天机器人一般应用第三种
        - 多论对话
            - 自然语言理解
            - 自然语言生成
            - 对话管理


# Viewpoint of NLP

+ https://www.wxwenku.com/d/100329482
	- 但是由于语言本身已经是一种高层次的表达，深度学习在 NLP 中取得的成绩并不如在视觉领域那样突出。尤其是在 NLP 的底层任务中，基于深度学习的算法在正确率上的提升并没有非常巨大，但是速度却要慢许多，这对于很多对 NLP 来说堪称基础的任务来说，是不太能够被接受的，比如说分词
	- 在完形填空类型的阅读理解（cloze-style machine reading comprehension）上，基于 attention 的模型也取得了非常巨大的突破（在 SQuAD 数据集上，2016 年 8 月的 Exact Match 最好成绩只有 60%，今年 3 月已经接近 77%，半年时间提升了接近 20 个点，这是极其罕见的）
	- 深度学习的不可解释的特性和对于数据的需求，也使得它尚未在要求更高的任务上取得突破，比如对话系统（虽然对话在 2016 年随着 Echo 的成功已经被炒得火热）
	- 在大多数端到端的 NLP 应用中，在输入中包括一些语言学的特征（例如 pos tag 或 dependency tree）并不会对结果有重大影响。我们的一些粗浅的猜测，是因为目前的 NLP 做的这些特征，其实对于语义的表示都还比较差，某种程度来说所含信息还不如 word embedding 来的多
	- 关于阅读理解（Open-domain QA）
		- 幸好 Stanford 的 Chen Danqi 大神的 Reading Wikipedia to Answer Open-Domain Questions 打开了很多的方向。通过海量阅读（「machine reading at scale」），这篇文章试图回答所有在 wikipedia 上出现的 factoid 问题。其中有大量的工程细节，在此不表，仅致敬意。
- ACL 2016：基于深度学习的 NLP 看点（十大优秀论文下载）
	- 2016年NLP深度学习技术的发展趋势
		- 深度学习模型在更多NLP任务上的定制化应用。例如将过去统计机器翻译的成熟成果迁移到神经网络模型上，基于深度学习的情感分析，再例如今年NAACL 2016的最佳论文Feuding Families and Former Friends; Unsupervised Learning for Dynamic Fictional Relationships也利用神经网络模型检测小说中的人物关系。
		- 带有隐变量的神经网络模型。很多NLP任务传统主要基于HMM、CRF方法对标注标签的关联关系建模，而单纯的神经网络模型并不具备这个能力，因此一个重要热点将是在神经网络模型中引入隐变量，增强神经网络的建模能力。
		- 注意力（attention）机制的广泛应用。大量工作已经证明attention机制在文本产生中的重要性，也是继CNN->RNN->LSTM之后的新的论文增长点，相信在2016年会有大量论文提出各种带有attention的神经网络模型。
	- 如何将先验知识引入分布式表示
		- 分布式表示（distributed representation）是深度学习的重要特点；避免特征工程的端对端（End-to-End）框架则是深度学习在NLP的独特优势。然而，现实世界中我们拥有大量人工标注的语言知识库和世界知识库，如何在深度学习框架中引入这些先验知识，是未来的重要挑战性问题，也是极大拓展深度学习能力的重要途径。在这个方面，有很多颇有创见的探索工作，例如来自香港华为Noah实验室Zhengdong Lu团队的Neural Enquirer: Learning to Query Tables [1]，等等。此外，我认为基于深度学习的attention机制也是引入先验知识的重要可能手段。机器学习领域还提供了很多其他可能的手段，等待我们去探索。
	- 探索人类举一反三能力的One-Shot Learning
		- 如2015年在Science发表的轰动论文[2]所述，人类学习机制与目前深度学习的显著差异在于，深度学习利用需要借助大量训练数据才能实现其强大威力，而人类却能仅通过有限样例就能学习到新的概念和类别，这种举一反三的学习机制，是机器学习也是自然语言处理梦寐以求的能力。这需要我们特别关注认知领域的相关进展[3, 4]，机器学习领域也在热切探索one-shot learning任务。在NLP领域，如何应对新词、新短语、新知识、新用法、新类别，都将与该能力密切相关。
	- 从文本理解到文本生成的飞跃
		- 目前取得重要成果的NLP任务大多在文本理解范畴，如文本分类，情感分类，机器翻译，文档摘要，阅读理解等。这些任务大多是对已有文本的“消费”。自然语言处理的飞跃，需要实现从“消费”到“生产”的飞跃，即探索如何由智能机器自动产生新的有用文本。虽然现在有媒体宣称实现了新闻的自动生成，但从技术上并无太多高深之处，更多是给定数据后，对既有新闻模板的自动填充，无论是从可扩展性还是智能性而言，都乏善可陈。我认为，自然语言处理即将面临的一个飞跃，就是智能机器可以汇总和归纳给定数据和信息，自动产生符合相关标准的文本，例如新闻、专利、百科词条[5]、论文的自动生成，以及智能人机对话系统等等。毫无疑问，这个技术飞跃带来的应用拥有无限的想象空间。
	- 大规模知识图谱的构建与应用
		- “知识图谱”是谷歌推出的产品名，现在已经成为对大规模知识库的通用说法。如果说深度学习是机器大脑的学习机制，那么知识图谱可以看做机器大脑的知识库。知识图谱是问答系统的重要信息来源，也是阅读理解、机器翻译、文档摘要等任务进一步发展的重要支撑。目前，知识图谱从构建到应用都仍有很多问题亟待解决，例如新概念、新知识的自动学习，如何基于知识图谱实现智能推理，等等。在这方面，我一直关注知识的分布式表示学习，能够建立统一的语义表示空间，有效解决大规模知识图谱的数据稀疏问题，有望在知识获取、融合和推理方面发挥重要作用[6]。

- 一文概述2017年深度学习NLP重大进展与趋势
    		- http://www.qingpingshan.com/bc/jsp/361202.html
- 李航NSR论文：深度学习NLP的现有优势与未来挑战
	- Deep Learning for Natural Language Processing: Advantages and Challenges
- pass
	- 端到端训练与表征学习是深度学习的核心特征，这使其成为 NLP 的强大工具。但深度学习并非万能，它在对解决**多轮对话**等复杂任务异常关键的**推断和决策**上表现欠佳。此外，如何结合符号处理与神经处理、如何应对长尾现象等问题依然是深度学习 NLP 面临的挑战[1]。
	- 自然语言处理领域有很多复杂任务，这些任务可能无法仅使用深度学习来轻松完成。例如，多轮对话是一个非常复杂的过程，涉及语言理解、语言生成、对话管理、知识库访问和推断。对话管理可以正式作为序贯决策过程，其中强化学习发挥关键作用。很明显，把深度学习和强化学习结合起来可能有利于完成任务。
	- 总之，深度学习 NLP 仍然面临许多待解决的挑战。深度学习与其他技术（强化学习、推断、知识）结合起来将会进一步扩展 NLP 的边界[1]。
