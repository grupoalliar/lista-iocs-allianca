# lista-iocs-allianca — triagem de leaks (gitleaks)

**Branch:** `hotfix`  
**Base:** `main`  
**Scan:** working tree, gitleaks 8.30.1 (2026-06-11)  
**Achados gitleaks:** 0  
**Visibilidade GitHub:** **público**

---

## Resumo executivo

| Veredito | Detalhe |
|----------|---------|
| **Fora do escopo de leak** | Repo publica IOCs (IPs maliciosos) de forma intencional |
| **Rotação** | **N/A** |
| **Ação** | Documentar propósito; **não** tratar como incidente de segredo |

---

## Contexto

Repositório mantido pela equipe de segurança/TI para distribuir **Indicators of Compromise** — endereços IP associados a atividade maliciosa, consumidos por:

- Firewalls / WAF
- SIEM / SOAR
- Ferramentas de threat intelligence

Conteúdo atual: `lista-iocs-allianca.txt` (~537 linhas, um IP por linha).

Exemplo:
```
181.30.42.98
199.71.235.199
128.14.232.87
...
```

---

## Varredura gitleaks

| Item | Resultado |
|------|-----------|
| Achados na working tree | 0 |
| Arquivos além da lista de IOCs | Nenhum (repo minimalista) |
| Credenciais, tokens, chaves | Não encontrados |
| Histórico git de `.env*` | N/A — repo sem arquivos de config |

---

## Por que não é leak

1. **Propósito explícito:** distribuição pública de blocklist — dado operacional de segurança, não credencial.
2. **Repo público no GitHub:** visibilidade intencional para integração externa.
3. **Conteúdo:** apenas endereços IP — gitleaks não classifica como segredo; scan confirmou 0 achados.

> IPs maliciosos **devem** ser públicos para efetividade de bloqueio colaborativo. Isso difere de API keys, passwords ou tokens.

---

## Riscos reais (fora do escopo gitleaks)

| Risco | Mitigação |
|-------|-----------|
| IP legítimo incluído por engano | Processo de revisão antes de commit; rollback via git |
| Lista desatualizada | Commits regulares (último: maio/2026) |
| Falsos positivos em scanners genéricos | Este documento + README do repo |

---

## Plano de rotação

**N/A** — nenhum segredo exposto.

---

## Recomendação na fila prioritária

**Remover da fila de remediação de leaks** ou marcar como **verificado — sem ação**.

Próximo repo com achado real na fila: **raimundo** (P4, majoritariamente mocks de teste) ou **portal-medico-front** (P8, token Mixpanel em `.env.development`).

---

## Checklist

- [x] Triagem concluída
- [x] README adicionado explicando propósito do repo
- [ ] Merge documentação (opcional — não bloqueia fila)
- [ ] Comunicar ao superior: repo excluído da fila de rotação
