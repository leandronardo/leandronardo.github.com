--- 
layout: post
title: "Criando swap em uma instância micro AWS EC2"
tags: [AWS, EC2, micro instância, swap, amazon web service]
---

Criando swap em uma instância micro AWS EC2.

A Amazon web service disponibiliza uma instância EC2 micro (que é de graça por um ano), com pouco de mais de 600 MB de memória RAM.  Porem esta instância não tem swap por padrão, e se algum processo seu demandar mais memória do que a existente o processo será morto.

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
<code>
$ sudo dd if=/dev/zero of=/var/swapfile bs=1M count=1024
$ sudo mkswap /var/swapfile
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

Pronto! A swap foi criada, porem ao reiniciar a máquina esse configuração será perdida. Para tornar permanente nesta alteração, adicione a seguinte linha no final do arquivo /etc/fstab:

<code>
$ sudo vi /etc/fstab
</code>

/var/swapfile none swap sw 0 0

É isso ai, espero que tenha ajudado.
Se tiver uma dúvida ou se o post ajudou, deixe uma mensagem.

Abraços,
Leandro Nardo
