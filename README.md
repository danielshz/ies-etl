# Processo ETL do Projeto de Data Warehousing

## Introdução

O tema deste projeto é a análise da rede de Instituições de Ensino Superior (IES) no Brasil. A proposta é compreender a distribuição dessas instituições, os recursos de que dispõem e a composição de seus corpos técnico e docente. Essa análise visa identificar deficiências e fornecer subsídios para políticas públicas voltadas ao ensino superior. Questões como disparidades regionais, diferenças entre instituições públicas e privadas, e características demográficas dos docentes são exemplos do tipo de investigação que o projeto busca viabilizar.

Os dados utilizados provêm do **Censo da Educação Superior**, realizado anualmente pelo INEP, que documenta informações detalhadas sobre as IES do país. Para complementar as análises, foram integrados dados geográficos e demográficos de municípios brasileiros, possibilitando comparações em diferentes níveis de granularidade.

O objetivo geral do trabalho é implementar um ambiente analítico que permita aos tomadores de decisão explorar os dados de forma prática e intuitiva, utilizando ferramentas de alto nível para gerar insights a partir de consultas e visualizações. Este documento foca no processo de **ETL (Extração, Transformação e Carga)**, essencial para preparar os dados para as análises.

---

## Processo ETL

### Ferramentas e Fluxo Geral

1. **Pentaho**  
   Inicialmente, utilizamos o Pentaho para estruturar o fluxo ETL. No entanto, devido à grande quantidade de dados e limitações da ferramenta, migramos para o **Google Colab**.

2. **Google Colab**  
   No Colab, implementamos o processo ETL utilizando as bibliotecas **pandas** e **SQLite** para:
   - **Extração**: Importar microdados do INEP e dados do IBGE.
   - **Transformação**:
     - Limpeza e padronização das informações.
     - Geração de dimensões como Tempo, Localização Geográfica e Instituição.
     - Criação de chaves substitutas para relacionar tabelas de forma eficiente.
   - **Carga**: Armazenar os dados transformados em tabelas relacionais no SQLite e exportar para arquivos CSV.

## Conclusão

O processo ETL desenvolvido foi projetado para atender aos requisitos do projeto e possibilitar análises robustas e precisas. Embora eficiente, o fluxo pode ser aprimorado com o uso de ferramentas mais avançadas ou customizações específicas, conforme a evolução das necessidades analíticas.