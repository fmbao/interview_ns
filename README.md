<!--
 * @Author: Baochenchen 1689940525@qq.com
 * @Date: 2022-07-09 15:11:51
 * @LastEditors: Baochenchen 1689940525@qq.com
 * @LastEditTime: 2022-07-09 15:15:14
 * @FilePath: /面经/Volumes/YAYA/Document/知乎专栏/interview_ns/README.md
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
# interview_ns
音频降噪的一些面试题，欢迎大家可以补充

【问】Rnnoise中的基音计算模块的组成以及相关特征提取的方式
【答】
https://blog.csdn.net/u011792766/article/details/119468692
有关Rnnoise的讲解： 在Rnnoise中，band struction 在其他论文中使用神经网络直接估计frequency bins需要的网络复杂度比较高。
作者为了避免这个问题，作者嘉定频谱包络足够平坦，进而可以使用比较粗糙的分辨率，此外，他没有直接计算频谱幅度，而是对理想临界带增益进行了估计
频带的划分选择和Opus codec使用的bark scale相同（实际上为了方便，文章作者直接就使用了Opus的pitch计算代码）
其中有关Opus的代码下载地址以及具体功能解释的网址是：
https://opus-codec.org
当然只要你愿意在网上搜也是可以看到很多有关Opus的文档的：
https://juejin.cn/post/6844903998831460360
还有写的非常详细的自己动手实现的版本：
https://xie.infoq.cn/article/35f73506b078f200f243d8997
【问】人耳对声音的敏感范围
【答】人耳对声音的敏感范围：1k-8kHz；人耳的能够听到的频率范围：20Hz-20kHz
【问】深度学习方案和传统音频降噪方案的差异
【答】深度学习降噪能够更好地应对非稳态噪声。
传统降噪算法主要是基于滤波理论，
深度学习降噪方案主要是基于TF域，时域降噪。
【问】GRU的权重是否共享
【答】GRU对每一帧的输入数据都是权重共享的
【问】BIGRU的具体实现
【答】具体实现在torch官网：
https://pytorch.org/docs/stable/generated/torch.nn.GRU.html?highlight=gru#torch.nn.GRU
【问】IIR FIR滤波器
【答】有关这两个滤波器的实现：
https://zhuanlan.zhihu.com/p/144662346
同时零逆战在这个博客中也讲述了比较详细的有关滤波器相关的描述;
https://www.cnblogs.com/LXP-Never/p/10886622.html

