# 🔄 Simulador de Gargalo - Teoria das Filas

Este projeto é um simulador interativo baseado em HTML, CSS e JavaScript que modela um fluxo de trabalho de desenvolvimento de software, aplicando conceitos da Teoria das Filas para visualizar e analisar gargalos. Ele permite configurar diversos parâmetros para entender como eles afetam a vazão, o tempo de ciclo, o trabalho em progresso (WIP) e a eficiência do fluxo.

## 🚀 Funcionalidades

- **Estágios de Fluxo:** Simula os estágios de "Fila Dev", "Dev", "Fila QA", "QA" e "Concluído".
- **Tipos de Tarefas:** Suporte para três tipos de tarefas (A, B, C), permitindo especialização de desenvolvedores.
- **Tempos de Ciclo Configuráveis:** Defina o tempo médio de desenvolvimento (`Dev Time`) e de QA (`QA Time`).
- **Taxa de Retrabalho:** Simule a probabilidade de uma tarefa retornar para desenvolvimento após a QA.
- **Estratégias de QA:**
  - **QA Separado (Marcado):** QAs focam em um tipo de produto por vez, otimizando o processamento de lotes do mesmo tipo.
  - **QA Não Separado (Desmarcado):** QAs operam em modo FIFO (First-In, First-Out), pegando a tarefa mais antiga da fila, independentemente do tipo.
- **Disponibilidade Variável:** Configure a porcentagem de tempo que Devs e QAs estão disponíveis para tarefas de produção, simulando alocações em outras atividades (pré-produção, reuniões, etc.).
- **Períodos de Homologação da QA:** Defina ciclos de homologação para a equipe de QA, durante os quais eles ficam indisponíveis para tarefas de produção.
- **Horizonte de Simulação:** Controle a duração total da simulação em dias.
- **Controles de Simulação:** Botões para Iniciar, Pausar e Resetar, além de um slider para ajustar a velocidade da simulação.
- **Visualização em Tempo Real:** Acompanhe o movimento das tarefas e o status dos trabalhadores (ocioso, trabalhando, indisponível).
- **Métricas Detalhadas:** Painel de métricas que exibe:
  - Total de Tarefas
  - Tarefas Concluídas
  - Throughput (Vazão)
  - WIP (Work In Progress)
  - Cycle Time Médio
  - Eficiência de Fluxo
  - Percentual de Ociosidade de Devs
  - Percentual de Ociosidade de QAs
  - Contagem de Retrabalhos
- **Log de Simulação para Planilhas:** Após cada simulação, uma tabela com os resultados chave é gerada, pronta para ser copiada e colada diretamente em ferramentas como o Google Sheets para análise posterior.

## 🛠️ Como Usar

1.  **Clone o Repositório:**
    ```bash
    git clone [https://github.com/seu-usuario/nome-do-repositorio.git](https://github.com/seu-usuario/nome-do-repositorio.git)
    cd nome-do-repositorio
    ```
2.  **Abra no Navegador:**
    Abra o arquivo `index.html` diretamente no seu navegador de internet. Se estiver usando o GitHub Pages, basta acessar a URL do seu site.
3.  **Configurar Parâmetros:**
    - Ajuste o número de `Tarefas A, B, C` para definir o backlog inicial.
    - Defina o `Dev Time` e `QA Time` (tempo médio para concluir uma tarefa em cada estágio).
    - A `Retrabalho %` (densidade de defeitos) define a chance de uma tarefa voltar para Dev após a QA.
    - Marque/desmarque `QA separado` para alternar entre as estratégias de foco por produto e FIFO para a QA.
    - Ajuste a `Dev Disponibilidade %` e `QA Disponibilidade %` para simular o tempo dedicado à produção.
    - Configure `QA Homologação (dias)` e `QA Homologação (a cada dias)` para simular períodos de indisponibilidade da QA.
    - Defina o `Horizonte (dias)` para a duração da simulação.
4.  **Controlar a Simulação:**
    - Clique em `▶️ Iniciar` para começar a simulação.
    - Use `⏸️ Pausar` para interromper a simulação a qualquer momento.
    - Clique em `🔄 Resetar` para limpar o estado da simulação e voltar aos parâmetros iniciais.
    - Use o slider `Velocidade` para acelerar ou desacelerar a simulação.
5.  **Analisar o Log:**
    Após pausar ou concluir uma simulação, uma tabela será gerada na seção "📊 Log da Última Simulação". Clique em `📋 Copiar Log para Planilha` e cole os dados na sua ferramenta de planilha (ex: Google Sheets) para análise.

## 💡 Insights das Simulações

Com base em diversas execuções, algumas tendências e insights importantes podem ser observados:

- **Impacto do Retrabalho:** A taxa de retrabalho é o fator mais crítico. Uma alta densidade de defeitos (ex: 80%) pode paralisar completamente o fluxo, resultando em baixíssima vazão, alto WIP e alta ociosidade dos recursos, mesmo com alta disponibilidade.
- **Estratégia de Fila da QA:**
  - A estratégia **FIFO (First-In, First-Out)** para a QA tende a otimizar a vazão e reduzir o Cycle Time médio, além de manter a ociosidade da QA menor, pois garante um fluxo contínuo de trabalho.
  - O modo **"Foco por Produto"** para a QA pode levar a uma maior ociosidade se não houver tarefas suficientes do tipo focado, mesmo que outras tarefas estejam na fila.
- **Disponibilidade vs. Qualidade:** Aumentar a disponibilidade das equipes é benéfico, mas seu impacto é limitado se a qualidade do trabalho (baixa taxa de retrabalho) não for priorizada. Um sistema com muitos defeitos fará com que os recursos fiquem ociosos ou presos em retrabalho, independentemente de sua disponibilidade nominal.
- **WIP como Sinal de Alerta:** Um WIP consistentemente alto é um forte indicador de gargalos e ineficiências no fluxo.

## 💻 Tecnologias Utilizadas

- HTML5
- CSS3
- JavaScript (ES6+)

## 🤝 Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues para sugestões de novas funcionalidades, relatar bugs ou enviar Pull Requests com melhorias.

## 📄 Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
