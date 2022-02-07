# mysql workbench 菜单中文汉化

## 说明

> `MySQL workbench` 版本: 8.0.x
>
> `MySQL workbench` 是一个面向数据库架构师、开发人员和dba的统一可视化工具。`MySQL` 工作台为服务器配置、用户管理、备份等提供了数据建模、`SQL` 开发和全面的管理工具。`MySQL Workbench` 在 `Windows`、`Linux` 和 `MacOS` 上可用。
>
> MySQL工作台使DBA、开发人员或数据架构师能够可视化地设计、建模、生成和管理数据库。它包括数据建模师创建复杂的ER模型、正向和逆向工程所需的一切，还提供了执行困难的变更管理和文档任务（通常需要大量时间和精力）所需的关键功能。

## 文件说明

* `main_menu_en.xml` *英文*(*原版自带*)
* `main_menu.xml` *中文版*

> PS：为什么还有英文版本呢？
>
> * 主要是与现有 `mysql workbranch` 的 `main_menu.xml` 进行对比，新增删除等，毕竟并不是所有人都是用的 `8.x` 版本，日后新增菜单也可以很快找到不同来进行修改。

### 使用说明

复制 `main_menu.xml` 替换 `mysql workbench` 安装目录的 `data/main_menu.xml` 文件。

MacOS: /Applications/MySQLWorkbench.app/Contents/Resources/data/main_menu.xml

Windows(默认): C:\Program Files\MySQL\MySQL Workbench 8.0 CE\data\main_menu.xml

## 连 MySQL 报错：SSL connection error

```shell
# 1. 先退出 mysql workbench （8.0.27+）
# 2. 执行下面的代码，windows 在 git bash 窗口中执行命令
sed -i "s/useSSL\">2/useSSL\">0/" ${APPDATA}/MySQL/Workbench/connections.xml # windows
sed -i "s/useSSL\">2/useSSL\">0/"  ${HOME}/.mysql/workbench/connections.xml # 应该是这个目录

## 把文件 connections.xml 中 useSSL 的值改成 0 即可
```
