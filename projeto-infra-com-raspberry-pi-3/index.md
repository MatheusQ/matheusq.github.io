# Projeto Infra com Raspberry PI 3 Model B / Origem do Site


Esse é o projeto que deu vida ao site Coisas de Infra. A seguir nesta página, contextualizo o projeto, conto como surgiu a ideia desse site e quais os objetivos com tudo isso. Além disso, também escrevo sobre as motivações.

<!--more-->

Antes de mais nada, os artigos técnicos sobre o projeto seguirão divididos em partes (parte 1, parte 2, etc). Essa sequência de partes formará um sistema base que será utilizado em outros artigos que não farão parte desta sequência.

O índice dos artigos estão em seguida deste parágrafo. Sempre que um novo artigo desta sequência for postado, atualizarei este índice com os respectivos links para os artigos.

Teste `teste`

{{< admonition note "Índice" >}}
  * [Contextualização](#contextualização)
  * [Objetivos](#objetivos)
  * [Motivações](#motivações)
  * [Curiosidade](#curiosidade)
{{< /admonition >}}

> * [Contextualização](#contextualização)
> * [Objetivos](#objetivos)
> * [Motivações](#motivações)
> * [Curiosidade](#curiosidade)

## Contextualização

A ideia inicial desse projeto era implementar um sistema que me servisse de plataforma de estudo, tendo a base necessária para a realização de experimentos em Administração de Sistemas, Redes de Computadores e Segurança da Informação.

Por ter tido a experiência de escrever relatórios e artigos para um projeto de Iniciação Científica durante a minha graduação na faculdade, senti necessidade de ter um “lugar” para escrever sobre esse projeto, para poder compartilhar conhecimento, criar um portfólio de experiências e conteúdos, além de que também poderia servir para possíveis discussões sobre os assuntos.

Logo, a ideia do projeto mais a necessidade de um lugar para escrever sobre ele se transformou em uma ideia só: implementar um servidor residencial que gerencie a rede e também sirva de base para ser um servidor web, assim podendo hospedar o blog onde eu escreveria sobre essas implementações/experiências.

Assim nasceu o blog Coisas de Infra.

## Objetivos

Então, formei objetivos para o projeto. Foram eles:

* Custo zero e Software Livre. Tirando o custo com os periféricos (hardwares) a ideia foi seguir o “faça você mesmo” e utilizar somente ferramentas (e sistema operacional) Free Software ou Open Source, assim não gastando com licenças de softwares pagos.
  
* Estudar sobre Administração de Sistemas Linux, Redes, Segurança da informação, ou basicamente, sobre Infraestrutura de T.I.
  
* Mostrar um pouco do meu trabalho.
  
* Compartilhar conhecimento e informação e estimular discussões sobre tudo que for abordado no blog.

* Compactuar com as ideias da comunidade Open Source/Free Software. Acho que já foi possível captar esse objetivo após ler o primeiro.

## Motivações

Alguns porquês do projeto possuir essa configuração (Raspberry, Free Software, Experimentos de Infra).

* Por ser um Single Board Computer (computador de placa única), o Raspberry Pi é um computador completo com baixo consumo de energia elétrica, sendo ideal para ficar ligado o tempo todo sem trazer custo significativo na conta de energia. Possui poder computacional suficiente para gerir uma rede residencial e também dar conta do tráfego de um site de pequeno porte.

* Administrar um sistema Linux, implementar e configurar serviços que esse sistema operacional oferece para gerenciamento de rede e segurança. Eu acredito que implementar e configurar serviços Free Software / Open Source nos deixam mais perto de como esses serviços funcionam e nos dão a base para trabalhar com qualquer outra solução.

* O modem/roteador Wi-Fi oferecido pela minha provedora de Internet está ultrapassado e fornece Wi-Fi no padrão 802.11G. Já o Raspberry Pi 3 Model B é capaz de fornecer Wi-Fi em um padrão mais recente, o 802.11N. Ao configurar o Raspberry Pi 3 como roteador Wi-Fi, torna-se possível realizar comparações entre o desempenho do modem/roteador da provedora assim como a diferença dos padrões Wi-Fi.

* Obter a experiência de implementar e gerir todos os serviços necessários para que um servidor web funcione bem. Caberá aqui bastante preocupação com a segurança.

## Curiosidade

O nome do site veio durante o banho (bem clichê, mas verdade). Como os primeiros artigos do site seriam sobre o projeto com o Raspberry Pi, dispositivo o qual se encaixa dentro da “Internet das Coisas”, e o site com um maior foco em assuntos relacionados a Infraestrutura de T.I, ficou então Coisas de Infra.


