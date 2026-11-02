# Validação da distribuição 1.3.5

Construção e validação técnica concluídas em **2026-11-02**.

A 1.3.5 corrige o nome para **Davi Girardi Padilha** no README do pacote,
na licença da raiz do ZIP, na licença do wheel e nos metadados de autoria.
Pedro Henrique Astolfi Gonçalves permanece nos avisos de autoria.
A lógica de proteção e revisão não mudou. As versões anteriores foram preservadas.

## Resultados desta construção

- Gateway: 225 testes, 222 aprovados e 3 ignorados.
- Instalador: 30 testes aprovados.
- Os 19 módulos conferem entre fonte, wheel e instalação.
- Instalação limpa do Sentry em novo ambiente, atualização desde 1.0.0,
  caminhos com espaços, menus de Codex e Claude Desktop em perfis fictícios,
  lançador CMD e execução sem a pasta extraída passaram.
- Transporte stdio e SDK MCP passaram, incluindo bloqueio antes da execução
  do backend alterado, revisão separada, uso único e aceitação permanente.
- A licença é preservada junto à ajuda instalada. O nome completo foi
  conferido diretamente nos arquivos e nos metadados do ZIP e do wheel.

## O que significa instalação limpa neste registro

O instalador do Sentry foi executado de fato em uma pasta e um ambiente novos,
na máquina de desenvolvimento, usando Python já disponível. Os perfis dos
clientes e os servidores MCP eram fictícios e isolados.

A ausência de Python, o download e a instalação do Python foram simulados
nas fronteiras do sistema operacional nos 30 testes do instalador. Isso
verifica o fluxo do programa, mas não equivale a instalar Python de fato
em uma VM Windows sem Python. Separadamente, a
[demonstração manual da 1.3.3](DEMO-INSTALADOR.md), analisada em 02/11/2026,
mostra Python instalado pelo assistente, Sentry instalado e configuração no
Codex. O operador confirmou que o Windows estava limpo e sem Python.
Portanto, há evidência manual desse fluxo; ela não é uma execução do ZIP 1.3.5.

Os downloads reais dos instaladores Python para x64, x86 e ARM64 tiveram
SHA-256 e assinatura conferidos na 1.3.3 em 25/10/2026, sem executá-los.
Essa verificação de rede não foi repetida na 1.3.5.

## Pacote

O ZIP contém doze arquivos, incluindo a licença MIT e a lista de somas.

```text
Arquivo: mcp-sentry-1.3.5.zip
SHA-256: bf2998642c8f944469f5f07decb5036029297d21566cef730fbe07634518ea60
```

O repositório permanece privado. O [roteiro de Windows limpo](TESTE-WINDOWS-LIMPO.md)
identifica o trecho já demonstrado e os cenários adicionais ainda não exibidos.
Não houve nova bateria com modelos.
