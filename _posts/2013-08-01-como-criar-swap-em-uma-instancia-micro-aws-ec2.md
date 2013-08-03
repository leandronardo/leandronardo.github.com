--- 
layout: post
title: "Como criar swap em uma inst&acirc;ncia micro AWS EC2"
tags: [AWS, EC2, micro inst&acirc;ncia, swap, amazon web service]
---

![AWS](/images/logo_aws.png)

A Amazon web service disponibiliza uma inst&acirc;ncia [EC2 micro](http://aws.amazon.com/pt/ec2/) (que &eacute; de gra&ccedil;a por um ano), com pouco de mais de 600 MB de mem&oacute;ria RAM.  Porem esta instancia nao tem swap por padrao, e se algum processo seu demandar mais memoria do que a existente o processo sera morto.

Para verificar a swap (Estou usando Ubuntu v.12):

<code>
$ free
</code>

	ubuntu@ip-10-xxx-26-xxx:~$ free
	total used free shared buffers cached
	Mem: 609468 600316 9152 0 16956 64428
	-/+ buffers/cache: 518932 90536
	Swap: 0 0 0

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
