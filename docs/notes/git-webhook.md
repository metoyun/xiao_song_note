# 利用宝塔webhook实现自动化部署
## 环境依赖
- Git
- 服务器必须装有WebHook (或者使用宝塔)
## webhook命令
``` sh
echo "-------------------------任务开始-----------------------------"
echo "$(date +'%Y-%m-%d %H:%M:%S')|$1开始调用接口"
cd /www/wwwroot/note.metoyun.com/note #网站根目录
git pull --rebase --no-rebase # 通过git pull 拉取新的代码
echo "$(date +'%Y-%m-%d %H:%M:%S')|$1调用接口执行完毕"
echo "-------------------------任务结束-----------------------------"

```

## 编写sh脚本示例

``` sh
#!/usr/bin/env sh
# 确保脚本抛出遇到的错误
set -e

echo "😀-------正在打包项目···-------"
# vuepress build docs为Vuepress打包命令
vuepress build docs

echo "👏-------添加文件到仓库-------"
# 添加所有更改的文件到git暂存区
git add .

echo "😯-------写入提交信息-------"
# 填写Git 提交信息
git commit -m "Updated $(date +'%Y-%m-%d %H:%M:%S')"

echo "😸提交仓库"
# 提交到远程仓库
git push -u origin master

echo "🤤$(date +'%Y-%m-%d %H:%M:%S')|开始到生产环境部署"
# 填写webhook地址
res=$(curl webhook地址)

echo "😯-------发送WebHook-------"

echo $res
# code 1 则执行成功

if [ "$res" == '{"code": 1}' ];then
# 走到此步骤既可说明自己的云服务器已经接受到webhook命令
echo "😏 $(date +'%Y-%m-%d %H:%M:%S')|生产环境部署请求已接受."

else
# webhook请求失败
echo "😨 $(date +'%Y-%m-%d %H:%M:%S')|部署请求未收到正常回应,请检查配置!"

fi
```