## 压缩

- 基本用法 `tar -cf all.tar *.jpg`
- tar调用gzip `tar -czf all.tar.gz *.jpg`
- tar调用bzip2 `tar -cjf all.tar.bz2 *.jpg`
- tar调用compress `tar -cZf all.tar.Z *.jpg`
- `rar a jpg.rar *.jpg` // rar格式的压缩，需要先下载rar for linux
- `zip jpg.zip *.jpg` // zip格式的压缩，需要先下载zip for linux

## 解压

- *.tar 用 `tar –xvf`
- *.gz 用 `gzip -d` 或 `gunzip`
- *.tar.gz 和 *.tgz 用 `tar –xzf`
- *.bz2 用 `bzip2 -d` 或 `bunzip2`
- *.tar.bz2 用 `tar –xjf`
- *.Z 用 `uncompress`
- *.tar.Z 用 `tar –xZf`
- *.rar 用 unrar e
- *.zip 用 unzip
