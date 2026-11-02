# Validação da distribuição 1.3.3

Validação técnica original concluída em **25/10/2026**. Esta página resume os
registros da construção; não representa uma nova execução de toda a bateria.

## Resultados registrados

- Gateway: 225 testes, com 222 aprovados e três ignorados.
- Instalador: 30 testes aprovados, incluindo consentimento, menus,
  integridade, recuperação e falhas. Rede e instalação do Python foram
  simuladas nas fronteiras do sistema operacional nessa bateria.
- Downloads reais dos instaladores oficiais Python para x64, x86 e ARM64:
  SHA-256 e Authenticode conferidos, com editor Python Software Foundation.
  Os instaladores Python não foram executados.
- Instalação do wheel, caminhos com espaços, lançador CMD, ajuda instalada,
  recusa de arquivos alterados e uso após remover a pasta extraída passaram.
- Atualização desde 1.0.0 preservou estado e configuração.
- Configuração e menus para Codex e Claude Desktop passaram em perfis
  descartáveis, com servidores fictícios e backups.
- Transporte stdio e SDK MCP: chamada normal, bloqueio antes da inicialização
  do backend alterado, revisão separada, autorização de uso único e aceitação
  permanente passaram.
- Os 19 módulos conferiram entre fonte, wheel e instalação.

## Conferência para publicação

Em **02/11/2026**, o ZIP existente foi reconferido para publicação: hash
externo correspondente ao registro da construção e dez arquivos internos
correspondentes às somas incluídas. O pacote contém onze arquivos ao todo,
incluindo a própria lista de somas. O ZIP validado foi preservado sem alteração.

```text
Arquivo: mcp-sentry-1.3.3.zip
SHA-256: bcf3c200df8bc11dc9e50e4cf3510bce5a17d8b948458468a8a8f0599895c5f8
```

## Verificações ainda pendentes

- Instalação efetiva do Python em uma VM ou máquina Windows sem Python.
- Instalação e configuração completas nas interfaces gráficas dos clientes
  em outra máquina.

Os testes em perfis fictícios não substituem essas verificações. O roteiro
está em [TESTE-WINDOWS-LIMPO.md](TESTE-WINDOWS-LIMPO.md). A distribuição é
publicada como experimental com esses limites explícitos.
