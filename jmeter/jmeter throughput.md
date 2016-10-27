
### jMeter 吞吐量(throughput)的计算方法

性能测试中，jmeter聚合报告中计算的throughput值小于压测值（使用throughput shaping timer），但是服务端实时计算的throughput值符合压测值。
原因是：计算方法不一样，一个是平均值，一个是实时值。


用语详细说明及公式详见官方地址： 
http://jmeter.apache.org/usermanual/glossary.html#Throughput 

Throughput = (number of requests) / (total time) 
total time = 测试结束时间 - 测试开始时间 
测试结束时间 = MAX(请求开始时间 + Elapsed Time) 
测试开始时间 = MIN(请求开始时间) 

若没有选中 "Successes" 时，其 Throughput 是包含出错的请求的 Throughput。 
若选中 "Successes" 时，Throughput 仅是所有正确的请求的 Throughput。 

PS: 
设置 Thread Group->Add->Listener->Simple Data Writer 就可以生成报告文件，默认情况下就包括“请求开始时间”和“Elapsed Time ”信息



http://yhz61010.iteye.com/blog/1735874