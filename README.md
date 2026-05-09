# 💌 Presente Digital de Dia das Mães - Mariana

Este é um projeto web interativo e emocional criado como um presente especial para a Mariana. O site conduz a utilizadora por uma jornada de memórias, começando por uma carta animada e terminando num álbum de fotografias 3D de alta capacidade, com várias surpresas visuais feitas puramente com código.

## ✨ Funcionalidades e Animações

O projeto foi construído com atenção minuciosa aos detalhes visuais e interativos:

* **✉️ Envelope Interativo:** Uma animação de abertura suave ao passar o rato e clicar, revelando a carta.
* **📜 Carta em Pergaminho CSS:** Um design de papel antigo e desgastado gerado 100% via CSS, usando gradientes radiantes, filtros de ruído e sombras internas para um aspeto realista.
* **🌸 Flor Animada (Homenagem à Fiore):** Uma flor desenhada com formas CSS que desabrocha suavemente no final da carta após a assinatura.
* **📖 Álbum de Memórias 3D Avançado:**
* **Capacidade para 50 fotos:** Estrutura dinâmica que organiza todas as imagens automaticamente.
* **Layout 2x2:** Exibe 4 fotos por página (8 fotos visíveis por spread), otimizando o espaço do álbum.
* **Efeito de Folhear Realista:** Animação de transição das páginas da **direita para a esquerda**, simulando a leitura de um livro real.


* **🔍 Lightbox (Zoom Interativo):** As fotos aumentam levemente ao passar o rato e, ao clicar, expandem-se em ecrã inteiro com fundo escuro.
* **💐 Surpresa Final (Buquê Vetorial):** Ao fechar o álbum, um buquê desenhado em SVG (com 10 rosas azul, branca e vermelha) surge na tela com animação de flutuação.
* **✍️ Tipografia Delicada:** Mensagem final escrita com a fonte `'Dancing Script'`, proporcionando um toque de caligrafia manual elegante.

## 🛠️ Tecnologias Utilizadas

* **HTML5:** Estrutura semântica e gráficos vetoriais (SVG inline).
* **CSS3:** Animações `@keyframes`, transformações 3D, `CSS Grid` (para o layout das fotos) e `Flexbox`.
* **JavaScript (Vanilla):** Lógica de paginação dinâmica, controlo de animações e sistema de Lightbox.
* **Python (Flask):** Servidor minimalista para servir o site de forma profissional.

## 📁 Estrutura de Pastas

```text
/
├── app.py                  # Servidor Python
├── README.md               # Documentação do projeto
├── templates/
│   └── index.html          # Ficheiro principal (HTML/CSS/JS)
└── static/
    └── img/                # Pasta das 50 fotos (foto1.jpeg até foto50.jpeg)

```

## 🚀 Como Executar

1. Instale o Flask: `pip install flask`
2. Execute o servidor: `python app.py`
3. Aceda no navegador: `http://localhost:8080`

## 📝 Notas de Manutenção

* **Fotos:** Para atualizar o álbum, basta substituir os ficheiros na pasta `static/img/`. O código está preparado para ler ficheiros com a extensão `.jpeg` e nomes numerados de 1 a 50.
* **Direção do Folhear:** A animação de folhear da direita para a esquerda foi configurada nas regras `@keyframes flipPageIn` e `flipPageOut` no CSS.
