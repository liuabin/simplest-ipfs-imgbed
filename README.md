# simplest-ipfs-imgbed

> 静态网页的最新地址：https://gateway.pinata.cloud/ipfs/QmVZ19cSQKhvtZJg8sxX9bMG9yXDfdzvKGBpDKYHke62Ah

最简单的 ipfs 图床 demo / The simplest ipfs image bed (demo) 

主要思路是：

* 图片放到 ipfs 网络上生成 hash
  * img -post-> hash
* 使用 txt 一行一条保存 hash
  * txt: hash \n hash ...
* txt 放到 ipfs 网络上生成 hash
  * txt -post-> hash
* 图床使用 txt hash 取得图片集 hashlist，再去 ipfs 网络获取显示图片
  * hash -get-> txt(string) -split-> hashlist -get-> images

存储 hashlist 的 txt 感觉可以用 GitHub 的 commit 托管其 hash 值变化

> ipns 也可以达到同样效果，但使用体验太差。