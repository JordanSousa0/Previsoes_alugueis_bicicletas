# 🚲 Análise e Previsão de Aluguéis de Bicicletas

Uma análise completa dos padrões de uso de bicicletas compartilhadas com base em dados temporais, climáticos e sazonais, usando ferramentas estatísticas, visualizações e modelagem preditiva.

---

## 🎯 Objetivo

Este projeto tem como propósito analisar dados de aluguéis de bicicletas ao longo do tempo, identificando padrões de comportamento em função do clima, feriados, finais de semana e horários. Também aplicamos modelos de previsão para estimar a demanda futura.

---

## 🧩 Sobre os dados

O conjunto de dados contém:

- Data e hora dos registros (`data_hora`)
- Contagem de bicicletas alugadas
- Condições climáticas: temperatura, sensação térmica, umidade, velocidade do vento, clima
- Indicadores temporais: feriado, estação do ano, fim de semana

**Fonte dos dados:** Repositório da Alura para projetos de Ciência de Dados.

---

## 🔍 O que foi analisado?

### 📥 1. Importação de Dados

- Leitura com `pandas` a partir de um CSV hospedado 'https://raw.githubusercontent.com/alura-cursos/data_science_projeto/main/Dados/bicicletas.csv'.
- Visualização inicial das colunas e tipos de dados.

### 🧹 2. Tratamento de Dados

- Interpolação linear para preencher valores nulos de temperatura e sensação térmica.
- Remoção de duplicatas com `drop_duplicates()`.
- Salvamento dos dados tratados na variável `dados_limpo`.

### 📈 3. Análise Exploratória

- **Distribuições**: Histogramas para temperatura, sensação térmica, umidade e vento.
- **Correlação**: Matriz de correlação e gráficos de dispersão entre variáveis climáticas e a contagem de bicicletas.
- **Padrões Temporais**: Extração de mês e hora para análise sazonal e diária. Gráficos mostram picos de uso pela manhã e ao fim da tarde.

### 🔮 4. Previsões com Facebook Prophet

- Reestruturação dos dados no formato esperado pelo Prophet (`ds`, `y`).
- Previsão da contagem para os próximos 365 dias.
- Treinamento com e sem outliers para comparar desempenho.
- Visualização interativa com `plot_plotly()`.

---

## 💡 Principais insights

### Influência de Feriados e Finais de Semana

- A contagem média de bicicletas cai consideravelmente em feriados e finais de semana.
- Indica que o sistema é utilizado principalmente por estudantes e trabalhadores locais durante a semana.
- O uso tem perfil mais funcional (locomoção) do que recreativo (lazer).

### Impacto do Clima

- Temperatura e sensação térmica têm relação positiva com o uso.
- Umidade elevada e vento forte tendem a reduzir a demanda.
- Clima ameno favorece o uso, enquanto frio e chuva desencorajam.

### Padrões Temporais

- Horários de pico pela manhã e ao fim da tarde.
- Maior volume nos meses de clima mais quente.
- Forte influência de sazonalidade e horário no comportamento dos usuários.

### Modelagem Preditiva

- O Prophet modela bem a tendência e a sazonalidade.
- Após remoção de outliers, a previsão melhora.
- Indica estabilidade ou leve crescimento na demanda futura.

---

## 🔧 Tecnologias utilizadas

- Python 🐍
- Pandas e NumPy
- Seaborn e Matplotlib
- Plotly
- Facebook Prophet

---

## 🧠 Próximos passos (sugestões)

- Incluir variáveis externas como feriados municipais ou eventos.
- Criar dashboards interativos com Streamlit ou Power BI.
- Avaliar modelos alternativos de previsão (ARIMA, LSTM).
- Identificar clusters de usuários por horário e clima.

---

## 🚀 Como executar
1. Clone o repositório
2. Instale as bibliotecas necessárias com pip install -r requirements.txt
3. Rode o notebook no Jupyter ou Google Colab
   
---

## 🤝 Contribuições
Sinta-se à vontade para abrir issues ou enviar pull requests com melhorias, visualizações alternativas ou extensões analíticas.
