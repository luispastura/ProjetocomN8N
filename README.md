# 📌 Workflow EPD_CheeseBread_LongLegs

## 🚀 Descrição

Este workflow automatiza a coleta, processamento e armazenamento dos dados de ônibus em movimento, obtidos de uma API externa. O objetivo é padronizar e formatar os dados coletados, tornando-os prontos para análises posteriores.

## ⚙️ Funcionalidades

### ⏰ Agendamento Automático
- Execução periódica em intervalos definidos por minuto.

### 🌐 Integração via HTTP Request
- Obtém dados em formato bruto através de uma requisição GET.

### 🔍 Filtro Inteligente
- Exclui registros onde a velocidade do ônibus é "0" ou linha marcada como "GARAGEM".

### ⏱️ Cálculo do Tempo de Transmissão
- Determina o tempo entre a captura e o recebimento dos dados.

### 🗓️ Formatação Clara de Datas
- Converte timestamps em formato legível (`yyyy-MM-dd HH:mm:ss:SSS`).

### 📍 Padronização das Coordenadas GPS
- Ajusta as coordenadas geográficas para um formato consistente, substituindo vírgulas por pontos.

### 📊 Armazenamento Automatizado
- Envia dados tratados diretamente para o Google Sheets para futura análise.

## 🔄 Fluxo de Execução

```
Schedule Trigger → HTTP Request → Filtrar Velocidade e Linha → Calcula Transmissão → Formatar Datas → Padronizar GPS → Google Sheets
```

## 📝 Campos Registrados
- `datahora`: Data/hora original dos dados
- `datahoraenvio`: Data/hora do envio dos dados
- `datahoraservidor`: Data/hora de recebimento dos dados
- `latitude`: Latitude do veículo
- `longitude`: Longitude do veículo
- `linha`: Linha do ônibus
- `ordem`: Identificação do ônibus
- `velocidade`: Velocidade do ônibus
- `transmissao`: Tempo de transmissão dos dados

## 🛠️ Tecnologias Utilizadas
- n8n
- Google Sheets API
- REST API via HTTP

## 📋 Pré-requisitos
- Credenciais válidas configuradas no Google Sheets (n8n)
- URL da API disponível e acessível

## ⚠️ Notas Importantes

- Certifique-se de ativar a execução no n8n para garantir a captura contínua.
- Ajuste os parâmetros de filtro e formatação conforme necessidades específicas.

## 👨‍💻 Equipe de Desenvolvimento
- Gui Duran
- Daniel Lloyd
- Thiago Borsoni
- Luis Pastura
