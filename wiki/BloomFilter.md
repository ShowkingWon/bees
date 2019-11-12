# Bloom Filter
    probabilistic data structure。
    By definition, Bloom filter can check for if a value is ‘possibly in the set’ or ‘definitely not in the set’. 
    The subtle difference between ‘possibly’ and ‘definitely not’ — is very crucial here. 
    可能在集合中
    肯定不在集合中
    
    The bloom filter essentially consists of a bit-vector or bit-list(a list containing only either 0 or 1-bit value) of length m, initially all values set to 0, as shown below.
    长度为m的位向量或者位列表。 （仅包含0 1值）
    
    我们可以根据过滤器的大小，m，哈希函数的个数，k，插入元素的个数，n来计算误报错误率p，公式为:
    
    
    需要用快哈希函数
    因为使用bloom filter的唯一目的是为了更快地搜索，所以我们不能使用慢速哈希函数。
    像Sha-1、MD5这样的加密哈希函数对于bloom过滤器来说不是一个好的选择，因为它们的速度有点慢。
    因此，对于速度更快的散列函数实现，更好的选择是whisper、fnv系列散列、Jenkins散列和HashMix。