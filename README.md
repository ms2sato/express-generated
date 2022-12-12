# Codespace with node

# 現在の問題
nodenv install が docker build 内で動作させられていないので、立ち上げた後に手動で入れられることを確認している

```
root@01ae787aa448:/workspaces/express-generated# /usr/local/nodenv/bin/nodenv install 18.12.0
perl: warning: Setting locale failed.
perl: warning: Please check that your locale settings:
        LANGUAGE = (unset),
        LC_ALL = (unset),
        LANG = "en_US.UTF-8"
    are supported and installed on your system.
perl: warning: Falling back to the standard locale ("C").
Downloading node-v18.12.0-linux-x64.tar.gz...
-> https://nodejs.org/dist/v18.12.0/node-v18.12.0-linux-x64.tar.gz
Installing node-v18.12.0-linux-x64...
Installed node-v18.12.0-linux-x64 to /usr/local/nodenv/versions/18.12.0

root@01ae787aa448:/workspaces/express-generated# nodenv global 18.12.0
root@01ae787aa448:/workspaces/express-generated# node -v
v18.12.0
```

エラー。コマンド引数が分解されてしまっていることが原因の様子
```
#13 [10/10] RUN /usr/local/nodenv/bin/nodenv install 18.12.0
#13 sha256:96871b7ab2c7155d2fe39ed7964750e026fa1e5bb376626194a61472b5b7a6b1
#13 0.341 nodenv: no such command `install'
#13 ERROR: executor failed running [/bin/sh -c /usr/local/nodenv/bin/nodenv install 18.12.0]: exit code: 1
```