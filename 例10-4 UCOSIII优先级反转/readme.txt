例10-4 UCOSIII优先级反转

实验内容：
   创建4个任务，任务start_task用于创建另外三个任务和一个初始值为1的信号量TEST_SEM。high_task和low_task都会请求信号量TEST_SEM，但是low_task任务需要很久才会释放信号量TEST_SEM，
这样high_task任务就需要等很久，直到low_task释放掉信号量TEST_SEM才能再次请求到信号量TEST_SEM。在high_task等待TEST_SEM的这段时间里，任务middle_task会一直运行，给人的感觉就是
middle_task的优先级高于high_task任务了，但是事实上high_task任务的优先级是高于middle_task的，这个就是优先级反转。

注意：
1、 UCOSIII中以下优先级用户程序不能使用，ALIENTEK将这些优先级分配给了UCOSIII的5个系统内部任务。
    优先级0：中断服务服务管理任务 OS_IntQTask()
    优先级1：时钟节拍任务 OS_TickTask()
    优先级2：定时任务 OS_TmrTask()
    优先级OS_CFG_PRIO_MAX-2：统计任务 OS_StatTask()
    优先级OS_CFG_PRIO_MAX-1：空闲任务 OS_IdleTask()

               	正点原子@ALIENTEK
               	2015-5-20
		广州市星翼电子科技有限公司
                联系电话（传真）：020-38271790
	       	购买：http://shop62103354.taobao.com 
                      http://shop62057469.taobao.com
               	技术支持论坛：www.openedv.com