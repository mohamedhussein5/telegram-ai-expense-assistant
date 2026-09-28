# Interview and Resume Notes

## 30-second project introduction

I built an AI-powered financial assistant on Telegram that automates receipt management and personal expense tracking. The Make.com workflow accepts receipts, bank-transfer screenshots and PDF documents, uses Gemini 2.5 Flash to extract structured transaction data, archives source files in Google Drive and records the results in Google Sheets. Users can also ask natural-language questions about weekly or monthly spending and receive calculated answers directly in Telegram.

## Resume bullet points

- Designed an event-driven expense automation workflow integrating Telegram, Google Drive, Google Sheets and Gemini 2.5 Flash.
- Implemented conditional routing for two distinct paths: multimodal transaction extraction and natural-language expense queries.
- Converted unstructured receipts and transfer records into a consistent JSON schema containing dates, merchants, line items and totals.
- Built a context-aware retrieval flow that aggregates spreadsheet records and returns concise, date-specific spending summaries in Telegram.
- Reduced repeated processing and unnecessary messages by aggregating multi-row Google Sheets results before sending them to the language model.

## Interview talking points

### Handling incomplete transaction details

Some bank screenshots do not clearly identify a merchant or payment purpose. The workflow combines the image with the user's Telegram caption so Gemini can use both visual and written context when producing the transaction record.

### Preventing repeated executions

Google Sheets searches can return several bundles. A text-aggregation step combines the matching records before the AI query, reducing repeated model calls and preventing multiple Telegram replies.

### Producing reliable responses

The extraction prompt requires a strict JSON structure, while the query prompt limits the response to the requested calculation. Formatting constraints also prevent internal spreadsheet values, such as date serial numbers, from appearing in user-facing replies.

## Suggested project title

**AI-Powered Telegram Expense Assistant — Multimodal Receipt Processing and Conversational Spending Analytics**
