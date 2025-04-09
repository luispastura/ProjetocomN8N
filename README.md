# ProjetocomN8N
Descrição:

Este workflow automatiza a captura, processamento e armazenamento de dados de ônibus em movimento, provenientes de uma API externa, com objetivo de formatar e padronizar os dados para análises posteriores.

Funcionalidades:

Agendamento de Execução:

Utiliza o nó "Schedule Trigger" configurado para execução periódica em minutos específicos.

Requisição HTTP:

Realiza uma requisição HTTP GET na URL especificada para obter os dados brutos dos ônibus (https://web-production-1e19.up.railway.app/onibus_bruto).

Filtragem de Dados:

Aplica um filtro para excluir registros com velocidade igual a "0" e registros com linha marcada como "GARAGEM".

Cálculo de Tempo de Transmissão:

Calcula o tempo gasto na transmissão de dados (transmissao) com base nas diferenças entre as datas (datahoraservidor e datahora).

Formatação de Datas:

Transforma timestamps em formato legível de data e hora padrão (yyyy-MM-dd HH:mm:ss:SSS).

Padronização dos Dados de GPS:

Corrige o formato das coordenadas geográficas substituindo vírgulas por pontos.

Armazenamento no Google Sheets:

Insere os dados tratados em uma planilha específica do Google Sheets, facilitando análises posteriores.

Estrutura do Workflow:

Schedule Trigger → HTTP Request → Filtrar Velocidade e Linha → Calcula Transmissão → Formatar Datas → Padronizar GPS → Google Sheets

Campos Armazenados:

datahora: Data e hora original dos dados

datahoraenvio: Data e hora do envio dos dados

datahoraservidor: Data e hora de recebimento dos dados no servidor

latitude: Latitude do veículo

longitude: Longitude do veículo

linha: Linha do ônibus

ordem: Código identificador do ônibus

velocidade: Velocidade do ônibus

transmissao: Tempo decorrido para transmissão dos dados

Tecnologias utilizadas:

n8n

Google Sheets API

HTTP REST API

Requisitos de uso:

Credenciais válidas do Google Sheets configuradas no n8n

URL da API ativa e acessível

Considerações:

Certifique-se de que a execução do workflow esteja ativa no n8n para captura contínua dos dados. Ajuste os filtros e formatações conforme necessário para atender a requisitos específicos do projeto.

Desenvolvedores:

Gui Duran

Daniel Lloyd

Thiago Borsoni

Luis Pastura
