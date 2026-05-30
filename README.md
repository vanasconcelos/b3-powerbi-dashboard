# Análise de Negociações B3 – Dashboard Power BI
> **Disciplina:** Power BI para Negócios  
> **Instituição:** ESPM  
> **Curso:** Publicidade e Propaganda  
> **Aluna:** Ana Vasconcelos  
> **Período dos Dados:** Janeiro de 2025 a Maio de 2026

---

## 📌 Visão Geral do Projeto

Este repositório contém o trabalho prático final desenvolvido para a disciplina de **Power BI para Negócios**. O objetivo principal do projeto é construir um dashboard interativo focado no desempenho de 5 grandes empresas listadas na B3 (PETR4, VALE3, ITUB4, BBDC4 e ABEV3), utilizando estritamente **recursos visuais nativos e relacionamentos de dados (sem o uso de fórmulas DAX)**.

O relatório final simula cenários comerciais e de movimentações diárias do mercado financeiro de janeiro de 2025 a maio de 2026, totalizando aproximadamente 1.680 registros processados.

---

## 🏗️ Modelagem de Dados e Relacionamentos

A arquitetura do modelo segue as diretrizes do esquema estrela (*Star Schema*), garantindo a integridade referencial por meio de conexões diretas entre as chaves das tabelas:

* `dim_empresa (EmpresaID)` $\leftrightarrow$ `fato_vendas_bovespa (EmpresaID)`
* `dim_tempo (DataID)` $\leftrightarrow$ `fato_vendas_bovespa (DataID)`
* `dim_empresa (EmpresaID)` $\leftrightarrow$ `mn_setor_empresa (EmpresaID)`

> 💡 **Nota de Modelagem:** Conforme recomendação do escopo do projeto, a categoria principal utilizada para as análises setoriais mapeadas foi a coluna `dim_empresa.Setor`, contornando de forma nativa a relação de muitos-para-muitos da tabela ponte secundária.

---

## 🖥️ Organização do Dashboard (5 Páginas)

O arquivo `.pbix` foi estruturado em **5 páginas temáticas** para facilitar a navegabilidade e a distribuição das visualizações:

### 📊 Página 1: Visões Gerais (Indicadores Macro)
* **Visual 1 (Cartão): Valor Total Negociado** *Análise:* O mercado movimentou um montante acumulado expressivo de R$ 1.994.890,72 Tri ao longo do período analisado. Este indicador macro demonstra a robustez de liquidez simulada das cinco grandes companhias selecionadas na carteira, servindo como base de controle financeiro para o dashboard.
* **Visual 2 (Cartão): Volume Total Simulado** *Análise:* Foram transacionados um total de 42,22 Mi de papéis corporativos entre janeiro de 2025 e maio de 2026. A magnitude dessa circulação de ativos reflete o alto giro de mercado, permitindo compreender a profundidade e constância das negociações diárias das empresas selecionadas.
* **Visual 3 (Cartão): Preço Médio de Fechamento Geral** *Análise:* O preço médio de fechamento geral do portfólio de ações atingiu o patamar de R$ 3.233,92 Tri. Este valor centralizado é influenciado pela distribuição das cotações simuladas no modelo, estabelecendo um panorama referencial para a precificação de tela.
* **Visual 4 (Cartão): Número Total de Dias Negociados** *Análise:* O dashboard computou exatos 336 dias de pregão efetivo e histórico operacional da bolsa de valores brasileira. Essa série temporal contínua oferece sustentação estatística sólida, cobrindo com precisão os dias úteis entre os anos de 2025 e os meses iniciais de 2026.

### 🏢 Página 2: Análise por Empresa
* **Visual 5 (Gráfico de Barras Verticais): Valor Total Negociado por EmpresaID** *Análise:* A empresa ABEV3 lidera ligeiramente o ranking financeiro em valores nominais totais, seguida de perto por BBDC4 e VALE3. O visual evidencia o equilíbrio de forças e a alta atratividade de liquidez simulada que todas as cinco companhias exercem sobre o fluxo de capital.
* **Visual 6 (Gráfico de Rosca): Participação Percentual por EmpresaID** *Análise:* O gráfico demonstra uma distribuição notavelmente homogênea entre as empresas na carteira. A ABEV3 detém a maior fatia com 22,57%, enquanto a PETR4 apresenta a menor com 17,03%, indicando que o portfólio não sofre com polarizações extremas de ativos.
* **Visual 7 (Tabela): Resumo de Desempenho Diário** *Análise:* Esta tabela detalha os valores exatos negociados cruzados com o volume e o dia da semana. Ela comprova como os fluxos volumétricos diários (como os 8,67 Mi transacionados nas sextas-feiras) se sustentam de forma regular para compor o acumulado de R$ 1,99 Tri do portfólio.
* **Visual 8 (Gráfico de Barras Horizontais Empilhadas): Volume Simulado por EmpresaID e Trimestre** *Análise:* O gráfico expõe o volume físico de ações segmentado pelos trimestres (1, 2, 3 e 4). Nota-se que o volume total de cada empresa se mantém muito próximo ao patamar dos 8 Mi de papéis, demonstrando consistência operacional e estabilidade na distribuição de cotas.
* **Visual 9 (Gráfico de Barras Horizontais): Média de Preço de Fechamento por EmpresaID** *Análise:* A precificação média individual revela um comportamento perfeitamente linear e padronizado no dataset simulado. Todas as cinco companhias registram médias equivalentes, o que facilita o processo de comparação direta do comportamento dos ativos.
* **Visual 10 (Gráfico de Linhas): Soma de Preço de Fechamento por MesNome e EmpresaID** *Análise:* O gráfico de linhas evidencia uma tendência geral de convergência e declínio gradual à medida que os meses avançam de abril até dezembro. A PETR4 inicia com picos superiores em relação às demais, mas o movimento macroeconômico conduz todas as curvas para um patamar unificado no fim do ano.

