--- 
layout: post
title: "Configurando virtual host no Glassfish"
tags: [virtual host, glassfish, dominio, dominios]
---

![glassfish_logo](/images/glassfish_logo.png)

Depois de buscarmos algumas op&ccedil;&otilde;es de arquitetura para um projeto SAAS aqui da empresa
acabamos optando pela arquitetura [JSF] (http://www.oracle.com/technetwork/java/javaee/javaserverfaces-139869.html) + [EJB] (http://pt.wikipedia.org/wiki/Enterprise_JavaBeans) + [EclipseLink] (http://wiki.eclipse.org/EclipseLink/Examples/JPA/JSF_Tutorial)
e consequentemento optamos pelo [Glassfish] (https://glassfish.java.net/getstarted.html) como servidor de aplica&ccedil;&atilde;o, principalmente
pelo seu console de administra&ccedil;&atilde;o e a interface de linha de comando. 

Uma das d&uacute;vidas era se o Glassfish na sua vers&atilde;o Open Source seria indicado para rodar
a aplica&ccedil;&atilde;o em produ&ccedil;&atilde;o. Esta sendo excelente a experi&ecirc;ncia, o servidor &eacute; est&aacute;vel e escal&aacute;vel,
tando que passamos outras apps. para o mesmo servidor e agora precisamos configurar a 
funcionalidade de Virtual Host para respondermos para v&aacute;rios dom&iacute;nios diferente.