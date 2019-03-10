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
# Useage
 Situation which TPS will vary according to the environment and configuration scenarios.
#  Advantages
Improving the utilization of CPU
TPS improvment

# Design
## Task termination no longer sends interruppt to the task and waits for the task to complete.
## Do not use with long-time stop-aid tasks

