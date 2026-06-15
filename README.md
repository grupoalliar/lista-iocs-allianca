# lista-iocs-allianca

Repositório **público** de Indicators of Compromise (IOCs) da Alliança.

Contém lista de endereços IP usados em regras de bloqueio (firewall, WAF, SIEM, etc.).

> **Não é repositório de segredos.** Os dados aqui são intencionalmente públicos para consumo por ferramentas de segurança.

## Formato

- Arquivo: `lista-iocs-allianca.txt`
- Um IP por linha
- Atualizado via commits diretos na branch `main`

## Uso

Importe o arquivo nas ferramentas de threat intelligence / blocklist da sua infraestrutura.

## Segurança

Este repo **não entra na fila de rotação de credenciais**. Ver `docs/security/leak-triage-lista-iocs-allianca.md` para detalhes da triagem.
