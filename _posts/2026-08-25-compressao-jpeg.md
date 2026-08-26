---
layout: post
title: "Como o JPEG engana seus olhos: compressão de imagens na prática"
date: 2026-08-25
---

Todo mundo já salvou uma foto em JPEG sem pensar muito nisso. Por trás desse formato existe uma ideia simples: em vez de guardar a imagem pixel por pixel, o JPEG explora os limites da percepção visual humana para descartar informação que o olho dificilmente notaria.

**Espaço de cor**

Antes de comprimir, o JPEG converte a imagem de RGB para YCbCr, separando luminância (brilho) de crominância (cor). O olho humano é muito mais sensível a variações de brilho do que a variações de cor, então o JPEG guarda o canal de luminância quase inteiro e já reduz a resolução dos canais de cor pela metade, sem perda perceptível relevante.

**Blocos e a Transformada de Cosseno Discreta**

A imagem é dividida em blocos de 8x8 pixels. Cada bloco passa por uma DCT, que converte os valores de pixel em frequências, separando variação suave de detalhe fino. O olho percebe muito menos as frequências altas, então o JPEG arredonda ou zera essas frequências sem perda tão visível.

**Quantização**

É nessa etapa que a perda de fato acontece. Quanto maior a compressão escolhida, mais frequências altas são arredondadas para zero. Por isso imagens muito comprimidas mostram aqueles blocos quadriculados: é a malha dos blocos 8x8 aparecendo pela perda de detalhe.

**JPEG e PNG**

Essa lógica é exclusiva de formatos com perda, como o JPEG. O PNG é sem perda: comprime reorganizando padrões repetidos, mas nunca descarta informação. Por isso arquivos PNG tendem a ser maiores para fotos, mas são ideais para imagens com texto, ícones e bordas nítidas.

A curiosidade fica por conta do nome: JPEG vem de Joint Photographic Experts Group, o comitê que criou o padrão em 1992. A sigla virou tão comum que hoje a maioria esquece que é o nome de um grupo de pessoas, não de uma tecnologia.

<img width="473" height="325" alt="jpegcompressao" src="https://github.com/user-attachments/assets/258b81f3-8fec-441e-b6e6-23a4c770ea42" />
