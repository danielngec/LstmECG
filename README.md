# Relatório sobre Análise de Dados Temporais com LSTM para Batimentos Cardíacos

## Introdução
A utilização de redes neurais recorrentes, especificamente Long Short-Term Memory (LSTM), tem sido amplamente explorada para análise de séries temporais. A capacidade do LSTM de armazenar informações de longo prazo torna essa abordagem promissora para modelar sinais biológicos, como os batimentos cardíacos. No entanto, os resultados obtidos no presente estudo não foram satisfatórios, indicando dificuldades na aprendizagem do modelo.

Os dados utilizados para o treinamento da rede foram extraídos de um conjunto de dados público contendo registros de batimentos cardíacos coletados a partir de sensores biomédicos. Esse dataset inclui séries temporais de frequência cardíaca em diferentes condições fisiológicas e patológicas. O dataset pode ser acessado em:

[https://www.kaggle.com/code/polomarco/ecg-classification-cnn-lstm-attention-mechanism](https://www.kaggle.com/code/polomarco/ecg-classification-cnn-lstm-attention-mechanism)

## Análise dos Resultados
Os resultados indicam que a rede não aprendeu bem os padrões presentes nos dados, apresentando erros elevados e baixa capacidade de generalização. Algumas das principais possíveis causas para esse desempenho insatisfatório incluem:

- **Tamanho da Janela Temporal**: A escolha de uma janela de 9 pontos para prever um ponto pode não ter sido adequada. Essa escolha pode ter limitado a capacidade do modelo de capturar padrões mais complexos ao longo do tempo.
- **Desbalanceamento Relativo dos Dados**: Observou-se que existiam poucos pontos com valores significativamente grandes, ou seja, com vários dígitos após a vírgula. Esse desbalanceamento pode ter dificultado o aprendizado da rede, tornando-a tendenciosa para padrões mais comuns e incapaz de detectar anomalias corretamente.

## Sugestões para Melhorias
Para melhorar o desempenho do modelo, algumas modificações podem ser consideradas:

1. **Alterar a Métrica de Erro**: Uma sugestão seria utilizar o erro relativo normalizado. Embora essa abordagem não seja usual, poderia ajudar a modelar melhor a variabilidade presente nos dados.
2. **Utilização de Duas Métricas para Atualizar os Pesos**: Outra possibilidade seria empregar duas métricas simultaneamente durante o treinamento para otimizar a função de perda de forma mais eficiente.
3. **Revisão da Janela Temporal**: Testar diferentes tamanhos de janela pode ajudar a melhorar a capacidade do modelo de capturar padrões temporais de maneira mais eficaz.
4. **Rebalanceamento dos Dados**: Estratégias para lidar com o desbalanceamento dos valores numéricos podem incluir técnicas de normalização diferenciada ou aumento artificial da quantidade de pontos com valores significativos.

## Conclusão
Os resultados obtidos indicam que o modelo LSTM, na configuração utilizada, não foi capaz de aprender os padrões temporais de maneira satisfatória. Questões como a escolha da janela temporal e o desbalanceamento dos dados podem ter contribuído para esse resultado. Para melhorar a performance, sugere-se a experimentação de novas métricas de erro, a utilização de diferentes janelas temporais e o tratamento adequado do desbalanceamento dos dados. Essas mudanças podem aumentar a capacidade do modelo de detectar anomalias nos batimentos cardíacos de forma mais eficaz.
