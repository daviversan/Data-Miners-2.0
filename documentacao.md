# Modelo de Template para Hipóteses

### Times com mais gols no campeonato tendem a marcar o primeiro gol
**[Essa hipótese busca confirmar que os times que mais marcam no campeonato tendem a marcar o primeiro gol de suas respectivas partidas]**

**Nota:**  
- Para acessar o modelo preditivo deste notebook, clique no link [QuemMarca](https://github.com/daviversan/Data-Miners-2.0/blob/main/Notebooks/modelos/quemMarca.ipynb).  
- Para acessar a hipótese testada no Random Forest Classifier, clique no link [Notebook Hipótese Random Forest Classifier](https://github.com/daviversan/Data-Miners-2.0/blob/08273bf3fbb349df8b9dde8e2228d050f700b3ac/Notebooks/modelos/RandomForest.ipynb).
- Para acessar a hipótese testada no Gradient Boost, clique no link [Notebook Hipótese Gradient Boost](https://github.com/daviversan/Data-Miners-2.0/blob/08273bf3fbb349df8b9dde8e2228d050f700b3ac/Notebooks/modelos/GradientBoost.ipynb).

A hipótese inicial proposta, "Times com mais gols no campeonato tendem a marcar o primeiro gol", foi testada para entender a correlação entre o número total de gols de uma equipe e sua probabilidade de abrir o placar em um jogo. Esse teste envolveu a comparação de alguns modelos preditivos, entre eles, o **Random Forest Classifier** e o **Gradient Boost**.

O modelo **Random Forest Classifier** foi escolhido como a opção final por sua robustez e capacidade de manipular dados de alta variabilidade, produzindo previsões precisas. Este modelo combina várias árvores de decisão que, ao serem treinadas com amostras aleatórias, permitem capturar padrões de uma forma mais precisa. A decisão de escolher o Random Forest foi suportada pela análise de métricas específicas de desempenho, como a acurácia média ou o desvio padrão dos dados de partidas jogadas em casa e fora.

As métricas de desempenho indicaram que o modelo conseguiu generalizar bem em ambos os contextos de partidas (em casa e fora), com uma acurácia média de 0,93 e uma acurácia nos jogos do Flamengo (time que mais marcou gols no campeonato) de 0,86. Esses valores mostram que o modelo é eficaz em prever novos cenários de partidas de futebol. Dessa forma, com um modelo final escolhido e corretamente treinado, a entrega esperada pelo stakeholder foi atingida.

### Desempenho Geral do Modelo

O modelo **Random Forest Classifier** foi escolhido por combinar múltiplas árvores de decisão para melhorar a precisão das previsões, aproveitando a aleatoriedade na seleção de amostras e características dos dados. Abaixo estão as métricas de desempenho:

1. **Acurácia Específica no Flamengo (86%)**  
   - O modelo foi capaz de prever corretamente, em grande parte dos jogos do Flamengo, se ele marcou o primeiro gol ou não. Isso indica que as variáveis selecionadas (como desempenho pré-jogo, posse de bola, etc.) capturam bem a relação entre os dados e o comportamento do Flamengo.

2. **Desempenho Geral Elevado (93% na validação cruzada)**  
   - O modelo é altamente preciso ao prever outros times também, o que reforça que ele está generalizando bem os padrões nos dados.  
   - A alta acurácia geral reduz a possibilidade de overfitting, indicando que o desempenho no Flamengo não é apenas sorte.

3. **Dados Diretos do Flamengo (Time que mais marcou no campeonato)**  
   - Como o modelo alcançou 86% de acurácia nos jogos do Flamengo, ele confirma que as características do time (como alta média de gols) são indicadores confiáveis para prever quem marcará o primeiro gol.

Através das análises acima, foi possível comprovar a hipótese proposta. Com o resultado de 86% de acurácia no Flamengo, é possível observar que o modelo tende a prever que o primeiro gol da partida será marcado pelo Flamengo, provando que o time que mais marcou gols no campeonato tende a marcar gols primeiros na partida.

### Importância das Variáveis

A análise das variáveis mais importantes revelou que características-chave impactam diretamente as previsões. Entre as mais influentes estão:  
- **away_ppg (Pontos por jogo da equipe visitante):** Reflete o desempenho histórico das equipes visitantes, destacando sua consistência em partidas anteriores.  
- **home_team_goal_count (Número de gols da equipe da casa):** A capacidade ofensiva da equipe anfitriã, medida pelo número de gols marcados, é um forte indicador de seu potencial para abrir o placar.  
- **home_ppg (Pontos por jogo da equipe da casa):** Representa o desempenho geral da equipe jogando em casa, sendo um fator relevante para avaliar sua competitividade e impacto no jogo.

Essas variáveis ajudam diferentes perfis de usuários a entenderem como os padrões nos dados influenciam as previsões. Por exemplo, analistas técnicos podem usar gráficos de importância das variáveis para priorizar estratégias baseadas em desempenho histórico, enquanto treinadores podem identificar pontos fortes e fracos para ajustar táticas. Visualizações, como gráficos de barras para importância relativa (Figura 1), permitem interpretar facilmente o impacto de cada variável no modelo preditivo.

<div align="center">
<sub>Figura 1 - Gráfico </sub> 
<img src="../assets/grafico.png"> 
 
<sup>Fonte: Material produzido pelo Data Miners (2024)</sup>
</div>  

A análise confirma que equipes com mais gols no campeonato têm maior probabilidade de marcar primeiro. O modelo Random Forest destacou variáveis como away_ppg, home_team_goal_count e home_ppg como as mais relevantes, evidenciando a relação entre capacidade ofensiva e a chance de abrir o placar. Esse padrão foi validado nos jogos do Flamengo, que, com a maior média de gols, apresentou uma acurácia de 86% no modelo. Isso reforça a aplicabilidade do modelo para prever padrões semelhantes no futuro, fornecendo uma base sólida para decisões estratégicas no futebol.

### Plano de Contingência

Para garantir que o modelo continue atendendo aos requisitos de desempenho e precisão, o plano de contingência inclui várias estratégias de monitoramento e ajuste:
- **Monitoramento Contínuo dos Dados:** Será implementado um processo de monitoramento contínuo para identificar e corrigir potenciais mudanças nas características dos novos dados, especialmente no que diz respeito a padrões de gol. Isso permite identificar se o modelo começa a perder precisão caso haja modificações nas estratégias dos times ou alterações na escalação, por exemplo.
- **Monitoramento de Falhas:**   Caso uma série de predições erradas seja detectada, uma análise humana deverá ser realizada com o objetivo de diagnosticar o problema, para que, dessa maneira, a origem das predições falhas possa ser determinada. Após o diagnóstico, as falhas encontradas no modelo devem ser corrigidas e revisadas.   
- **Re-treinamento do Modelo:** Antes da reaplicação do modelo agora corrigido, este deve ser testado e validado como garantia de que as falhas previamente encontradas foram corrigidas.


### Verificação de Hipóteses

A hipótese "Times com mais gols no campeonato tendem a marcar o primeiro gol" foi confirmada com os seguintes resultados:  
- **Desempenho Superior em Recall:**  
 O Random Forest Classifier alcançou 86% de acurácia nos jogos do Flamengo, o time com mais gols no campeonato. Essa precisão mostra que o modelo consegue identificar bem o time que marca o primeiro gol, validando a hipótese inicial.  
- **Generalização:**  
  Com uma acurácia geral de 93% na validação cruzada, o modelo mostrou ser eficiente em prever o primeiro gol de outros times também. Esse desempenho consistente prova que o modelo funciona bem em diferentes cenários e não está ajustado apenas para os dados do Flamengo, confirmando a tendência analisada.

### Explicabilidade do Modelo

Para explicar as previsões, foi utilizada a técnica SHAP (SHapley Additive exPlanations). Isso possibilita a análise de como cada variável afeta as previsões, atribuindo a cada feature um valor que representa sua contribuição positiva ou negativa no resultado do modelo. A seguir, são destacadas as principais variáveis que apresentaram impacto relevante tanto para as previsões de goals_home quanto para as de goals_away (Modelo de previsão do Placar).

- **total_goal_count:**  Todas as observações apresentaram valores de SHAP positivos, sugerindo que, ao aumentar o número total de gols marcados na temporada, a probabilidade do modelo prever mais gols (seja em casa ou fora) se eleva.
 
- **goal_difference:** Geralmente indica impacto positivo quando o saldo de gols é maior. Contudo, houve algumas observações próximas ao zero, mostrando que seu impacto pode variar conforme o contexto do jogo ou do time.
  
- **goals_scored_per_match:** Mostra um comportamento mais equilibrado: algumas observações contribuem positivamente, enquanto outras se aproximam de zero ou têm contribuição ligeiramente negativa. Isso sugere que o número de gols por partida precisa ser analisado em conjunto com outras variáveis.

- **minutes_per_goal_conceded:**  Para as previsões de goals_home, teve um impacto predominantemente negativo. Já no contexto de goals_away, o efeito foi majoritariamente positivo, indicando que sofrer poucos gols por tempo de jogo pode influenciar de formas distintas a performance dentro ou fora de casa.

- **wins (para goals_home) e losses (para goals_away):** Ambas as variáveis têm efeitos mistos. Em alguns cenários, mais vitórias (ou derrotas) podem influenciar positivamente ou negativamente, dependendo do conjunto de demais características do time analisado.


**Impacto de exemplo**

Imagine uma partida em que a equipe analisada estivesse com um bom saldo de gols (goal_difference alto) e alto número de gols totais marcados na temporada (total_goal_count). O SHAP mostraria contribuições positivas dessas variáveis, indicando aos stakeholders que a força ofensiva e o saldo de gols dessa equipe são fatores-chave para projetar um maior número de gols na próxima partida. Por outro lado, se a equipe estivesse sofrendo gols em curtos intervalos de tempo (baixo minutes_per_goal_conceded), isso poderia diminuir a previsão de gols a favor, caso ela jogue fora de casa.

Essa análise de impacto fornece aos gestores esportivos e à comissão técnica uma visão clara sobre como e por que o modelo chega às suas estimativas, permitindo a tomada de decisões mais embasadas (por exemplo, reformular estratégias de ataque ou reforçar setores defensivos).

**Visualização Gerada**
A figura gerada (Figura 2) expõe, no eixo X, a contribuição de cada variável (valor SHAP) e, no eixo Y, as variáveis mais importantes ranqueadas de acordo com sua influência no modelo. Cada ponto representa um jogo ou registro no dataset, e a cor indica o valor que aquela feature assumiu. Essa forma de visualização é fundamental para que stakeholders, analistas e demais interessados compreendam rapidamente quais variáveis são mais determinantes para a previsão de gols.

<div align="center">
<sub>Figura 2 - Explicabilidade </sub> 
<img src="../assets/explicabilidade.png"> 
 
<sup>Fonte: Material produzido pelo Data Miners (2024)</sup>
</div>  

**Visualização dos dados**

Os dados para o modelo de quem marca o primeiro gol são apresentados diretamente no código do projeto

<div align="center">
<sub>Figura 3 - Visualização </sub> 
<img src="../assets/flamengoo.PNG"> 
 
<sup>Fonte: Material produzido pelo Data Miners (2024)</sup>
</div>  

A partir de um dicionário também fornecido no código da aplicação, o usuário consegue determinar que número pertence a qual time. No exemplo acima, o número 10 representa o Flamengo, que segundo o modelo, seria o primeiro a marcar em uma partida contra o Atlético Mineiro.


### Conclusão

Com as informações acima, é possível determinar que a hipótese “O time que mais marca gols no campeonato tende a marcar o primeiro gol” está correta, uma vez que o modelo tem uma tendência de prever que o Flamengo será o primeiro marcador, e, ao verificar o time com mais gols no campeonato, o Flamengo é o detentor desse título, tornando aceita a hipótese supracitada.
