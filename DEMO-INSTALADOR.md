# Demonstração de instalação em Windows sem Python

Análise visual de `demo_instalador.mp4`, recebida e registrada em 02/11/2026.
A gravação mostra a versão **1.3.3**. O operador confirmou que o ambiente era
um Windows limpo, sem Python previamente instalado. A data exibida na barra
do Windows é **25/10/2026**.

## Etapas observadas

Os tempos abaixo são posições aproximadas na gravação, de 41,67 segundos.

| Trecho | Evidência visual |
| --- | --- |
| 00:00–00:05 | Pacote `mcp-sentry-1.3.3` no Explorer e janela do instalador aberta. |
| 00:06 | O instalador informa que não encontrou Python 3.11+ e oferece baixar Python 3.13.17 (amd64) de python.org. |
| 00:07–00:09 | Confirmação `s`, progresso de transferência e mensagens de conferência de SHA-256/assinatura e instalação do Python. |
| 00:10–00:11 | Mensagem de Python instalado e verificado; o caminho encontrado aponta ao Python 3.13.17 no perfil do usuário. |
| 00:12–00:15 | Instalação do wheel e mensagens de instalação bem-sucedida do MCP Sentry 1.3.3, com ambiente e ajuda instalados. |
| 00:15–00:25 | Abertura do assistente, escolha do Codex, seleção de `server_teste`, arquivos a proteger e confirmação `DESCOBRIR`. |
| 00:30–00:36 | Catálogo de ferramentas, confirmações `APROVAR` e `SUBSTITUIR`, resultado `connected_restart_required`, backup e registro de instalação. |
| 00:37–00:41 | Interface real do Codex aberta; a resposta à pergunta sobre ferramentas identifica `Server Teste` e `MCP Sentry Review`. |

## Conclusão

Há evidência visual do fluxo de instalação do Python seguido da instalação
do Sentry 1.3.3 e de sua configuração assistida para o Codex. Com a confirmação
do operador sobre o estado inicial, a demonstração deve ser registrada como
**teste manual em Windows limpo, sem Python**, e não apenas como simulação.

Isso complementa os testes automatizados, nos quais a instalação do Python
continua corretamente descrita como simulada na fronteira do sistema operacional.
A pendência genérica de que esse fluxo nunca foi testado em máquina limpa
estava incorreta e foi corrigida na documentação.

## Escopo da evidência

- O vídeo mostra o resultado do instalador e a confirmação do operador
  caracteriza o estado inicial. Não há inventário independente prévio do Windows.
- As mensagens mostram a etapa de hash/assinatura, mas o vídeo não fornece
  os hashes calculados ou um relatório independente de Authenticode.
- A resposta do Codex identifica os conectores; não mostra uma chamada
  específica a uma ferramenta protegida nem um ciclo de alteração, bloqueio,
  revisão e autorização nessa instalação.
- Não demonstra Claude Desktop, instalação em x86/ARM64, recusa do download,
  falhas de rede ou atualização de uma instalação anterior.
- O pacote exibido é 1.3.3. Não é uma execução manual dos ZIPs 1.3.4 ou 1.3.5.
- O relógio do Windows avança alguns minutos dentro de uma gravação de
  41,67 segundos; a duração do vídeo não é uma medição de tempo de instalação.

## Identificação da gravação

Vídeo H.264, 1920×1080, 30 quadros/s, duração aproximada de 41,67 segundos.
SHA-256 do arquivo analisado:

```text
9673a09df7b64e530be83b780e0ed6849a51b503f8e23df6390a1268e4b855ef
```

Foi feita análise visual com amostragem e quadros adicionais nas transições.
O vídeo original e os quadros de análise permanecem locais; este repositório
contém o relato escrito. A análise não executou os instaladores mostrados.
