# performace_monitor
Continuously monitor the value of CPU, memory, IO of the specified port or PID or system in the Linux system.
Monitor can be started or stopped at any time. And plotting them.<br>

It can monitor linux system's free memory, when free memory is too low, it can clear cache or email to you.<br>
It can monitor gc for java's applications, when the frequency of full gc, it can email to you.<br>

## Usage
1. Clone performance_monitor repository
   ```shell
   git clone https://github.com/leeyoshinari/performance_monitor.git
   cd performance_monitor
   ```

2. Modify `config.py`.
   
3. Ensure which disk your application runs, or which disk your application reads and writes. And then, set the name of disk into `config.py`.

4. If you want to email to you when memory and gc's frequency wrong, please set `PASSWORD` in `config.py`, the password is generated by `GenerateKey.py`. Meanwhile, you must modify `GenerateKey.py` and `PwdEncrypt.py` to protect your password.<br>

5. Run
   ```shell
   python3 server.py
   ```
   or
   ```shell
   nohup python3 server.py &
   ```

6. using<br>
   Enter `http://ip:port` in browser<br>
   (1) `http://ip:port/startMonitor`<br>
   ![startMonitor](https://github.com/leeyoshinari/performance_monitor/blob/master/templates/startMonitor.jpg)
   
   (2) `http://ip:port/Visualize`<br>
   ![Visualize](https://github.com/leeyoshinari/performance_monitor/blob/master/templates/Visualize.jpg)
   
## Note
1. Your Linux must support the `jstat`, `top`, `iostat` and `netstat` commands, if not, please install them.

2. For more information, please [read me](https://blog.csdn.net/leeyoshinari/article/details/98248304).

3. If you don't know how to install Python 3.7+ in Linux, please [read me](https://blog.csdn.net/leeyoshinari/article/details/95805478)

## Requirements
1. flask
2. flask_bootstrap
3. matplotlib
4. Python 3.7+
