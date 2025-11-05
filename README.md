# Alura Store, Desafio de Data Science (ONE)

Análise das quatro lojas da Alura Store. Objetivo, identificar a loja com pior desempenho e recomendar qual vender, usando dados oficiais do desafio, Python com Pandas e Matplotlib, e um fluxo reprodutível no Google Colab.

---

## Propósito da análise

- Identificar a loja com pior desempenho no período disponível.
- Calcular e comparar métricas por loja: faturamento total, categorias mais compradas, avaliação média e mediana, produtos mais e menos vendidos, frete médio.
- Produzir gráficos claros e um resumo executivo que embasem a recomendação.

Métrica principal de decisão, faturamento total igual a **Preço + Frete**. Esta definição está documentada no notebook e foi usada no ranking e na recomendação.

---

## Estrutura do projeto

alura-store-latam-ds-challenge/
├─ README.md
├─ alura_store_latam_ds_challenge.ipynb
└─ images/
├─ 01_faturamento_por_loja.png
├─ 02_vendas_por_categoria.png
├─ 03_avaliacao_lojas.png
├─ 04_top10_produtos_volume.png
└─ 05_frete_medio_por_loja.png

---

## Exemplos de gráficos e insights

### 1) Faturamento total por loja
<img src="images/01_faturamento_por_loja.png" alt="Faturamento por loja" width="900">

Achados principais, participação no total:
- loja_1, 26,1%  | R$ 1.616.347  
- loja_2, 25,4%  | R$ 1.567.773  
- loja_3, 24,9%  | R$ 1.542.048  
- loja_4, 23,6%  | R$ 1.458.253  

A loja_4 contribui menos para a receita total.

---

### 2) Vendas por categoria, contagem de pedidos
<img src="images/02_vendas_por_categoria.png" alt="Vendas por categoria" width="900">

Mix dominante:
- móveis, 20%  
- eletrônicos, 19%  
- brinquedos, 14%  
- eletrodomésticos, 12%  

Mercado pulverizado, sem item individual que concentre grande volume.

---

### 3) Avaliação média e mediana por loja
<img src="images/03_avaliacao_lojas.png" alt="Avaliação das lojas" width="900">

As médias variam ligeiramente de 3,98 a 4,05 - 
loja 3: 4,05, loja 2: 4,04, loja 4: 4,00, loja 1: 3,98.

As medianas são 5,0 em todas as lojas, indicando concentração de avaliações máximas.

A diferença entre a melhor e a pior média é de 0,07 ponto (≈ 1,8% na escala 1–5), pequena e sem vantagem competitiva clara para a loja_4.

Insight: como a mediana é 5,0 em todas, a melhoria passa por reduzir eventos de notas 1–4, que puxam a média para baixo.  

---

### 4) Top 10 produtos por volume
<img src="images/04_top10_produtos_volume.png" alt="Top 10 produtos por volume" width="900">

Os líderes ficam perto de 2% do volume cada, reforçando a pulverização. Não há produto âncora que mude o resultado da loja_4.

---

### 5) Frete médio por loja com referência na mediana global
<img src="images/05_frete_medio_por_loja.png" alt="Frete médio por loja" width="900">

Frete médio: loja 1: R$ 35, loja 2: R$ 34, loja 3: R$ 33, loja 4: R$ 31.  
Mediana global, aproximadamente R$ 16. Frete um pouco menor na loja_4 não compensa a menor receita.

---

## Resumo executivo e recomendação

**Recomendação, vender a loja_4.**

Justificativa curta:
- Menor participação no faturamento total do período.
- Satisfação parecida, média 4,00, sem vantagem frente às demais.
- Frete um pouco menor não compensa a menor geração de receita.
- Mix disperso, sem alavancas claras para reversão no curto prazo.

---

## Instruções para executar o notebook

1. Abra **`alura_store_latam_ds_challenge.ipynb`** no **Google Colab**.  
2. Execute a célula de **setup** e a **seção 0.2** para montar o DataFrame mestre.  
3. Execute as seções **1 a 5**, na ordem. As figuras são exibidas e também **salvas automaticamente** na pasta `images/`.  
4. Verifique a pasta `images/` para usar os arquivos PNG no README e em apresentações.

Requisitos:
- Google Colab, ou Python 3 com **pandas** e **matplotlib**.
- O notebook usa **unicodedata** apenas para normalizar nomes de colunas. É biblioteca padrão do Python, não adiciona dependência externa.

---

## Notas sobre dados e metodologia

- Os CSV oficiais do desafio são lidos pelas URLs do repositório base no notebook.
- Tipos garantidos, datas convertidas, valores monetários como float, avaliação como inteiro, normalização de nomes de colunas.
- Métrica principal de faturamento, **Preço + Frete**, explicitada para evitar ambiguidade.
- Foco comparativo entre lojas, com gráficos simples, rótulos legíveis e unidades claras.

---

## Nota sobre a documentação

Este projeto mantém a documentação em dois locais complementares:

**README.md**
Visão geral do projeto, estrutura de pastas, exemplos de gráficos e instruções de execução.

**Dentro do notebook**
Seção **“Resumo executivo — Alura Store (Desafio ONE)”**, com os principais achados e a recomendação final, pensada para leitura contínua no Colab logo após executar as células.

### Por que manter os dois

* Facilita a vida de quem navega pelo GitHub e de quem abre direto no Colab.
* Garante reprodutibilidade: os gráficos exibidos no README são gerados pelo notebook e salvos em `images/`.
* Evita dependência de ferramentas externas para entender o resultado.

### Como evitar divergências

* O README não repete números linha a linha. Os valores “oficiais” ficam no notebook e nas figuras salvas em `images/`.
* Sempre que atualizar as análises, reexecute as células de gráficos para atualizar `images/` antes de commitar.

### Como encontrar no notebook

* Abra o arquivo `.ipynb` e busque por **“Resumo executivo — Alura Store (Desafio ONE)”**.

## Autor

Fábio Andrade, participante do programa Oracle Next Education.
