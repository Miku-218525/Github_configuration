# Github_configuration
## 配置Git
    1.安装时设置默认使用vs code作为编辑器
    2.SSH：
        （1）生成密钥：ssh-keygen -t rsa -b 4096 -C "<your_email@example.com>"
        （2）将~/.ssh/id_rsa.pub中的密钥存在Github.com
        （3）在~/.ssh/config中配置SSH：
            Host github.com
                Hostname ssh.github.com
                Port 443
                User git
                IdentityFile C:\\Users\\Miku/.ssh/id_rsa
        （4）检查是否连接成功：ssh -T git@github.com
    3.SSL：
        如果：SSL certificate problem: unable to get local issuer certificate
        则：（按顺序操作，直到成功）
        （1）（默认）使用系统的CA证书：git config --global http.sslCAinfo <Git安装路径/...>ca-bundle.crt
        （2）手动下载证书并更新：
            下载网站：https://curl.se/ca/cacert.pem
            更新指令：git config --global http.sslCAinfo <下载文件存放路径>
        （3）禁用SSL验证（不推荐）：git config --global http.sslVerify false
    4.以上步骤失败则安装软件：Github Desktop

    