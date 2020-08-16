#install vs code for go plugin 
Tools environment: GOPATH=N:\GoSpace
Installing 17 tools at N:\GoSpace\bin in module mode.
  gocode
  gopkgs
  go-outline
  go-symbols
  guru
  gorename
  gotests
  gomodifytags
  impl
  fillstruct
  goplay
  godoctor
  dlv
  gocode-gomod
  godef
  goimports
  golint

Installing github.com/mdempsky/gocode (N:\GoSpace\bin\gocode.exe) SUCCEEDED
Installing github.com/uudashr/gopkgs/v2/cmd/gopkgs (N:\GoSpace\bin\gopkgs.exe) SUCCEEDED
Installing github.com/ramya-rao-a/go-outline (N:\GoSpace\bin\go-outline.exe) SUCCEEDED
Installing golang.org/x/tools/gopls (N:\GoSpace\bin\gopls.exe) SUCCEEDED

All tools successfully installed. You are ready to Go :).
Installing github.com/acroca/go-symbols (N:\GoSpace\bin\go-symbols.exe) SUCCEEDED
Installing golang.org/x/tools/cmd/guru (N:\GoSpace\bin\guru.exe) SUCCEEDED
Installing golang.org/x/tools/cmd/gorename (N:\GoSpace\bin\gorename.exe) SUCCEEDED
Installing github.com/cweill/gotests/... (N:\GoSpace\bin\gotests.exe) SUCCEEDED
Installing github.com/fatih/gomodifytags (N:\GoSpace\bin\gomodifytags.exe) SUCCEEDED
Installing github.com/josharian/impl (N:\GoSpace\bin\impl.exe) SUCCEEDED
Installing github.com/davidrjenni/reftools/cmd/fillstruct (N:\GoSpace\bin\fillstruct.exe) SUCCEEDED
Installing github.com/haya14busa/goplay/cmd/goplay (N:\GoSpace\bin\goplay.exe) SUCCEEDED
Installing github.com/godoctor/godoctor (N:\GoSpace\bin\godoctor.exe) SUCCEEDED
Installing github.com/go-delve/delve/cmd/dlv (N:\GoSpace\bin\dlv.exe) SUCCEEDED
Installing github.com/stamblerre/gocode FAILED
Installing github.com/rogpeppe/godef (N:\GoSpace\bin\godef.exe) SUCCEEDED
Installing golang.org/x/tools/cmd/goimports (N:\GoSpace\bin\goimports.exe) SUCCEEDED
Installing golang.org/x/lint/golint (N:\GoSpace\bin\golint.exe) SUCCEEDED

1 tools failed to install.

gocode-gomod: failed to install [object Object]: Error: Command failed: N:\GoFiles\go1.15.windows-amd64\go\bin\go.exe get -v -d github.com/stamblerre/gocode
go get github.com/stamblerre/gocode: module github.com/stamblerre/gocode: Get "https://goproxy.cn/github.com/stamblerre/gocode/@v/list": dial tcp: lookup goproxy.cn: no such host
 undefined  

 # 解决方案 

PS N:\GoSpace\src> cd .\github.com\stamblerre\
PS N:\GoSpace\src\github.com\stamblerre> git clone https://github.com/stamblerre/gocode gocode

PS N:\GoSpace\src\github.com\stamblerre> go install github.com/stamblerre/gocode

# 还有一种解决方案 ，git clone 下来后， 用vscode 写代码提示安装 即可 

Tools environment: GOPATH=N:\GoSpace
Installing 1 tool at N:\GoSpace\bin in module mode.
  gocode-gomod

Installing github.com/stamblerre/gocode (N:\GoSpace\bin\gocode-gomod.exe) SUCCEEDED

All tools successfully installed. You are ready to Go :).

# git push github 免密码登录 
git config --global credential.helper store

打开~/.gitconfig文件，会发现多了一项:

[credential]

　　helper = store

此时,再次push  输入用户名和密码,以后再次push即可免去输入用户名和密码


在使用git push时报出如下的错误：
Fatal: HttpRequestException encountered.
Username for ‘https://github.com‘:
Password for ‘https://github.com‘:
之前时不需要输入的，现在需要输入了，原因是git更新了一个证书，我们本地需要再更新以下：
https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/tag/v1.14.0
进去后点击下载安装 GCMW-1.14.0.exe即可：

# next config 