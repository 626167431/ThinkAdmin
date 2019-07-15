[![Latest Stable Version](https://poser.pugx.org/zoujingli/thinkadmin/v/stable)](https://packagist.org/packages/zoujingli/thinkadmin) [![Total Downloads](https://poser.pugx.org/zoujingli/thinkadmin/downloads)](https://packagist.org/packages/zoujingli/thinkadmin) [![Latest Unstable Version](https://poser.pugx.org/zoujingli/thinkadmin/v/unstable)](https://packagist.org/packages/zoujingli/thinkadmin) [![License](https://poser.pugx.org/zoujingli/thinkadmin/license)](https://packagist.org/packages/zoujingli/thinkadmin)


大道至简 · 原生框架
--
ThinkAdmin V4.1 是一个基于 ThinkPHP5.1 开发的后台管理系统。

我们致力于二次开发底层框架，提供完整的组件及API，基于此框架可以快速开发应用。

另外项目安装及二次开发可以参考 ThinkPHP 官方文档，数据库文件摆放在项目根目录下。

#### 注意事项 
* 项目测试需要自行搭建环境导入数据库( admin_v4.sql )并修改配置( config/database.php )；
* 若操作提示“测试系统禁止操作”等字样，需要删除演示路由配置( route/demo.php )或清空路由文件；
* 当前版本使用 ThinkPHP5.1.x，对 PHP 版本标注不低于 PHP5.6，具体请阅读 ThinkPHP 官方文档；
* 环境需开启 PATHINFO，不再支持 ThinkPHP 的 URL 兼容模式运行（源于如何优雅的展示）；

技术支持
--
开发前请认真阅读 ThinkPHP 官方文档会对您有帮助哦！

本地开发命令`php think run`，使用`http://127.0.0.1:8000`访问项目。


权限管理
--
* 此版本的权限使用注解实现管理
* 注释必需使用标准的块注释，如下案例
* 其中`@auth true`表示访问需要权限验证
* 其中`@menu true`显示在菜单编辑的节点可选项
```php
/**
* 操作的名称
* @auth true  # 表示需要验证权限
* @menu true  # 在菜单编辑的节点可选项
*/
public function index(){
   // @todo
}
```

框架指令
--
* 执行 `build.cmd` 可更新 `Composer` 插件，会删除并替换 `vendor` 目录
* 执行 `php think run` 启用本地开发环境，访问 `http://127.0.0.1:8000`

* 线上代码更新
>* 执行 `php think xsync:admin` 从线上服务更新 `admin` 模块的所有文件（注意文件安全）
>* 执行 `php think xsync:wechat` 从线上服务更新 `wechat` 模块的所有文件（注意文件安全）
>* 执行 `php think xsync:service` 从线上服务更新 `service` 模块的所有文件（注意文件安全）
>* 执行 `php think xsync:plugs` 从线上服务更新 `plugs` 静态插件的部分文件（注意文件安全）
>* 执行 `php think xsync:config` 从线上服务更新 `config` 项目配置的部分文件（注意文件安全）

* 微信资料管理
>* 执行 `php think xfans:all` 更新已经对接的公众号全部列表
>* 执行 `php think xfans:list` 更新已经对接的公众号粉丝列表
>* 执行 `php think xfans:tags` 更新已经对接的公众号标签列表
>* 执行 `php think xfans:black` 更新已经对接的公众号黑名单列表

* 守护进程管理
>* 执行 `php think xtask:reset` 重启消息任务守护进程
>* 执行 `php think xtask:start` 启动消息任务守护进程
>* 执行 `php think xtask:state` 查询消息任务守护进程
>* 执行 `php think xtask:stop` 暂停消息任务守护进程

* 其它自定工具
>* 执行 `php think xclean:session` 清理无效的会话SESSION文件
>* 执行 `php think xclean:store` 清理无效的订单信息及定时任务
