# Calculadora da Reforma Tributária (CBS/IBS)

### O cálculo oficial de CBS e IBS dentro do seu ChatGPT ou Claude

**O cálculo oficial de CBS e IBS dentro do seu ChatGPT ou Claude.** Usa o código aberto oficial da Receita Federal (regime regular 1.6.1, Simples Nacional 0.0.6, base V0059 de 30/09/2026), sem recálculo próprio. Base V0059: só tem alíquotas de referência de 2026. Não substitui a análise do seu contador. Serviço independente, sem vínculo com a Receita Federal.

- 🧾 **CBS, IBS-UF, IBS-Mun e Imposto Seletivo** por item, com a memória de cálculo oficial e a norma
- 🏪 **Regime regular e Simples Nacional**
- 📚 **Tabelas oficiais**: CST, cClassTrib, fundamentação legal, NCM, NBS e atividades do Simples
- 🧩 **XML**: gera os grupos de IBS/CBS/IS e valida contra o XSD oficial
- 🔎 **Rastreável**: toda resposta traz repositório, versão, commit e versão da base
- 🔒 **Sem login e sem chave**, grátis
- 💬 **Funciona com qualquer cliente MCP**: Claude, ChatGPT, Cursor, VS Code

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Calculadora da Reforma Tributária (CBS/IBS)` e **URL** `https://api.mcp.ai/p_calculadora_rtc`.

### Cursor

[➕ Instalar Calculadora da Reforma Tributária (CBS/IBS) no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=calculadora_rtc&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9jYWxjdWxhZG9yYV9ydGMifQ==)

### VS Code (Copilot Chat)

[➕ Instalar Calculadora da Reforma Tributária (CBS/IBS) no VS Code](vscode:mcp/install?name=calculadora_rtc&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_calculadora_rtc%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_calculadora_rtc
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Calcule a CBS e o IBS de um serviço de consultoria empresarial de R$ 5.000 prestado em Campo Grande/MS em março de 2026, com tributação integral
O que significa o cClassTrib 200028? Qual a redução e a fundamentação legal?
Confira se o grupo de IBS/CBS deste XML de NF-e está válido no leiaute oficial: [cole o XML]
```

---

## 8 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `calculadora_rtc_regime_regular` | Calcula CBS, IBS (UF e município) e Imposto Seletivo de uma operação do REGIME REGULAR (LC 214/2025) pela calculadora oficial da Receita, com erros por item (um item inválido não derruba os outros). |
| `calculadora_rtc_simples_nacional` | Calcula CBS e IBS de uma operação de empresa do SIMPLES NACIONAL pela calculadora oficial da Receita (NT 2026.005), com erros por item. |
| `calculadora_rtc_aliquotas` | Alíquotas de REFERÊNCIA de CBS (União), IBS estadual (UF) e IBS municipal vigentes numa data, direto da base oficial. |
| `calculadora_rtc_consultar_tabela` | Consulta as tabelas oficiais da calculadora numa data de vigência. |
| `calculadora_rtc_explicar_erro` | Explica códigos de erro das calculadoras oficiais: REG-xxx (regime regular) e VSN-xxx (Simples Nacional), com título, descrição e orientação do catálogo oficial. |
| `calculadora_rtc_base_calculo` | Base de cálculo UNIFICADA oficial de um item de NF-e/NFC-e (documento 'nfe') ou NFS-e ('nfse'): devolve as bases do regime regular, do Imposto Seletivo e do Simples Nacional, aplicando a vigência de cada componente no… |
| `calculadora_rtc_gerar_xml` | Calcula a operação do regime regular (modo estrito: qualquer item inválido recusa a operação inteira) e gera o XML dos grupos de tributação IBS/CBS/IS para o documento fiscal (`tipo`: nfe, nfce, cte, bpe, nf3e, nfcom… |
| `calculadora_rtc_validar_xml` | Valida um XML contra o XSD oficial: só os grupos de tributação (subtipo 'grupo') ou a nota completa ('nota'). |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Grátis.

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O cálculo é da Receita Federal?**
O cálculo é feito pelo código aberto oficial que a Receita Federal publicou (licença MIT), rodando sem alteração. O serviço é independente e não tem vínculo nem endosso da Receita.

**Quais anos ele cobre?**
A base oficial V0059 (30/09/2026) só tem alíquotas de referência de 2026. De 2027 em diante a calculadora exige que você informe as alíquotas e o resultado sai como simulação.

**Substitui o contador?**
Não. O resultado é o da calculadora oficial para os dados informados; classificação e enquadramento são decisão sua e do seu contador.

**Precisa de login ou chave?**
Não. É grátis e hospedado pela plataforma.


---

## Suporte

- 📧 [calculadora_rtc@mcp.ai](mailto:calculadora_rtc@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/calculadora_rtc-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_calculadora_rtc` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
