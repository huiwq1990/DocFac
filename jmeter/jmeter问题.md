
### Throughput Shaping Time - No free threads left in worker pool

当使用 Throughput Shaping Time 的时候，线程已经足够多，但是并发量不仅上不去，而且还报线程不够。
说明，现在jmeter的线程都在使用，没法达到预期的吞吐量。
原因：很有可能是服务器的处理能力问题，例如tomcat设置的连接线程数限制。