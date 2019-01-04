---
layout: post
title:  "Como reutilizar sua SSH Key"
image: ''
date: 2018-12-31 15:00:00
created: 2018/12/31
by: Ana Paula Mendes
tags:
- linux
- ssh
- devops
- terminal
description: ''
categories:
- Security
---

![Um gatinho digitando em um computador, sentado em uma cadeirinha](https://media.giphy.com/media/13HBDT4QSTpveU/giphy.gif)

Se você quer trocar de computador ou formatar o seu atual e já está utilizando a sua SSH Key pública para se autenticar em servidores e algumas contas, daria um trabalhão gerar uma nova chave no seu novo ambiente e trocar em todos os locais que você está utilizando-a, né?! Eu vou te ajudar hoje a resolver esse problema tendo menos trabalho! =)

Antes de formatar o seu computador ou trocá-lo, você deve copiar a pasta chamada .ssh em algum lugar, pode ser um pen-drive. Geralmente esta pasta fica localizada na sua home e fica oculta. Daí você pode pressionar Ctrl + H e ela irá aparecer.

Dentro da pasta .ssh irá ter alguns arquivos nomeados como: id_rsa (sua chave privada), id_rsa.pub (sua chave pública) e algum ou alguns arquivos de configurações. Se estiverem com nomes diferentes, no momento que você gerou pode ter renomeado, mas não terá problema. Por padrão eu vou utilizar os nomes id_rsa e id_rsa.pub.

Você copiou para o destino desejado? Sim? Então vamos prosseguir!

Já no seu novo ambiente sem as chaves, você vai seguir os seguintes passos:

Copie sua pasta .ssh de onde você salvou e cole na home do seu ambiente novo:

> Quer fazer pelo terminal? Abaixo o comando para copiar e colar a
> pasta.
>
> cp caminho_do_arquivo caminho_de_destino

Já com sua pasta .ssh em sua nova home, verifique se todos os arquivos estão dentro da pasta certinho para prosseguir. Agora vamos alterar as permissões das chaves:
```
sudo chmod 600 ~/.ssh/id_rsa
sudo chmod 600 ~/.ssh/id_rsa.pub
```
Pronto? Agora vamos inicializar o ssh-agent em background:
```
eval $(ssh-agent -s)
```
E pra finalizar vamos fazer o ssh-agent realmente utilizar a sua SSH Key que foi copiada:
```
ssh-add ~/.ssh/id_rsa
```

E é isso! Agora você pode acessar suas contas facim facim! haha

Gostou do help? Curte e compartilha com as pessoas! ❤

Segue nas redes também:

-   [Instagram: @ananoterminal](https://www.instagram.com/ananoterminal/)
-   [Twitter: @ananoterminal](https://twitter.com/ananoterminal)
-   [Facebook: /ananoterminal](https://www.facebook.com/ananoterminal/)
-   [Medium: /ananoterminal](https://medium.com/ananoterminal)
-   [Github: /ananoterminal](https://github.com/ananoterminal)
