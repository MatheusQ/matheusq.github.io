# Relançamento do blog Coisas de Infra: sai Wordpress entra Hugo

# Resumo

Em 2018, subi um blog em um servidor próprio usando wordpress. Depois, me mudei de cidade devido a um novo emprego e a gerência do servidor que ficava na casa dos meus pais se tornou mais difícil, além do tempo mais escasso. Pausei o projeto em 2019.

Em Julho de 2020 resolvi retomar o blog. Analisei que wordpress exigiria encontrar algum serviço de hospedagem, envolveria custos e etc. Isso me incentivou buscar outras soluções e tecnologia, então me deparei com o [github pages](https://pages.github.com/).

Com o github pages você consegue hospedar gratuitamente um site do tipo estático, usar um domínio próprio e com certificado válido (by [Let's Encrypt](https://letsencrypt.org)) para HTTPS.

Para me auxiliar a produzir um site estático legal eu encontrei o [Hugo](https://gohugo.io/) que "é um dos mais populares geradores de site estáticos de código aberto (open-souce)".

Com o conjunto GitHub Pages e Hugo, retomei meu blog!

# Não resumido, historinha, porquês e etc

Durante a faculdade, além do curso em si, duas coisas foram bem marcantes:

**1. Ter trabalhado em uma iniciação científica, a qual o projeto de pesquisa foi de minha autoria**

**2. Ter feito estágio com pessoas fantásticas na área de infraestrutura, área tema da minha iniciação científica e também linha de carreira que eu queria seguir (e segui).**

Quando eu terminei a faculdade, a falta de contato com o estágio e o término do projeto de iniciação científica, além do desemprego, me motivaram a criar um blog.

Produzir conteúdo e compartilhar conhecimento sobre a área que eu gosto são coisas que me inspiram e que me dão prazer.

Então, na metade de 2018 inventei de subir um blog usando um rapsberry. Foi uma experiência fantástica. Houveram muitos aprendizados. Vale citar alguns vários:

> * Descobri que as provedoras de internet bloqueiam tráfego entrante para clientes residencias nas portas "baixas", como exemplo, 80 e 443;
> * briguei com uma provedora de internet para fugir do CGNAT (ter um IPv4 público direto em meu modem, mesmo que dinâmico), a ter direito a tráfego entrante nas portas baixas, direito ao IPv6;
> * configurei minha rede em pilha dupla, IPv4 e IPv6, e meu blog era acessível em ambos os protocolos
> * aprendi a configurar o web server Apache;
> * aprimorei meus conhecimentos no firewall iptables;
> * aprendi a configurar o fail2ban para proteger minha conexão SSH;
> * fiz um monitoramento básico do sistema com Logwatch;
> * configurei o hostapd para o raspberry ser o roteador wi-fi da rede;
> * configurei um DHCP server;
> * fiz *hardening* do Apache e de outras configurações do Linux para aprimorar a segurança;
> * desenvolvi scripts em Shell Script para automatizar atualizações, backups entre outras tarefas;
> * aprendi a usar o cron;
> * aprendi muito sobre boot, particionamento, lvm, MBR e GPT;
> * até eletrônica: confira <https://coisasdeinfra.com/rodando-o-sistema-do-raspberry-pi-3-em-um-hd-externo/>
> * a instalar o wordpress e todo o necessário para botar o blog no ar
> * etc

Esse projeto com raspberry é o tipo de coisa que vou carregar comigo sempre, que vez ou outra eu vou contar, vou lembrar. Para mim esse projeto será uma lembrança tão importante quanto como deve ser para Bezos lembrar dos seus primórdios em uma garagem, rsrs. O ponto é: ali algo deu origem a um futuro próspero (independente da proporção).

Não posso deixar de citar e agradecer meu amigo Bruno Costa, cara que conheci quando tinha uns 8 anos, e que em 2018 (15 anos depois) me emprestou, ingenuamente, sua placa raspberry, a qual tomei conta e não devolvi por 2 anos hahaha. Valeu, mano! Você fez parte disso.

Então, depois de alguns meses de ter aprendido muita coisa e ter colocado o blog no ar, eu, que estava buscando emprego, consegui um e me mudei de cidade (e da casa dos meus pais). Fui trabalhar com infraestrutura. Objetivo de início de carreira cumprido. Com um mundo de novas coisas, novas rotinas, responsabilidades e um tempo mais escasso, a gerência do raspberry remotamente ficou mais difícil. Eu tinha um problema com a fonte de energia do raspberry, e vez ou outra, era necessário tirar da tomada e colocar de novo hahaha.

Com isso, eu não concluí todas as partes do projeto do raspberry <https://coisasdeinfra.com/projeto-infra-com-raspberry-pi-3/> que eu queria escrever e postar no blog. Faltaram partes onde eu escrever em como eu configurei o apache, o iptables, o fail2ban, o ssh, logwatch, o update, como instalei o wordpress, os *hardenings* que fiz, etc.

Mas deu tempo de postar muita coisa legal sobre o projeto também. Apesar do relançamento do blog, todo o conteúdo postado em 2018 e 1 post de 2019 foi conservado e pode ser acessado nesta publicação atual.

Eu não subi mais o blog no raspberry porque para conseguir ter um servidor web usando internet residencial foi uma luta. Briguei com a provedora de internet contratada na casa dos meus pais para conseguir tráfego entrante nas portas baixas e deu bastante trabalho. Não quis repetir a historia em minha nova moradia em outra cidade. Por isso, abandonei de ter o rapsberry como servidor do blog de qualquer lugar.

Então, para subir o antigo wordpress que eu havia configurado, eu precisaria pagar por um serviço de hospedagem. Sinceramente, achei muita coisa ter que pagar por um serviço de hospedagem e manter um wordpress (algo meio pesado, convenhamos, ao menos para um blog de portfólio) no ar. Então comecei a buscar outras soluções e deparei com o Hugo e depois com o GitHub Pages.

## Vamos começar por "o que é Hugo?".

Ninguém melhor que o própria documentação do Hugo para explicar o que ele é, então lá vai a citação, com a minha tradução (perdoem erros) do site <https://gohugo.io/about/what-is-hugo/>

{{< admonition type=quote title="O que é Hugo" open=true >}}

Hugo é um gerador de sites estático rápido e moderno escrito em Go e projetado para tornar a criação de sites divertida novamente.

Hugo é um *framework* de site de uso geral. Tecnicamente falando, Hugo é um gerador de sites estáticos. Ao contrário dos sistemas que constroem uma página dinamicamente com cada solicitação do visitante, Hugo constrói páginas quando você cria ou atualiza seu conteúdo. Uma vez que os sites são vistos com muito mais frequência do que editados, o Hugo foi projetado para fornecer uma experiência de visualização ideal para os usuários finais do seu site e uma experiência de escrita ideal para os autores do site.

Os sites construídos com Hugo são extremamente rápidos e seguros. Os sites da Hugo podem ser hospedados em qualquer lugar, incluindo Netlify, Heroku, GoDaddy, DreamHost, GitHub Pages, GitLab Pages, Surge, Aerobatic, Firebase, Google Cloud Storage, Amazon S3, Rackspace, Azure e CloudFront e funcionam bem com CDNs. Os sites Hugo são executados sem a necessidade de um banco de dados ou dependências em tempos de execução caros, como Ruby, Python ou PHP.

{{< /admonition >}}

Para experimentar o Hugo, de maneira simples e rápida, eu segui o tutorial da página <https://gohugo.io/getting-started/quick-start/>.

Depois, experimentei [temas](https://themes.gohugo.io/), coloquei mais conteúdos e fui moldando como queria colocar meus conteúdos no Hugo.

## Seguindo com GitHub Pages

Criei um repositório no GitHub para armazenar e versionar meus experimentos com Hugo.

Então, estudei o [GitHub Pages](https://pages.github.com/), pois precisava de um lugar/servidor para publicar meu site estático. E o GitHub Pages faz exatamente isso.
Basta você criar um repositório com configurações específicas na sua conta que o Git vai interpretar o conteúdo colocado nesse repositório como um site estático. Ou seja, se for colocado arquivos HTML, CSS e companhia, devidamente estruturados, o Git vai interpretar e publicar como site para você. Depois, indo além nas configurações, é possível configurar um nome de domínio customizado (que seja seu, claro) e ativar HTTPS.




