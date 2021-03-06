#局部性原理--各类优化的基石

    所以什么是局部性？这是一个常用的计算机术语，是指处理器在访问某些数据时短时间内存在重复访问，
    某些数据或者位置访问的概率极大，大多数时间只访问_局部_的数据。
    基于局部性原理，计算机处理器在设计时做了各种优化，比如现代CPU的多级Cache、分支预测…… 
    有良好局部性的程序比局部性差的程序运行得更快。
    虽然局部性一词源于计算机设计，但在当今分布式系统、互联网技术里也不乏局部性，
    比如像用redis这种memcache来减轻后端的压力，CDN做素材分发减少带宽占用率……
    局部性的本质是什么？其实就是概率的不均等。
 
##局部性的分类

    局部性有两种基本的分类， 时间局部性 和 空间局部性 ，按Wikipedia的资料，可以分为以下五类，
    
  ### 时间局部性(Temporal locality):
  
    如果某个信息这次被访问，那它有可能在不久的未来被多次访问。
    时间局部性是空间局部性访问地址一样时的一种特殊情况。
    这种情况下，可以把常用的数据加cache来优化访存。
  ### 空间局部性(Spatial locality):
  
    如果某个位置的信息被访问，那和它相邻的信息也很有可能被访问到。 
    这个也很好理解，我们大部分情况下代码都是顺序执行，数据也是顺序访问的。
    
  ### 内存局部性(Memory locality):
  
    访问内存时，大概率会访问连续的块，而不是单一的内存地址，其实就是空间局部性在内存上的体现。
    目前计算机设计中，都是以块/页为单位管理调度存储，其实就是在利用空间局部性来优化性能。
  
  ### 分支局部性(Branch locality)
  
    这个又被称为顺序局部性，计算机中大部分指令是顺序执行，顺序执行和非顺序执行的比例大致是5:1，
    即便有if这种选择分支，其实大多数情况下某个分支都是被大概率选中的，于是就有了CPU的分支预测优化。
    
  ### 等距局部性(Equidistant locality)
    等距局部性是指如果某个位置被访问，那和它相邻等距离的连续地址极有可能会被访问到，
    它位于空间局部性和分支局部性之间。举个例子，比如多个相同格式的数据数组，
    你只取其中每个数据的一部分字段，那么他们可能在内存中地址距离是等距的，
    这个可以通过简单的线性预测就预测是未来访问的位置。