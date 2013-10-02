--- 
layout: post
title: "Como incluir atributos HTML5 em componentes JSF"
tags: [JSF, Java, HTML5, OmniFaces, primefaces]
---

![html5](/images/HTML5_Color_Black.jpg)

Quando precisei usar alguns atributos do HTML 5 como placeholder, autofocus, com
[Primefaces] (http://primefaces.org/) vi que n&atilde;o era poss&iacute;vel uma vez que estes
atributos n&atilde;o s&atilde;o recolhecidos. Depois de algum tempo pesquisando, encontrei 
a API [omnifaces] (https://code.google.com/p/omnifaces/) que tem algumas classes
utilit&aacute;rias para JSF e entre elas esta a [Html5RenderKit](http://wiki.omnifaces.googlecode.com/hg/javadoc/org/omnifaces/renderkit/Html5RenderKit.html),
respons&aacute;vel por renderizar os novos atributos.

O processo &eacute; bem simples:

1. Baixe a API [omniface](https://code.google.com/p/omnifaces/downloads/list).

2. Inclua o arquivo `omnifaces-X.X.jar` na sua biblioteca de jars.

3. No arquivo `faces-config.xml`, inclua:

	<pre><code>&lt;factory&gt;
	    &lt;render-kit-factory&gt;org.omnifaces.renderkit.Html5RenderKitFactory&lt;/render-kit-factory&gt;
	&lt;/factory&gt;
	</code></pre>
	
4. Inclua normalmente os atributos HTML5 nos componentes JSF:

	<pre><code>&lt;h:hinputText id="mensagem" value="#{usuario.mensagem}" placeholder="sua mensagem" /&gt;
	</code></pre>
<br/>	
&Eacute; isso ai. <br/><br/>
Qualquer d&uacute;vida ou sugest&atilde;o deixe uma mensagem.