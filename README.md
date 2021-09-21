## 事前準備

- ランタイム install

```
plenv install 5.30.1
plenv global 5.30.1
plenv install-cpanm
```

- module install

```
cpanm Convert::Base32
cpanm Authen::OATH
```

- conf準備

```
mkdir ~/.totp
touch ~/.totp/conf
chmod 700 ~/.totp
chmod 600 ~/.totp/conf
vim ~/.totp/conf
```

conf例

```
$ cat ~/.totp/conf
+{
  'example1'  => +{ secret => 'SECRETXXXXXXXXXXXXXXXXX', description => 'hoge' },
  'example2'  => +{ secret => 'SECRETYYYYYYYYYYYYYYYYY', description => 'foo'  },
}
```

- shebang 修正

```
echo "#\!$(which perl)"
vim totp
```

- pathを通す

```
totp_dir=/path/to/this/totp/dir
echo "export \"PATH=\$PATH:${totp_dir}\"" >> ~/.zshrc
source ~/.zshrc
```
