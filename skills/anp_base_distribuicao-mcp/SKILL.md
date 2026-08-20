---
name: anp_base_distribuicao-mcp
description: Skill da REST API do ANP: Base de Distribuição na MCP.AI: 1 endpoint em /api/anp_base_distribuicao. ANP: Base de Distribuição, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# ANP: Base de Distribuição — REST API skill

Você tem acesso à **ANP: Base de Distribuição** REST API na MCP.AI.

> ANP: Base de Distribuição, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/anp_base_distribuicao
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
curl -X POST https://api.mcp.ai/api/anp_base_distribuicao/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"cnpj":"...","tipo_instalacao":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/anp_base_distribuicao/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `anp_base_distribuicao_consultar`

ANP: Base de Distribuição, consulta em fonte oficial. _(POST /api/anp_base_distribuicao/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cnpj` | string | Sim | Parâmetro de consulta "cnpj". |
| `tipo_instalacao` | string | Sim | Parâmetro de consulta "tipo_instalacao". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_anp_base_distribuicao` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
