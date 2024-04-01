# giflib
GNU Emacs30.0.50に含まれる`java/INSTALL`にしたがってパッチを適用したgiflibモジュールのレポジトリ。

# 作成した手順
1. [Google Gitのgiflib](https://android.googlesource.com/platform/external/giflib)をclone

```bash
$: git clone https://android.googlesource.com/platform/external/giflib
```

2. `nougat-release`ブランチから修正用ブランチ`my/nougat-release`をcheckout

```bash
$: cd giflib
$: git checkout nougat-release
$: git checkout -b my/nougat-release
```

3. `java/INSTALL`にしたがいpatchを適用

```bash
$: patch -p1 < PATCH_FOR_GIFLIB.patch
```

4. 上記patch ファイルとpatch適用後ファイルをcommitして空レポジトリにpush

```bash
$: git add -A
$: git commit -m 'nanika commit messages...'
$: gh repo create my-giflib --public
$: git remote add mine https://github.com/JIBUN/my-giflib.git
$: git branch -M my/nougat-release
$: git push -u mine my/nougat-release
```