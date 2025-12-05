# 🌍 Comparação de Algoritmos: Problema do Caixeiro Viajante (TSP)

Este notebook implementa e compara duas abordagens distintas para resolver o **Problema do Caixeiro Viajante (PCV/TSP)** em um espaço Euclidiano 2D.

## 🚀 Abordagens Implementadas

### 1. Heurística Gulosa: Vizinho Mais Próximo (NN)
* **Estratégia:** Parte de uma cidade inicial e sempre escolhe a cidade não visitada mais próxima.
* **Complexidade:** $O(N^2)$
* **Característica:** Extremamente rápido, mas tende a cair em ótimos locais (soluções sub-ótimas).

### 2. Computação Evolutiva: Algoritmo Genético (AG)
Uma abordagem meta-heurística baseada na seleção natural.
* **Seleção:** Torneio ($k=5$).
* **Cruzamento (Crossover):** *Order Crossover 1* (OX1) — essencial para o TSP pois evita cidades duplicadas.
* **Mutação:** *Swap* (Troca de posições).
* **Parâmetros:**
    * População: 50
    * Gerações: 200
    * Taxa de Cruzamento: 80%
    * Taxa de Mutação: 5%

---

## 📊 Metodologia de Teste

O código executa uma bateria de testes automatizados variando o número de cidades ($N$) de **10 a 200**. Para cada tamanho, são realizadas múltiplas repetições para garantir consistência estatística.

### Indicadores Analisados:
1.  **Custo da Rota (Fitness):** A distância total percorrida (quanto menor, melhor).
2.  **Tempo de Execução:** Medido via `time.perf_counter()` para precisão.
3.  **Fator de Qualidade ($\rho$):** Razão entre o custo do NN e do AG ($\rho = \frac{Custo_{NN}}{Custo_{AG}}$).

## 📈 Visualizações Geradas

Ao executar o código, três análises gráficas serão plotadas:
1.  **Gráfico de Barras:** Comparação direta de custo por instância e repetição.
2.  **Tabela de Médias:** Resumo estatístico dos tempos e custos.
3.  **Análise Agregada:**
    * *Esquerda:* Curva de crescimento do tempo (Análise Big-O).
    * *Direita:* Comportamento da qualidade relativa das soluções conforme o problema cresce.

## 📦 Dependências
O código utiliza as seguintes bibliotecas (já instaladas no Colab):
* `numpy` (Cálculo vetorial)
* `pandas` (Tabulação de dados)
* `matplotlib` & `seaborn` (Visualização de dados)