### 📅 Página 3: Análise Temporal
* **Visual 11 (Gráfico de Linhas): Valor Total Negociado por Mês e Ano** *Análise:* A linha temporal para o ano de 2026 indica uma manutenção de alta liquidez nos primeiros quatro meses, seguida por uma forte retração em direção ao mês 5. Esse comportamento visual é estritamente justificado pelo encerramento da coleta de dados do dataset em maio de 2026.
* **Visual 12 (Matriz): Cruzamento de Ano e Trimestre** *Análise:* A análise matricial expõe o cruzamento de valores entre o ano de 2026 e os trimestres 1 e 2. O primeiro trimestre consolidou R$ 3,46 Tri, ao passo que o segundo trimestre (parcial) registrou R$ 1,61 Tri, organizando perfeitamente os subtotais para auditoria financeira.
* **Visual 13 (Gráfico de Colunas): Volume Simulado por Trimestre e Ano** *Análise:* O primeiro trimestre de 2026 registrou o maior volume físico de ações movimentadas, ultrapassando a barreira dos 7 Mi de papéis. O segundo trimestre apresenta uma coluna menor devido à limitação temporal dos dados até maio.
* **Visual 14 (Gráfico de Barras Horizontais): Valor Total Negociado por Dia da Semana** *Análise:* As quartas e quintas-feiras revelaram-se os períodos com maior fluxo financeiro acumulado na bolsa, superando ligeiramente os demais dias úteis. As sextas-feiras aparecem com menor montante, sugerindo desalocação de posições institucionais antes do final de semana.
* **Visual 15 (Segmentação de Dados): Filtro por Ano** *Análise:* Este componente visual em formato de botões (*slicer*) permite alternar e isolar de forma instantânea os dados entre os anos de 2025 e 2026. A segmentação nativa sincroniza dinamicamente as tabelas e gráficos para análises personalizadas.

### 🌾 Página 4: Análise Setorial
* **Visual 16 (Gráfico de Barras Horizontais): Valor Total Negociado por Setor** *Análise:* O setor Financeiro desponta na liderança de captação financeira do painel, acumulando valores acima de R$ 5.000.000 Tri. Os segmentos de Bebidas, Mineração e Petróleo aparecem na sequência, demonstrando a distribuição setorial do portfólio.
* **Visual 17 (Gráfico de Colunas): Valor Total Negociado por EmpresaID e Setor** *Análise:* Este gráfico de colunas detalha individualmente a contribuição de cada ativo atrelado ao seu respectivo setor. ABEV3 (Bebidas) e BBDC4 (Financeiro) destacam-se no topo das colunas com os maiores aportes financeiros gerados.
* **Visual 18 (Gráfico de Colunas): Preço Mestre de Fechamento por Setor** *Análise:* A avaliação do preço de fechamento agrupado por setor reitera a liderança do setor Financeiro em termos de valoração acumulada de tela, superando os setores de Petróleo e Gás, Mineração e Bebidas consecutivamente.
* **Visual 19 (Gráfico de Pizza): Distribuição do Volume Simulado por Setor** *Análise:* O gráfico de pizza ilustra que o setor Financeiro é o campeão absoluto em giro físico de papéis, dominando com 39,8% de toda a circulação da carteira. Essa dominância se deve à presença de duas grandes instituições bancárias (Itaú e Bradesco) no mesmo agrupamento.
* **Visual 20 (Tabela): Resumo Consolidado dos Segmentos da B3** *Análise:* Esta tabela sintetiza a inteligência setorial cruzando Setor, EmpresaID, Valor Total e Média de Volume. Ela valida que o setor Financeiro equilibra perfeitamente o seu volume físico massivo com uma alta representatividade financeira.

### 🚀 Página 5: Análise Avançada (Extras)
* **Visual 21 (Gráfico de Dispersão): Volume Simulado por Valor Total Negociado** *Análise:* O gráfico espalha as negociações diárias e aponta uma forte concentração de pontos na zona inferior esquerda. O comportamento comprova estatisticamente que a maior parte dos pregões opera sob volumetrias regulares, registrando poucos *outliers* de alta liquidez isolada.
* **Visual 22 (Tabela): Acumulado de Preço de Fechamento por EmpresaID** *Análise:* Esta tabela expõe o somatório bruto dos preços operados na tela para cada ativo, liderado pela PETR4 com R$ 6,30 Tri e seguida por ITUB4 com R$ 5,05 Tri. O arranjo permite conferir a consistência dos dados numéricos integrados de ponta a ponta.
* **Visual 23 (Gráfico de Cascata): Contribuição de Valor Total por EmpresaID** *Análise:* O gráfico de cascata mapeia de forma incremental como cada empresa soma recursos para atingir o valor total geral de R$ 1,99 Tri. Os blocos verdes demonstram o ganho acumulativo constante de cada papel até a consolidação da barra azul final do portfólio.

---

## 📁 Estrutura de Entregas do Repositório

* `/entrega/Dashboard_B3_Analise.pbix`: Arquivo original do Power BI Desktop contendo o modelo e painéis interativos.
* `/entrega/Relatorio_Analise_B3.pdf`: Documentação impressa contendo Capa formalizada, capturas de tela das 23 visualizações e as respectivas análises textuais descritas acima.

---

## 👤 Desenvolvedora
* **Nome:** Ana Vasconcelos
* **Curso:** Publicidade e Propaganda
* **Instituição:** ESPM
* **Data:** Maio de 2026
