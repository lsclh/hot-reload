#文件修改热重启worker

>在swoole启动处mainServerCreate
添加进程即可
该进程使用定时器自动扫描文件


###开启热重载 提高开发效率
```
$swooleServer = ServerManager::getInstance()->getSwooleServer();
$swooleServer->addProcess((new  \Lsclh\HotReload\HotReload('HotReload', ['disableInotify' => false]))->getProcess());
```