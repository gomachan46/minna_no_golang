# 開発環境構築

## インストール

homebrewとかで普通に入る

## GOROOT

Goのインストールパスのこと。

以前は環境変数で設定する必要があったが今はもうGoのバイナリにその情報が含まれているため設定は不要らしい。便利。

当たり前だけど自分でインストールディレクトリを変更した場合には変更は必要。

```
go env GOROOT
```

とかやると設定されているGOROOTを確認できる

## GOPATH

Go言語の開発を行うワークスペース

設定したパスの下で今後全てのGo言語の開発行うことになる。

GOROOT以外ならどこでも大丈夫

### よくある設定先

* $HOME/dev
* $HOME/go
* $HOME

```
export GOPATH=$HOME/dev
export PATH=$PATH:$GOPATH/bin
```

みたいな感じでパスを通してあげればOK

## go get

`go get` はgemのようなパッケージインストールの仕組みを提供してくれるコマンド。

```
go get github.com/motemen/gore
```

とかやると`gore`というライブラリをインストール出来る。

https://github.com/motemen/gore

GOPATH下は以下のような構成でディレクトリが掘られる

* bin/
  * 実行形式コマンド
* pkg/
  * パッケージオブジェクト
* src/
  * ソースコード
  
### gore

`gore`はGoの代表的なREPL。(むしろ標準じゃないんだなぁ)
