--- 
layout: post
cover: https://dl.dropboxusercontent.com/s/nowfnmx1d7zdh76/logo_aws.png
title: "Como criar swap em uma inst&acirc;ncia micro AWS EC2"
tags: [AWS, EC2, micro inst&acirc;ncia, swap, amazon web service]
---

![AWS](/images/logo_aws.png)



Execute os comandos:
<br/>
<code>
$ sudo dd if=/dev/zero of=/var/swapfile bs=1M count=1024
</code>
<br/>
<code>
$ sudo mkswap /var/swapfile
</code>
<br/>
<code>
$ sudo swapon /var/swapfile
</code>

Execute o comando free novamente:

<code>
$ free
</code>

	ubuntu@ip-10-xxx-26-xxx:/etc$ free
	total used free shared buffers cached
	Mem: 609468 600544 8924 0 6008 75284
	-/+ buffers/cache: 519252 90216
	Swap: 1048572 1188 1047384

Pronto! A swap foi criada. Porem ao reiniciar a m&aacute;quina esse configura&ccedil;&atilde;o sera perdida. Para tornar permanente nesta alteracao, adicione a seguinte linha no final do arquivo /etc/fstab:

<code>
$ sudo vi /etc/fstab
</code>


	/var/swapfile none swap sw 0 0

E isso ai, espero que tenha ajudado.<br/>
Se tiver uma d&uacute;vida ou se o post ajudou, deixe uma mensagem.

Abra&ccedil;os,<br/>
Leandro Nardo
