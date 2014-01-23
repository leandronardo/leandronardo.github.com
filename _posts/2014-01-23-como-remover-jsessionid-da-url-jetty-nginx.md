--- 
layout: post
title: "Como remover o jsessionid da URL. Jetty + NGINX"
tags: [jetty, nginx, jsessionid, proxy reverso, remover jsession]
---

![jetty_nginx](/images/servers.png)


<code>
  <context-param>
    <param-name>org.eclipse.jetty.servlet.SessionIdPathParameterName</param-name> 
    <param-value>none</param-value>
  </context-param>	
</code>

Reinicie o servidor e est&aacute; pronto.

Quero deixar registrado que estamos muito contentes com o baixo consumo de mem&oacute;ria e a &oacute;tima performance do Jetty, isso sem fazer ainda qualquer tunning pelo Nginx.

Espero que ajude.
Qualquer d&uacute;vida ou sugest&atilde;o deixe uma mensagem.  
