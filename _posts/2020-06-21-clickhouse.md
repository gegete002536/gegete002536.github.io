---\ncategories: 数据库\n---\n
一、表引擎

1. tinylog
   - 不支持索引
   - 不支持并发
   - 存储在内存
   - 适用于只读不改的情形
2. memory：数据以未压缩的形式直接保存在内存中
   - 查询速度快，10G/s
   - 不支持索引
   - 没有持久化
   - 适用于测试，性能要求非常高且数据量不大（上限1亿行）的情形
3. merge：本身不存储数据，只是从其他表中进行读取
4. **Mergetree**
   - 数据按主键排序
   - 可以使用分区：只支持按日期分区
   - 多副本