--- 
layout: post
title: "Como remover o jsessionid da URL. Jetty + NGINX"
tags: [jetty, nginx, jsessionid, proxy reverso, remover jsession]
---

![jetty_nginx](/images/servers.png)

Para solucionar um problema com virtual host do [Jetty] (http://www.eclipse.org/jetty/) que tinhamos, fizemos um proxy reverso com [Nginx] (http://wiki.nginx.org/Main/)
e ap&oacute;s todas as configura&ccedil;&otilde;es e os servers funcionando perfeitamente, o jsessionid come&ccedil;ou a ser escrito na URL, em todos os links dos sites. 

A solu&ccedil;&atilde;o para o problema &eacute; muito simples esta dispon&iacute;vel no site do jetty: [Jetty/Howto/SessionIds] (http://wiki.eclipse.org/Jetty/Howto/SessionIds).

Acrescentar no web.xml as seguintes linhas:

```xml
 <context-param>
    <param-name>org.eclipse.jetty.servlet.SessionIdPathParameterName</param-name> 
    <param-value>none</param-value>
  </context-param>	
```

Reinicie o servidor e est&aacute; pronto.

Quero deixar registrado que estamos muito contentes com o baixo consumo de mem&oacute;ria e a &oacute;tima performance do Jetty, isso sem fazer ainda qualquer tunning pelo Nginx.

Espero que ajude.
Qualquer d&uacute;vida ou sugest&atilde;o deixe uma mensagem.  
