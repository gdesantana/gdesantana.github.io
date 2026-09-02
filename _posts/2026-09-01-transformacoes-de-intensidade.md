---
layout: post
title: "Transformações de intensidade: mexendo em uma imagem pixel por pixel"
date: 2026-09-01
---

Transformações de intensidade processam uma imagem pixel a pixel, sem olhar a vizinhança: s = T(r), onde r é a intensidade de entrada e s a de saída.

O negativo inverte os níveis de cinza (s = (L-1) - r), útil para realçar detalhes claros em regiões escuras, como em mamografias.

A transformação logarítmica (s = c log(1+r)) expande intensidades baixas e comprime as altas. É usada em espectros de Fourier, onde os valores variam tanto que um ajuste linear deixaria os pixels claros dominando a imagem.

A transformação de potência (s = cr^gama) clareia ou escurece a imagem dependendo do gama. É a base da correção gama, usada para ajustar como uma imagem aparece na tela.


<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a331688f-da42-4163-bd04-d328250fbc87" />



Transformações lineares por partes incluem alargamento de contraste (expande o intervalo de intensidades de uma imagem "lavada"), fatiamento de intensidade (realça uma faixa específica, como vasos sanguíneos em um angiograma) e fatiamento por planos de bits (separa a imagem em camadas binárias, uma por bit).

**Curiosidade**

A correção gama existe por causa dos monitores CRT antigos: a relação entre voltagem e brilho do tubo não era linear, seguia uma curva de potência com expoente perto de 2.5. Só que essa mesma curva, por coincidência, também se aproxima de como o olho humano percebe luminância. Os CRTs sumiram, mas a correção gama continua até hoje porque aproveita melhor os bits disponíveis exatamente nas faixas de brilho que o olho consegue distinguir.
<img width="316" height="231" alt="image" src="https://github.com/user-attachments/assets/84fda189-9bc2-45d8-b41e-4e2b1579dec5" />
