---
name: tribunal_tjrs_primeiro_grau-mcp
description: Skill da REST API do Tribunal TJRS: Certidão do 1º Grau na MCP.AI: 1 endpoint em /api/tribunal_tjrs_primeiro_grau. Tribunal TJRS: Certidão do 1º Grau, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Tribunal TJRS: Certidão do 1º Grau — REST API skill

Você tem acesso à **Tribunal TJRS: Certidão do 1º Grau** REST API na MCP.AI.

> Tribunal TJRS: Certidão do 1º Grau, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/tribunal_tjrs_primeiro_grau
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/tribunal_tjrs_primeiro_grau/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"tipo_certidao":"...","nome":"...","endereco":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/tribunal_tjrs_primeiro_grau/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `tribunal_tjrs_primeiro_grau_consultar`

Tribunal TJRS: Certidão do 1º Grau, consulta em fonte oficial. _(POST /api/tribunal_tjrs_primeiro_grau/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `tipo_certidao` | string | Sim | Parâmetro de consulta "tipo_certidao". |
| `nacionalidade` | string | Não | Parâmetro de consulta "nacionalidade". |
| `cpf` | string | Não | Parâmetro de consulta "cpf". |
| `rg` | string | Não | Parâmetro de consulta "rg". |
| `orgao_expedidor_rg` | string | Não | Parâmetro de consulta "orgao_expedidor_rg". |
| `uf_rg` | string | Não | Parâmetro de consulta "uf_rg". |
| `genero` | string | Não | Parâmetro de consulta "genero". |
| `nome_mae` | string | Não | Parâmetro de consulta "nome_mae". |
| `nome_pai` | string | Não | Parâmetro de consulta "nome_pai". |
| `birthdate` | string | Não | Parâmetro de consulta "birthdate". |
| `cnpj` | string | Não | Parâmetro de consulta "cnpj". |
| `estado_civil` | string | Não | Parâmetro de consulta "estado_civil". |
| `nome` | string | Sim | Parâmetro de consulta "nome". |
| `endereco` | string | Sim | Parâmetro de consulta "endereco". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_tribunal_tjrs_primeiro_grau` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
