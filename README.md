# Github Command Line Magic

### 安装hub
```
sha256sum:
140f1a8f1e5110fa2df21188904bb536267aa80e695bb7d125adc517152afb55  hub-linux-amd64-2.5.0.tgz
554553372d38c8781911946b6c66c178e546b9053c211e61324af772433e4de2  /usr/local/bin/hub
```
```
wget https://github.com/github/hub/releases/download/v2.5.0/hub-linux-amd64-2.5.0.tgz
tar xf hub-linux-amd64-2.5.0.tgz && cd hub-linux-amd64-2.5.0 && ./install
alias git=hub
```
参考：
https://hub.github.com/

#### 1.命令行fork
```
git clone https://github.com/github/hub.git
cd hub
echo "# 01" >> README.md
git add .
git commit -m "testing"
git fork # 第一次会要求用户名密码，用于创建token（https://github.com/settings/tokens），保存在：~/.config/hub。也可以通过配置环境变量：GITHUB_TOKEN，这样可以避免使用帐号密码
git remote -v
git push Zer0d0y
```

#### 2.create a new repository on the command line
```
mkdir 01 && cd 01
echo "# 01" >> README.md
git init
git add README.md
git commit -m "first commit"
hub create # 先配置GITHUB_TOKEN
# git remote add origin git@github.com:Zer0d0y/01.git
git push -u origin master

## ORGANIZATION repository
hub create tianyulab/Threat_Hunting_with_ELK
git remote add origin git@github.com:tianyulab/Threat_Hunting_with_ELK.git
git push -u origin master
```

#### 3.push an existing repository from the command line
```
mkdir 01 && cd 01
git remote add origin git@github.com:Zer0d0y/01.git
git push -u origin master
```
