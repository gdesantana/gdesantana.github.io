---
layout: post
title: "Reflexão final: o que eu vi em Computação Visual"
date: 2026-11-08
---

No começo do semestre eu achava que Computação Visual era só visão computacional. Depois de cursar a disciplina, vejo que ela cobre o caminho completo da imagem, como ela é captada, como é processada e como é desenhada na tela.


**O que mais gostei**

Minha aula favorita foi a primeira, sobre o olho humano e a luz. Ver como a retina capta a informação e como isso virou base para câmeras, sensores e formatos de imagem deu sentido ao resto da matéria. Muita coisa que parecia só técnica depois se explica pela forma como a gente enxerga.

**Curiosidade:** o ponto cego existe em todo olho humano, na região onde o nervo óptico sai da retina e não há células sensíveis à luz. A gente não percebe porque o cérebro preenche a lacuna com base no que está ao redor, uma espécie de interpolação natural.

**Como os temas que estudamos se conectam**

Os sensores mostraram que a câmera imita o olho. No filtro de Bayer, usado na maioria dos sensores, existe o dobro de pixels verdes em relação a vermelho e azul, justamente porque o olho humano é mais sensível ao verde. Essa lógica também aparece no JPEG, que descarta o que a percepção humana quase não nota.

Depois vieram as técnicas de processamento. As transformações de intensidade e o histograma trabalham o contraste pixel a pixel, e a equalização redistribui as intensidades da imagem inteira. O método de Otsu usa o histograma para escolher o limiar de segmentação. A interpolação entra quando precisamos redimensionar ou girar uma imagem e criar valores para pixels que não existiam.

A filtragem espacial e a detecção de bordas mostraram que olhar a vizinhança do pixel muda o tipo de informação que se consegue extrair. Já o domínio de frequência mudou a forma de pensar a imagem, não como pixels, mas como variações suaves e detalhes finos.

Por fim, a pipeline gráfica e os shaders mostraram o caminho inverso: em vez de analisar uma imagem pronta, o computador gera uma a partir de dados. Foi quando entendi de verdade que o campo funciona nas duas direções.

**Curiosidade:** os shaders rodam na GPU e o mesmo programa é executado ao mesmo tempo para milhares de pixels. É por isso que um jogo consegue calcular iluminação e cor de cada pixel da tela dezenas de vezes por segundo.

**Na prática: a minha loja**

Eu tenho uma loja de roupas e uso computação visual no dia a dia dela. Tiro foto de cada peça e troco o fundo original pelo fundo padronizado da loja, para o catálogo ficar com a mesma cara em todas as fotos. Foi daí que surgiu a ideia do meu projeto de removedor de fundo na disciplina. Separar o objeto do fundo é um problema de segmentação, e conceitos que vimos, como histograma, limiarização e detecção de bordas, ajudam justamente nisso. Foi legal ver a matéria resolvendo um problema real do meu negócio.
**Exemplo Real**

<img width="2250" height="2813" alt="1" src="https://github.com/user-attachments/assets/68c36b94-24d8-4722-a9be-878e580f1b85" />


Foi uma matéria que me exigiu bastante. Eu nunca tinha estudado o assunto antes e muitos tópicos envolvem matemática e conceitos novos de uma vez. Mesmo assim, foi uma das matérias mais interessantes do curso, porque dá para ver o resultado do que se aprende diretamente na imagem.


Saio da disciplina com uma visão bem diferente da que eu tinha no primeiro post. Computação Visual não é uma técnica isolada, é uma cadeia que vai da luz que chega ao olho até o pixel que aparece na tela.
