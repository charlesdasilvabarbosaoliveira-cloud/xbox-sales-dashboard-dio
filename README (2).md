# 🎮 Xbox Sales Intelligence | Dashboard de Assinaturas no Excel

![Excel](https://img.shields.io/badge/Excel-Dashboard-217346?logo=microsoftexcel&logoColor=white) ![DIO](https://img.shields.io/badge/DIO-Desafio%20de%20Projeto-111827) ![Status](https://img.shields.io/badge/status-conclu%C3%ADdo-22c55e)

## Sobre o projeto

Dashboard analítico desenvolvido em Microsoft Excel para o desafio de visualização de vendas da **DIO**. O projeto converte uma base de assinaturas Xbox em informações executivas, com foco em organização, monitoramento de receita registrada e análise dos planos e modalidades de assinatura.

## 📊 Indicadores

- **Receita registrada:** soma dos valores totais dos registros, descontados os cupons.
- **Total de assinantes:** contagem dos registros de assinaturas.
- **Ticket médio:** receita registrada dividida pelo total de assinantes.
- **Taxa de renovação automática:** proporção de assinaturas com opção *Yes*.
- Receita por plano (Core, Standard, Ultimate).
- Receita por periodicidade (Monthly, Quarterly, Annual).
- Evolução mensal da receita por **data de início** da assinatura.

Os indicadores e gráficos são atualizados ao selecionar os filtros de **plano** e **periodicidade** na aba `DASHBOARD`.

## 🗂️ Arquivo e abas

| Aba | Finalidade |
|---|---|
| `DASHBOARD` | KPIs, filtros de seleção e gráficos comparativos. |
| `BASE DE DADOS` | Base de 295 registros, fórmulas de valor total e ano-mês, validações de entrada. |
| `ANÁLISES` | Tabelas auxiliares com fórmulas `SUMIFS` e `COUNTIFS`. |
| `GUIA` | Instruções de utilização, cálculos e origem dos dados. |

## 🔎 Origem dos dados

Material fornecido pela DIO para o desafio:

- [Base de dados Excel](https://hermes.dio.me/files/assets/805d54f9-6d53-4246-bed7-4aa2da615923.xlsx)
- [Dashboard de referência](https://hermes.dio.me/files/assets/0120950e-64c8-4092-a257-ba22ed198c69.xlsx)

Os dados incluem identificador, nome do assinante, plano contratado, data de início, renovação automática, valor da assinatura, tipo de assinatura, passes EA Play/Minecraft e descontos por cupom.

**Nota de interpretação:** os registros representam valores informados para assinaturas. Sua soma **não** equivale necessariamente a faturamento mensal recorrente, receita reconhecida contabilmente ou projeção anual. O gráfico mensal agrupa registros pelo mês de início da assinatura.

## ⚙️ Fórmulas e recursos

- **Total por assinatura:** `=SUM(F2,I2,K2)-L2` (soma valores numéricos; ignora o traço `-` de serviços não contratados).
- **Mês/ano:** `=TEXT(D2,"yyyy-mm")`.
- **Receita selecionada:** `SUMIFS` por plano e periodicidade.
- **Contagem de assinaturas:** `COUNTIFS` com os mesmos filtros.
- **Ticket médio:** `IFERROR(receita/assinantes,0)`.
- **Renovação automática:** assinaturas com `Yes` divididas pelo número de assinantes no filtro.
- Listas de validação para plano, tipo de assinatura, renovação e passes.
- Barras de dados condicionais e gráficos nativos do Excel.

A versão entregue está preparada para trabalhar com os **295 registros** fornecidos (linhas 2 a 296). Para incluir novas linhas além desse limite, é necessário estender as fórmulas de `BASE DE DADOS` e os intervalos das fórmulas de `DASHBOARD` e `ANÁLISES`.

## ▶️ Como reproduzir e usar

1. Faça o download do arquivo [`XBOX_SALES_INTELLIGENCE_DIO.xlsx`](./XBOX_SALES_INTELLIGENCE_DIO.xlsx) deste repositório.
2. Abra-o no Microsoft Excel e, se solicitado, habilite a edição.
3. Acesse `DASHBOARD` e selecione o plano e a periodicidade desejados (ou mantenha `Todos`).
4. Analise os KPIs e os três gráficos que reagem às seleções.
5. Para conferir os registros e fórmulas, visite `BASE DE DADOS` e `ANÁLISES`.
6. Para refazer o processo, baixe a base da DIO, mantenha os campos A–L, calcule as colunas M–N e reconstrua as agregações com `SUMIFS`/`COUNTIFS`, conforme exemplificado no arquivo.

**Requisitos:** Microsoft Excel com suporte a gráficos, validação de dados e às funções `SUMIFS`, `COUNTIFS`, `TEXT` e `IFERROR` (ou equivalentes localizados para o idioma da instalação).

## 📈 Aprendizados

Tratamento e estruturação de dados, criação de KPIs, cálculos condicionais, validação de entradas, visualização de indicadores, desenho de dashboards e documentação de projetos para portfólio.

## 📄 Entrega do desafio

O repositório deve conter pelo menos este `README.md` e a planilha `XBOX_SALES_INTELLIGENCE_DIO.xlsx`. Na plataforma DIO, enviar a **URL pública do repositório do GitHub**.

---

Projeto educacional elaborado a partir do conjunto de dados disponibilizado pela DIO.
