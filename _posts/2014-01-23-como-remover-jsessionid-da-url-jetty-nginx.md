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

<code>
  <context-param>
    <param-name>org.eclipse.jetty.servlet.SessionIdPathParameterName</param-name> 
    <param-value>none</param-value>
  </context-param>	
</code>


