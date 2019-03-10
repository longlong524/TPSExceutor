# TPSExceutor
One threadpool implements executor that adjust thread num based TPS

# how to use
private Executor EXE=MyExecutor.getSingle(64,218,300000,30000,1.01,4,System.currentTimeMillis()-120000);

# params
	 * @param LowThreadNum the min num
	 * @param highThreadNum the max num
	 * @param timeInterval check time interval,milliseconds.
	 * @param taskTPSInterval TPS time interval,like 20 secs
	 * @param changeRate the change rate we think TPS improvment
	 * @param threadStep how many thread num we ajust
	 * @param startTime when to start.
# 场景
用于任何任务TPS会根据环境和配置不断变化的场景。

#  优势
提高CPU利用率
提高总TPS
# 设计某些关键点
## 任务终止不再向任务发送interruppt，会等待任务执行完成。
## 长时间助停任务不要使用
