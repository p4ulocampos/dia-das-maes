📖 Documentação e Guia de Estudos: Presente da Mariana
Bem-vindo(a) ao "por trás das câmeras" do seu presente! Este documento foi criado para ajudar você a entender como o código funciona passo a passo. Assim, você poderá fazer manutenções, alterar textos ou adicionar mais fotos no futuro sem medo de quebrar tudo.

🏗️ A Regra de Ouro: Como a Web Funciona
Uma página de internet (como o seu arquivo index.html) é a união de três "idiomas" diferentes trabalhando juntos num mesmo arquivo:

HTML (<body>): É o esqueleto. Ele diz o que está na tela (os botões, os textos, as imagens).

CSS (<style>): É a roupa e maquiagem. Ele diz como as coisas se parecem (cores, tamanho, posição, 3D, animações).

JavaScript (<script>): É o cérebro. Ele dita o comportamento (passar de página quando clica, esconder a carta, fazer os cálculos de qual foto mostrar).

🔎 Entendendo o Esqueleto (HTML)
Se você olhar no código, tudo que está dentro de <body> e </body> é o que aparece na tela. Nós dividimos a tela em 3 "Sessões" principais usando a tag <div> (que é como se fosse uma "caixa" invisível para agrupar coisas).

1. Envelope (<div id="envelope-container">)
A caixa principal do envelope. Dentro dela, temos uma caixa menor para o destinatário ("Mariana Silva Neto").

2. A Carta (<div id="letter-container">)
Aqui ficam todos os parágrafos (<p>) do seu texto amoroso. Também colocamos dois botões com setas:

onclick="voltarParaEnvelope()": Uma seta para a esquerda (voltar).

onclick="mostrarCapaAlbum()": Uma seta para a direita (avançar).

3. O Álbum de Memórias (<div id="album-container">)
A parte mais complexa. Ela guarda:

A capa do álbum (album-cover).

O álbum aberto (opened-album).

Dentro do álbum aberto, temos duas "páginas" (page-left e page-right).

Cada página contém 3 espaços vazios para imagens (<img>), identificados com nomes únicos (ex: id="img-left-1").

🎨 Entendendo a Estética (CSS / <style>)
O CSS usa os IDs (indicados por #) e as Classes (indicadas por .) do HTML para dar estilo a eles.

Os Grandes Destaques Visuais:
Fontes do Google (font-family): Usamos a Caveat (letra de mão) e a Playfair Display (letra chique de jornal) importadas lá no topo do arquivo.

O Fundo da Carta (Mapa do Tesouro): Se você olhar o #letter-container, verá um código gigante começando com background: url('data:image/svg+xml.... Isso é um desenho (SVG) criado diretamente por código para simular as linhas de um mapa antigo!

A Textura do Álbum: Na .album-cover::after, usamos repeating-linear-gradient para criar listras finíssimas que simulam a textura de couro de um livro antigo.

O Efeito 3D e Animações (@keyframes):

Para o álbum abrir, usamos transform: scale(1) rotateX(45deg); simulando o álbum deitando na mesa.

Para as páginas virarem, usamos perspective(1200px) e rotateY(), que faz o elemento girar no eixo Y (como uma porta abrindo), criando a ilusão 3D de folhear o papel.

CSS Grid (display: grid): Nas páginas do álbum, usamos o Grid. É um sistema que cria "tabelas" invisíveis. Definimos grid-template-columns: repeat(3, 1fr), o que significa: divida o espaço em 3 colunas de tamanhos iguais. É por isso que cabem 3 fotos perfeitamente em cada página.

🧠 Entendendo o Cérebro (JavaScript / <script>)
Esta parte fica no final do arquivo e é ativada quando o usuário clica nas coisas.

A Lista de Fotos (Array)
JavaScript
const fotos = [ "/static/img/foto1.jpeg", "/static/img/foto2.jpeg", ... ];
A variável const guarda uma lista com os caminhos das suas fotos. O JavaScript sempre começa a contar do ZERO. Então, a "foto1" é a posição 0.

A Variável de Controle
JavaScript
let paginaAtual = 0;
A variável let pode ter seu valor alterado. Ela serve para o computador lembrar em que página o usuário está. Começamos na 0.

Como a troca de páginas funciona (carregarFotos)
Como agora você tem 3 fotos na esquerda e 3 na direita, o código faz o seguinte cálculo:

Ele limpa as imagens para tocar a animação de página virando.

Ele pega a foto da paginaAtual + 0, +1 e +2 e joga na página da esquerda.

Ele pega a foto da paginaAtual + 3, +4 e +5 e joga na página da direita.

No total, ele exibe 6 fotos por vez na tela.

Quando você clica em proximaPagina(), o código pega a paginaAtual e soma + 6 (paginaAtual += 6;). Assim, ele pula as fotos que já foram mostradas e exibe a próxima remessa.

🛠️ Guia de Manutenção e Alterações (Como "Hackear" seu Código)
Aqui é onde você coloca a mão na massa para modificar seu projeto no futuro:

1. Como alterar os textos da carta?
No HTML, procure por <div class="letter-text">. Os textos estão dentro das tags <p> (parágrafo). Basta apagar o texto escrito em preto e digitar o novo.
Dica: Nunca apague os símbolos de <p> e </p>, eles são as paredes que seguram o seu texto!

2. Como adicionar MUITO mais fotos?
Digamos que você queira colocar 20 fotos no total.

Coloque as fotos na pasta /static/img/ renomeadas corretamente (foto11.jpeg, foto12.jpeg...).

Vá até o JavaScript (<script>) no final do arquivo.

Adicione as novas fotos na lista const fotos, sempre entre aspas e separadas por vírgula. Exemplo:

JavaScript
const fotos = [
    "/static/img/foto1.jpeg", 
    /* ... outras fotos ... */
    "/static/img/foto10.jpeg",
    "/static/img/foto11.jpeg", // <-- SÓ ADICIONAR AQUI
    "/static/img/foto12.jpeg"  // <-- A ÚLTIMA NÃO PRECISA DE VÍRGULA NO FINAL
];
A matemática do JavaScript (paginaAtual + 6) já é inteligente o suficiente para saber que existem mais fotos e continuará gerando as páginas automaticamente!

3. Como alterar a cor de fundo do site?
Lá no topo, na tag <style>, procure por:

CSS
body {
    background-color: #fce4ec;
}
Esse #fce4ec é um "Código Hexadecimal" (rosa bem clarinho). Para mudar:

Pesquise no Google por "Seletor de cores" ou "Color picker hex".

Escolha a cor, copie o código que começa com # (ex: #e3f2fd para azul bebê).

Substitua no código e salve.

4. Como mudar o destinatário no envelope?
Procure no HTML (logo após a tag <body>) por:

HTML
<div class="destinatario">Mariana Silva Neto</div>
Basta alterar o nome que está no meio!