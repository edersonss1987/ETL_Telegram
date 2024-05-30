# ETL_Telegram

**  Objetivo
O objetivo deste projeto é apresentar o processo de extração de dados do Telegram, em sua forma original em um formaro semi-estruturado(.JSON),transferir esses dados para um Datalake, realizar o processamento dos dados de forma automatizada e então fazer a análise dos dados tratados, usando linguagem SQL. Esses dados fornecem a base para extrair informações valiosas, abrindo possibilidades para aprimorar serviços e explorar oportunidades.

O que é Pipeline?
A palavra “pipeline” em inglês é frequentemente usada em português com o mesmo significado, especialmente em argumentos técnicos ou de negócios. No entanto ele é muito utilizado em um contexto de processamento de dados ou de projetos, pode ser traduzida como “fluxo de trabalho” ou “processo”.

Um Pipeline de Dados é uma série de etapas de processamento de dados, onde a saída de uma etapa é a entrada para a próxima. Essas etapas podem incluir coleta, limpeza, transformação, modelagem e visualização de dados.

Pipeline do projeto
O pipeline de dados deste projeto inicia com a ingestão dos dados de um aplicavo de mensagens, bastante conhecido TELEGRAM, as trocas de mensagens são coletadas via WEBHOOK, conectada a API da Amazon Web Services (AWS). Na plataforma da AWS, os dados são recebidos por uma função Lambda, que os organiza por dias no AWS S3. Diariamente, um AWS Event Bridge aciona um processo em lote no serviço Lambda, que transforma os dados brutos, extrai apenas as informações relevantes (data da mensagem,user_id, nome do contato,texto digitado e tipo de chat(grupo)) e os armazena de maneira organizada no AWS S3. No processo de visualização, tabelas criadas a partir dos arquivos Parquet gerados no passo anterior possibilitam a realização de análises variadas usando a linguagem SQL.**
