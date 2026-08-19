# Rede Ânima — Healthcare

## Sobre o projeto

Projeto de análise de dados desenvolvido no Power BI a partir de uma base de dados de uma rede de saúde.

O objetivo foi transformar os dados de atendimentos, pacientes, médicos, tratamentos e faturamento em um dashboard que permitisse analisar os principais indicadores e acompanhar diferentes aspectos dos atendimentos realizados.

A base utilizada possui aproximadamente 200 registros.

## Objetivos

O projeto foi desenvolvido com foco na prática de relacionamentos entre tabelas, criação de medidas e construção de visuais no Power BI, buscando analisar questões como:

* Quantos atendimentos foram realizados?
* Quais tipos de tratamento possuem maior volume?
* Quais médicos possuem maior quantidade de atendimentos?
* Quanto foi faturado ao longo do período?
* Qual é o faturamento por tipo de tratamento?
* Qual é o ticket médio por tratamento?

## Ferramentas utilizadas

* Power BI
* Power Query
* DAX

## Dashboard

O dashboard apresenta os seguintes indicadores:

* Faturamento Total
* Total de Atendimentos
* Total de Tratamentos
* Ticket Médio

Principais análises:

* Evolução dos Atendimentos
* Tratamentos por Tipo
* Atendimentos por Médico
* Faturamento por Tipo de Tratamento

Também foi utilizada uma segmentação para permitir a filtragem dos dados por unidade.

<img width="890" height="496" alt="dashboard" src="https://github.com/user-attachments/assets/85a7fd23-6ab3-44ea-9911-634d5d22cd7d" />

## Tooltips

Foram utilizados tooltips nos gráficos para apresentar informações adicionais sem sobrecarregar o dashboard principal.

<img width="902" height="523" alt="tooltip-atendimentos-tempo" src="https://github.com/user-attachments/assets/0470b3f1-a627-49cc-9254-240cd7648d63" />

<img width="898" height="498" alt="tooltip-tratamento-tipo" src="https://github.com/user-attachments/assets/01a8d9db-7a5f-4cc5-8b4d-c1146cc1953d" />

<img width="894" height="496" alt="tooltip-atendimento-medico" src="https://github.com/user-attachments/assets/f0d8472e-5c52-4976-9e33-f6b21f96ba2c" />

<img width="890" height="493" alt="tooltip-faturamento-tipo" src="https://github.com/user-attachments/assets/1c9f1c1e-9781-4d9f-85aa-ee28365ae5f9" />

## Tratamento dos dados

O tratamento das bases foi realizado utilizando Power Query.

Entre as principais etapas realizadas estão:

* Importação dos arquivos CSV;
* Renomeação das colunas para facilitar a leitura dos dados;
* Ajuste dos tipos de dados;
* Tradução das especializações e unidades dos médicos;
* Tradução dos gêneros e convênios dos pacientes;
* Tradução dos tipos e descrições dos tratamentos;
* Tradução dos motivos dos atendimentos e seus status;
* Tradução dos métodos e status de pagamento;
* Padronização dos endereços de e-mail;
* Organização dos dados para utilização no Power BI.

## Modelo de dados

O projeto foi organizado em seis tabelas:

* `dMedico`
* `dPaciente`
* `dCalendario`
* `fAtendimento`
* `fTratamento`
* `fFaturamento`

Principais relacionamentos:

* `dMedico` 1 → N `fAtendimento`
* `dPaciente` 1 → N `fAtendimento`
* `dCalendario` 1 → N `fAtendimento`
* `fAtendimento` 1 → 1 `fTratamento`
* `fTratamento` 1 → 1 `fFaturamento`

A estrutura permite relacionar os atendimentos aos respectivos tratamentos e informações de faturamento, além de permitir análises por médico, paciente e período.

<img width="812" height="468" alt="modelo-dados" src="https://github.com/user-attachments/assets/eece5284-4f12-4d11-931a-c0c862f177ee" />

## Medidas e cálculos

Foram criadas medidas em DAX para os principais indicadores do dashboard:

* `Faturamento Total`
* `Qtd. Atendimentos`
* `Qtd. Tratamentos`
* `Ticket Médio por Tratamento`

Também foi criada a coluna calculada `Nome Completo`, utilizada para unir o primeiro e o último nome dos médicos e facilitar a análise de atendimentos por médico.

## Arquivos

* `Rede Ânima - Healthcare.pbix` — arquivo do projeto desenvolvido no Power BI.
* `Base de Dados` — pasta contendo os arquivos CSV utilizados no projeto.

## Fonte dos dados

A base utilizada neste projeto foi disponibilizada pelo Kaggle.

Kaggle: https://www.kaggle.com/datasets/kanakbaghel/hospital-management-dataset

## Créditos

Os ícones utilizados no dashboard foram obtidos através do Flaticon, seguindo as condições de uso e atribuição aplicáveis aos recursos utilizados.
