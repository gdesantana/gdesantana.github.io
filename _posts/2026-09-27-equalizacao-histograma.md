---
layout: post
title: "Equalização de histograma: redistribuindo o contraste de uma imagem"
date: 2026-09-27
---

O histograma de uma imagem mostra quantos pixels existem em cada nível de intensidade, do mais escuro ao mais claro. Uma imagem de baixo contraste tem esse histograma concentrado numa faixa estreita, com poucos valores bem escuros ou bem claros.

A equalização de histograma redistribui essas intensidades de forma que ocupem toda a faixa disponível, de forma mais uniforme. O resultado costuma ser uma imagem com contraste mais equilibrado, revelando detalhes que antes estavam "escondidos" em regiões muito escuras ou muito claras.

A técnica usa a função de distribuição acumulada do histograma como transformação. Isso significa que ela não estica a imagem de forma linear e arbitrária, ela se baseia na própria estatística dos pixels daquela imagem específica, então o resultado se adapta a cada caso.

É bastante usada em imagens médicas, como radiografias, e em fotos tiradas com pouca luz, onde o contraste original costuma ser insuficiente.

Curiosidade

Câmeras de segurança e sistemas de reconhecimento facial aplicam equalização de histograma automaticamente antes de qualquer análise. A ideia é simples: um algoritmo de reconhecimento treinado com rostos bem iluminados falha muito mais em imagens escuras ou estouradas de luz. Equalizar o histograma antes da análise reduz esse problema sem precisar retreinar o modelo para cada condição de iluminação possível.
