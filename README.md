# Plamo Linuxで指定したカテゴリのパッケージをインストールする
## 概要
Plamo Linuxで指定したカテゴリのパッケージをインストールします。  
00_baseしかインストールされていないシステムでも、Pythonとget_pkginfoをインストールしてから指定したカテゴリのパッケージをインストールします。

## 使用方法
### 引数なしで実行する
```bash
$ get_category 
Do you want to install as root? [y/N] 
```
rootになってget_categoryを実行するか聞かれます。  
rootになった場合はPythonとget_pkginfoのダウンロードとインストールを行ないます。  
rootにならない場合はPythonとget_pkgnifoのダウンロードのみを行ないます。

Pythonとget_pkginfoが使える場合は、現在インストールされているカテゴリのアップデートパッケージを表示します。

# 引数にカテゴリ番号(0〜16)が与えられた場合
```bash
$ get_category 0-3
```

指定したカテゴリ番号にあるパッケージを表示します。  
カテゴリ番号に加えて、引数として-aを与えらられかつrootになった場合はパッケージのインストールを行ないます。  
引数として-dを与えられた場合はパッケージのダウンロードを行ないます。

# その他
ヘルプメッセージを参照してください。

```
$ get_category --help
Usage: ./get_category [OPTIONS] [NUMBERS]
Options:
  -a, --autoinstall       Enable auto installation
  -d, --download          Enable download
  --debug                 Enable debug mode
  -l, --localblock ARGS   Specify local blocks
  -h, --help              Show this help message and exit
  -p, --python            Download and Install Python only
  -g, --get_pkginfo       Download and Install get_pkginfo only
  NUMBERS                 Specify numbers in the range 0-16
     Example: get_category 2 4 6-8

Plamo Linux Category
  0: 00_base 1: 01_minimum 2: 02_devel 3: 03_libs 4: 04_x11
  5: 05_ext 6: 06_xapps 7: 07_multimedia 8: 08_daemons
  9: 09_printings 10: 10_xfce 11: 11_lxqt 12: 12_mate
  13: 13_tex 14: 14_libreoffice 15: 15_kernelsrc 16: 16_virtualization
```
