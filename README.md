# ETL com python e GPT-4

## Descrição:
Este projeto é parte do [Santander Bootcamp 2023 de Ciência de Dados com Python](https://web.dio.me/track/santander-bootcamp-2023-ciencia-de-dados-com-python?tab) e tem como objetivo abrir as portas para o mundo da ciência de dados e inteligência artificial.

## ETL:
ETL é uma sigla que significa "Extract, Transform, Load" em inglês, e se refere a um processo de integração de dados usado em engenharia de dados e em bancos de dados. Cada etapa do processo tem uma função específica:

- Extract (Extrair): Nesta etapa, os dados são coletados de diversas fontes, como bancos de dados, sistemas, arquivos, serviços da web, entre outros. Os dados são extraídos dessas fontes em seu formato bruto e geralmente são armazenados temporariamente em uma área de armazenamento intermediária.

- Transform (Transformar): Após a extração, os dados passam por uma série de transformações. Essas transformações podem incluir a limpeza e normalização dos dados, a eliminação de duplicatas, a conversão de formatos, a agregação de informações e a aplicação de regras de negócios. O objetivo é preparar os dados para que sejam úteis e coerentes para análises ou para serem carregados em um novo sistema.

- Load (Carregar): Na etapa final, os dados transformados são carregados em um repositório de destino, que pode ser um banco de dados, um data warehouse, um sistema de armazenamento em nuvem ou qualquer outro local onde os dados serão usados para análise ou aplicação em processos de negócios.

## Funcionamento:

Neste projeto, utilizamos a biblioteca Pandas para ler um documento no formato CSV (Comma-Separated Values) e obter os identificadores dos usuários armazenados na API fornecida pelo curso (conforme indicado pelo [link para Swagger da API](https://sdw-2023-prd.up.railway.app/swagger-ui/index.html#/)). Uma vez que temos em nossa posse os identificadores, fazemos requisições à referida API a fim de obter informações completas sobre os usuários. Com os dados completos dos usuários, a etapa de Extração é considerada concluída.

Em seguida, iniciamos a fase de Transformação, que envolve o envio de uma solicitação à API do chat GPT-4 para cada usuário, permitindo que o sistema gere uma mensagem personalizada e única para cada um deles. Posteriormente, usamos a resposta para atualizar o atributo 'news' dos usuários em nossa aplicação.

Por fim, na etapa de Carregar, efetuamos uma requisição à primeira API para garantir que os usuários estejam atualizados com as novas mensagens.

