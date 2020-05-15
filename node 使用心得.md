pm2

pm2 logs //显示所有日志
pm2 logs 0 //显示执行编号为0的日志
pm2 logs server.js //显示名称为server.js的进程
pm2 flush  //清洗所有的数据[注：我没有试出来效果]

pm2 monit //监控当前所有的进程
pm2 monit 0 //监控批评行编号为0的进程
pm2 monit server.js //监控名称为server.js的进程

pm2 list //查看当前正在运行的进程
pm2 show 0 //查看执行编号为0的进程

pm2 start server.js //启动server.js进程
pm2 start server.js -i 4 //启动4个server.js进程
pm2 restart server.js //重启server.js进程
pm2 stop all // 停止所有进程
pm2 stop server.js //停止server.js进程
pm2 stop 0 //停止编号为0的进程
