#Dionaea
###web_dionaea

> web_dionaea为企业内部web类蜜罐，用来捕捉APT，内鬼及被内鬼等入侵行为。项目使用Django编写，使用Docker运行方便部署。


注：项目前端部分由ID:chanyipiaomiao帮忙完成,github地址：https://github.com/chanyipiaomiao


####部署方式
1. 自定义蜜罐名称；修改/web_dionaea/templates/index.html中的对应title。
2. 制作蜜罐镜像；#docker build -t "web_dionaea" .
3. 创建蜜罐容器；#docker run -d -p 80:80 -v /opt:/tmp --restart=always web_dionaea
4. 添加计划任务；*/5 * * * * /bin/bash /opt/Check.sh 


####登录界面
![](pic/web_dionaea_01.png)

####日志截图
![](pic/web_dionaea_02.png)

####分析脚本执行结果
![](pic/web_dionaea_03.png)

####注意事项
这个dockerfile我没有直接构建push到dockerhub,可以任意修改成自己想要的样子，Check.sh脚本默认是在centos7环境下执行，修改Dionaea_HostIP值可直接兼容其他环境。有问题与我联系:d2VjaGF0OmF0aWdlcjc3
