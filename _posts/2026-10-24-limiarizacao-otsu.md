---
layout: post
title: "Método de Otsu: escolhendo o limiar ideal automaticamente"
date: 2026-10-24
---

Limiarização é a forma mais simples de segmentar uma imagem: todo pixel acima de um valor (o limiar) vira branco, e todo pixel abaixo vira preto. O resultado é uma imagem binária que separa o objeto de interesse do fundo.

O problema é escolher o limiar. Um valor fixo, como 128, funciona em uma imagem e falha em outra com iluminação diferente.

O método de Otsu resolve isso olhando o histograma da imagem. Ele testa todos os limiares possíveis, divide os pixels em dois grupos (abaixo e acima do limiar) e escolhe o valor que deixa os dois grupos o mais separados possível entre si, ou seja, o que maximiza a variância entre as classes. Funciona melhor quando o histograma tem dois picos bem definidos, um para o fundo e outro para o objeto.

Entre as aplicações estão a leitura de documentos digitalizados, a separação de células em imagens de microscópio e a remoção de fundo em imagens com bom contraste.

**Curiosidade**

O método leva o nome de Nobuyuki Otsu, que o publicou em 1979, e continua sendo uma das técnicas de limiarização mais usadas até hoje. Bibliotecas como o OpenCV trazem o método pronto, bastando ativar uma flag na função de limiarização.

<img width="1430" height="630" alt="image" src="https://github.com/user-attachments/assets/6e417a0b-2195-43f4-82f9-3dfc2dd7d33e" />
