# Ch02 - k-近邻(KNN)

##### K-近邻算法：
##### 优点：精度高，对异常值不敏感，无数据输入假定。
##### 缺点：计算复杂度高，空间复杂度高。
##### 适合数据范围：数值型和标称型。

##### 通常k是不大于20的整数，最后，选择k个最相似数据中出现次数最多的分类，作为新数据的分类。

##### 训练算法不适用于K-近邻算法。

##### KNN是通过测量不同特征值之间的距离进行分类。
##### 它的的思路是：如果一个样本在特征空间中的k个最相似(即特征空间中最邻近)的样本中的大多数属于某一个类别，则该样本也属于这个类别。

##### KNN算法的思想总结一下：
##### 就是在训练集中数据和标签已知的情况下，输入测试数据，将测试数据的特征与训练集中对应的特征进行相互比较，找到训练集中与之最为相似的前K个数据，则该测试数据对应的类别就是K个数据中出现次数最多的那个分类，其算法的描述为：
##### [1] 计算测试数据与各个训练数据之间的距离；
##### [2] 按照距离的递增关系进行排序；
##### [3] 选取距离最小的K个点；(k<=20)
##### [4] 确定前K个点所在类别的出现频率；
##### [5] 返回前K个点中出现频率最高的类别作为测试数据的预测分类。

##### k-近邻算法优缺点
##### 优点:
##### [1] 在数据量不是很大时，是作为最简单最有效的算法。

##### [2] k-近邻算法是基于实例的学习，使用算法必须有接近实际数据的训练样本数。

##### 缺点：
##### [1] k-近邻算法对每个测试集样本都使用了一次全部的训练集，第一若是训练集大，需要较大的存储空间，这一点倒不是什么问题，现在处理的数据基本上上G，主要是第二点，因为对每个测试集样本都需要使用一次全部的训练集得到最短的k个距离值，那么计算必然非常耗时。
##### [2] k-近邻算法无法给出任何数据的基础结构信息。无法知晓平均实例样本和典型实例样本具有怎样的特征。

##### KNN 与 SVM 的区别是什么？
##### 一般分类任务主要有两个步骤：
##### 1.训练；
##### 2.测试。

##### 对于SVM，是先在训练集上训练一个模型，然后用这个模型直接对测试集进行分类。这两个步骤是独立的。
##### KNN是一种基于实例的学习算法，它不同于贝叶斯、决策树等算法，KNN不需要训练，当有新的实例出现时，直接在训练数据集中找k个最近的实例，把这个新的实例分配给这k个训练实例中实例数最多类。KNN也成为懒惰学习，它不需要训练过程，在类标边界比较整齐的情况下分类的准确率很高。KNN算法需要人为决定K的取值，即找几个最近的实例，k值不同，分类结果的结果也会不同。对于KNN，没有训练过程。只是将训练数据与训练数据进行距离度量来实现分类。

##### KNN：原理比较简单，可以需要很少量的样本数据，但一定要足够典型；高纬度情况下会疯掉。

##### SVM：适合处理高纬度情况。

##### K 值的选取没有一个绝对的标准，但可以想象，K 取太大并不能提高正确率，而且求 K 个最近的邻居是一个O(K*N)复杂度的算法，k 太大，算法效率会更低。

##### 虽然说 K 值的选取，会影响结果，有人会认为这个算法不稳定，其实不然，这种影响并不是很大，因为只有这种影响只是在类别边界上产生影响，而在类中心附近的实例影响很小。
