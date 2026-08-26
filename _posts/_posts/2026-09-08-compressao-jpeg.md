---
layout: post
title: "Como o JPEG engana seus olhos: compressão de imagens na prática"
date: 2026-09-08
---

Todo mundo já salvou uma foto em JPEG sem pensar muito nisso. Mas por trás desse formato existe uma ideia bem inteligente: em vez de guardar a imagem pixel por pixel, o JPEG explora os limites da nossa própria percepção visual pra descartar informação que o olho humano dificilmente notaria.

**O truque principal: espaço de cor**

Antes de comprimir, o JPEG converte a imagem de RGB para um espaço de cor chamado YCbCr, que separa luminância (brilho) de crominância (cor). Isso importa porque o olho humano é muito mais sensível a variações de brilho do que a variações de cor — então o JPEG guarda o canal de luminância quase inteiro, mas já reduz a resolução dos canais de cor pela metade sem perda perceptível relevante. Essa etapa sozinha já corta bastante dado.

**Divisão em blocos e a Transformada de Cosseno Discreta (DCT)**

A imagem é dividida em blocos de 8x8 pixels. Cada bloco passa por uma DCT, que converte os valores de pixel em frequências — basicamente, separa o que é "variação suave" do que é "detalhe fino". Como o olho humano percebe muito menos as frequências altas (detalhes muito finos), o JPEG pode arredondar ou até zerar essas frequências sem que a perda seja tão visível.

**Quantização: onde a perda realmente acontece**

É nessa etapa que o JPEG decide, de fato, o que descartar. Quanto maior o fator de compressão escolhido, mais agressivamente as frequências altas são arredondadas para zero. É por isso que imagens JPEG muito comprimidas ficam com aqueles blocos quadriculados visíveis (artefatos de compressão) — é literalmente a "malha" dos blocos 8x8 aparecendo porque perderam detalhe demais.

**JPEG vs. PNG: perda vs. sem perda**

Vale notar que essa lógica toda é exclusiva de formatos com perda (lossy), como o JPEG. O PNG, por outro lado, é sem perda (lossless): ele comprime dados reorganizando padrões repetidos, mas nunca descarta informação — por isso arquivos PNG tendem a ser maiores para fotos, mas são ideais para imagens com texto, ícones e bordas nítidas, onde qualquer artefato de compressão ficaria muito visível.

No fim, a escolha entre os dois formatos é basicamente uma escolha entre tamanho de arquivo e fidelidade — e entender esse trade-off é, na prática, aplicar diretamente os conceitos de processamento de imagem que estamos vendo na disciplina.
