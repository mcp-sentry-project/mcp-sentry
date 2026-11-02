# Validação da distribuição 1.3.4

Construção e validação técnica concluídas em **2026-11-02**.

## Resultados

- Gateway: 225 testes, 222 aprovados e 3 ignorados.
- Instalador: 30 testes aprovados. Rede e instalação do Python simuladas nas fronteiras do sistema operacional nessa bateria.
- Os 19 módulos conferem entre fonte, wheel e instalação.
- Instalação limpa do gateway, atualização desde 1.0.0, caminhos com espaços,
  lançador CMD e funcionamento após remover a pasta extraída passaram.
- Menus e configuração em perfis fictícios de Codex e Claude Desktop passaram,
  com preservação das demais entradas e backups.
- Transporte stdio e SDK MCP passaram, incluindo bloqueio do backend alterado,
  revisão separada, uso único e aceitação permanente.
- A licença MIT confere com a fonte na raiz do ZIP e no wheel. Sua cópia junto
  à ajuda instalada também foi verificada.

## Pacote

O ZIP contém doze arquivos, incluindo a licença e a lista de somas.

```text
Arquivo: mcp-sentry-1.3.4.zip
SHA-256: a186679bd77f35953882d82ae3925955b38a0f4194c3c88fc5314659bf1c8c63
```

A 1.3.3 permanece preservada sem alterações em seus anexos. Os downloads reais
dos instaladores Python para x64, x86 e ARM64 tiveram hash e assinatura
conferidos na validação da 1.3.3 em 25/10/2026; essa verificação de rede não foi
repetida na 1.3.4. Não foram executados instaladores Python nessa verificação.

## Limites e pendências

O repositório permanece privado durante a preparação. Não foi realizada
instalação efetiva do Python em Windows sem Python, nem teste completo nas
interfaces gráficas dos clientes em outra máquina. Os testes usam perfis e
servidores fictícios; não substituem essas verificações.

O [roteiro de Windows limpo](TESTE-WINDOWS-LIMPO.md) continua pendente.
Não houve nova bateria com modelos. O Sentry continua sendo um protótipo.
