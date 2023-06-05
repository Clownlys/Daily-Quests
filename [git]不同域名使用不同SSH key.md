## 不同域名使用不同SSH key

### 1. 问题描述

GitHub和公司仓库需要配置不同的SSH key,使用`ssh-keygen -t rsa -f {fileName}`生成文件名为`fileName`的SSH密钥后如何使用本地密钥文件执行clone操作

### 2. 问题分析

如何根据不同域名使用不同的SSH key

### 3. 解决方案

在`~/.ssh`目录下创建`config`文件，内容如下：

```shell
# GitHub
Host github.com
HostName github.com
IdentityFile ~/.ssh/id_rsa_github

# work
Host xxx.com
HostName xxx.com
IdentityFile ~/.ssh/id_rsa_work
```

### 4. 问题总结

- `Host`：自定义的域名
- `HostName`：实际的域名
- `IdentityFile`：SSH key文件路径
