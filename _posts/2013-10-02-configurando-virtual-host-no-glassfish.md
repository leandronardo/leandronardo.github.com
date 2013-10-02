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

Vamos ao processo, que &eacute; simples:

1. Inicie o glassfish pela linha de comando ou pelo Eclipse.

2. Entre no console de admin. pelo link: `localhost:4848`

3. Navegue na arvore do menu at&eacute; Virtual Host

![vistual_host_glassfish](/images/glassfish_virtual_host_1.png)

4. Clique em New... para criar um novo virtual host

![novo_vh](/images/novo_virtual_host.png)

`Id:` que &eacute; obrigat&oacute;rio, preencha com um nome qualquer que fa&ccedil;a sentido para seu contexto.
`Hosts` tambem &eacute; obrigat&oacute;rio, preencha com o dom&iacute;nio que deve apontar para a app. separado por vingula.
`Importante`: Note que esse &eacute; o campo mais importante, se alguma coisa n&atilde;o funcionar provavelmente o erro esta nele.

5. O seu dom&iacute;nio deve apontar para o IP, DNS P&uacute;blico do load balance da m&aacute;quina onde esta instalado o Glassfish.

![configuracao_dominio](/images/conf_dominio.png)

&Eacute; isso ai. <br/><br/>
Qualquer d&uacute;vida ou sugest&atilde;o deixe uma mensagem. 