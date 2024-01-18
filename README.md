# 2024-mcm

2024年数模美赛仓库

## Github workflow

Git工作原理:

```shell
     git add . ------------> git commit -m 说明 -------------> git push
   (添加到暂存区)              （提交到本地仓库）             （推送到远程仓库）

```

- 将改动新增到远程仓库:`git add .` -> `git commit -m "commit message"` -> `git push`
- 更换代码分支: `git checkout branch_name`
- 发现错误, 需要回滚: `git reset [--soft,--mixed,--hard] commit_id`, 其中回滚模式有:

  - `soft`: 本地代码不变, 撤销`git push`和`git commit`, `git add`是有效的, 此时本地代码是`add`了没有`commit`的状态
  - `mixed`: 本地代码不变, 撤销`git push`, `git commit`, `git add`, 此时本地代码是没有`add`的状态
  - `hard`: 本地代码改变, 撤销全部命令, 连着本地文件一起回滚到指定的状态
 
- 从远程更新改动到本地: `git pull`

要点:

- 每完成一个改动(如增加了一个功能, 改变了一个算法)就要及时`commit`, 然后`push`到远程仓库
- `commit message`要简洁明了. `commit mseeage`的规范格式是: `<type>(<scope>): <subject>`. 其中:

    - `type`: 必须, 用来说明改动类型:
    
      - `feat`: 新功能feature
      - `fix`: 修复bug
      - `docs`: 增加或改动文档和注释
      - `style`: 格式(不影响代码运行的改动)
      - `refactor`: 重构(不是新增功能, 也不是修复bug)
      - `perf`: 性能优化
      - `test`: 为代码增加测试
      - `revert`: 回滚
      - `merge`: 合并分支
      - `sync`: 和主线同步

    - `scope`: 可选, 说明`commit`的影响范围, 如第一问, 第二问, 某个功能等
    - `subjuct`: 必须, 对`commit`目的的简短描述, 可以用中文, 结尾没有标点符号

以下是几个典型的`commit message`:

- feat:增加第二题的代码
- fix:维度错误
- docs:给xxx函数增加说明
- revert:寄,回滚到xxx

## 文件和命名规范

```shell
.
|---src // 存放解题代码的文件夹
|    |---命名规范: 题号-小问.py
|    |---1-1.py // 第一题第一小问的代码
|    |---1-2.ipynb
|
|---assets // 存放图片的文件夹
|     |---命名规范: 题号-小问-关键信息, 空格用下划线_代替
|     |---1-1-rays_with_i.png
|
|---drafts // 存放草稿的文件夹(是否要同步?)
|     |---乱七八糟的代码.py
|     |---乱七八糟的想法.md
|     |---其他的一些代码.ipynb
|
|---test.py // 不同步的代码, 当你想不起来某个函数怎么用, 或者想看看这么写会不会报错, 就在test文件里跑一下看看
|
|---test.ipynb // 不同步的代码, 同test.py
|
|---paper.tex // Latex论文(如果在本地写的话)
|
|---README.md // 项目自述文件
```
