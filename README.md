# dio-azure-cognitive-search

# Azure AI Search - Organização e Pesquisa de Documentos com IA

Este repositório documenta o laboratório de **ingestão de dados, indexação inteligente e exploração de documentos** com Azure AI Search, proposto no desafio da DIO. O laboratório tem como foco aplicar técnicas de mineração de conhecimento em documentos usando recursos de IA para transformar dados não estruturados em informação pesquisável e útil.

## Objetivo

O objetivo desta prática foi compreender como funciona o processo de enriquecimento de documentos com inteligência artificial, desde a ingestão dos arquivos até a consulta dos dados indexados. A atividade foi baseada no laboratório oficial **Explore an Azure AI Search index (UI)** do Microsoft Learning e adaptada como documentação técnica para entrega no GitHub.

## Tecnologias utilizadas

- Azure AI Search, responsável pela criação do índice e execução das pesquisas inteligentes
- Azure AI Services, usado para enriquecer os documentos com recursos como OCR, extração de frases-chave e análise de sentimento
- Azure Storage Account, utilizado para armazenar os arquivos de entrada que serão processados pelo indexador
- GitHub, usado para versionamento e publicação da documentação técnica do laboratório

## Estrutura do laboratório

Durante a atividade, o fluxo prático foi dividido em três grandes etapas:

1. **Ingestão de conteúdo**: envio dos documentos para o Azure Storage, tornando-os disponíveis para processamento.
2. **Criação do índice inteligente**: configuração do Azure AI Search com enriquecimento por IA, permitindo extração automática de informações relevantes.
3. **Exploração dos dados**: uso do Search Explorer para executar consultas e analisar os resultados retornados pelo índice.

## Recursos criados no Azure

Para a execução do laboratório, foram configurados os seguintes recursos:

| Recurso | Finalidade |
|---|---|
| Azure AI Search | Criar e gerenciar o índice de pesquisa dos documentos |
| Azure AI Services | Aplicar enriquecimento cognitivo aos dados, como OCR, frases-chave e sentimento |
| Storage Account | Armazenar os arquivos utilizados como fonte de dados |

## Passo a passo realizado

### 1. Criação dos recursos

Inicialmente, foi necessário acessar o portal do Azure e criar os recursos básicos do laboratório: um serviço do Azure AI Search, um recurso do Azure AI Services e uma Storage Account. Esses serviços trabalham em conjunto para armazenar, enriquecer e indexar os documentos.

### 2. Upload dos documentos

Os arquivos de revisão de cafeterias foram enviados para um container no Azure Blob Storage. Esse conjunto de documentos funciona como base de dados do experimento e será usado pelo indexador para extrair conteúdo e metadados.

### 3. Importação de dados

No Azure AI Search, foi utilizada a opção **Import data** para conectar a origem de dados armazenada no Blob Storage. Nessa etapa, também foi definida a associação com o Azure AI Services, liberando os recursos cognitivos de enriquecimento.

### 4. Enriquecimento com IA

Durante a configuração do pipeline, foram habilitadas habilidades cognitivas como:

- OCR para leitura de texto em imagens
- Extração de frases-chave
- Detecção de sentimento
- Extração de locais mencionados
- Geração de campos enriquecidos para melhorar a busca

Esse processo permite transformar documentos brutos em dados mais estruturados e pesquisáveis.

### 5. Criação do índice

Após a definição dos campos e habilidades cognitivas, foi gerado o índice de busca. O índice é a estrutura que organiza os dados para permitir consultas rápidas, filtros e exploração por atributos específicos.

### 6. Execução do indexador

Em seguida, o indexador foi executado para processar os documentos, aplicar o enriquecimento e preencher o índice com os dados tratados. Esse passo automatiza a leitura dos arquivos e a atualização das informações no serviço de busca.

### 7. Exploração no Search Explorer

Com o índice criado, as consultas foram realizadas no **Search Explorer**. Exemplos de buscas usados nesse tipo de laboratório incluem a listagem de todos os documentos, filtros por localização e filtros por sentimento negativo, o que ajuda a validar se o enriquecimento funcionou corretamente.

## Exemplos de consultas

```json
{
  "search": "*",
  "count": true
}
```

Essa consulta retorna todos os documentos indexados e a quantidade total de registros disponíveis.

```json
{
  "search": "locations:'Chicago'"
}
```

Essa busca permite localizar documentos associados a uma determinada cidade identificada automaticamente no enriquecimento.

```json
{
  "search": "sentiment:'negative'"
}
```

Essa consulta ajuda a identificar avaliações com sentimento negativo, o que pode ser útil em cenários de monitoramento de satisfação do cliente.

## Insights obtidos

A prática mostrou que o Azure AI Search não se limita a procurar palavras em documentos. Ele também permite agregar valor ao conteúdo com análise cognitiva, facilitando a descoberta de padrões e informações importantes em grandes volumes de dados textuais.

Alguns aprendizados importantes deste laboratório foram:

- A ingestão de documentos é apenas a primeira parte do processo; o diferencial está no enriquecimento com IA.
- A criação de índices inteligentes melhora significativamente a capacidade de pesquisa e filtragem.
- Recursos como análise de sentimento e extração de frases-chave podem apoiar decisões de negócio com base em dados não estruturados.
- A documentação no GitHub ajuda a consolidar o aprendizado e a demonstrar domínio prático do conteúdo estudado.

## Conclusão

Este laboratório permitiu aplicar, na prática, conceitos de ingestão de conteúdo para IA, criação de índices inteligentes e exploração de dados enriquecidos. A experiência mostrou como o Azure AI Search pode ser utilizado para organizar documentos, extrair conhecimento e tornar grandes volumes de informação mais acessíveis por meio de pesquisa inteligente.
