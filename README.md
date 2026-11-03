# MCP Sentry

O MCP Sentry é um proxy local de segurança para MCP, com verificação de
integridade e controle de execução. Antes de iniciar o servidor protegido, o
Sentry confere sua implementação em relação à referência aprovada. Quando encontra
uma mudança, bloqueia a execução e oferece evidências para revisão assistida
por IA. A decisão de autorizar permanece com o operador.

**Distribuição experimental 1.3.5 para Windows.** Este repositório publica
os pacotes de instalação e as informações de uso do projeto.

## Download

**[Baixar MCP Sentry 1.3.5](https://github.com/mcp-sentry-project/mcp-sentry/releases/download/v1.3.5/mcp-sentry-1.3.5.zip)**

[Releases e notas de versão](https://github.com/mcp-sentry-project/mcp-sentry/releases)

Baixe o arquivo `mcp-sentry-1.3.5.zip` anexado à release. Os arquivos
automáticos “Source code” do GitHub contêm os documentos deste repositório;
o instalador está no pacote com o nome acima.

## Requisitos

- Windows com PowerShell.
- Cliente de IA com suporte a MCP local por `stdio`. O assistente oferece
  configuração para Codex e Claude Desktop; outros clientes exigem configuração manual.
- Servidor MCP de sua escolha já funcionando, com seu runtime e credenciais.
- Python 3.11+ com pip/venv. Se faltar, o instalador oferece baixar e instalar
  o Python oficial, mediante confirmação, conferindo SHA-256 e assinatura.
  Esse download exige internet.

O pacote inclui o proxy, o instalador e os guias. Não inclui o servidor MCP
protegido, seu runtime, suas credenciais ou o instalador do Python.

## Instalação

1. Baixe o ZIP e extraia todo o seu conteúdo.
2. Abra a pasta `instalar-mcp-sentry` e execute `INSTALAR.cmd`.
3. Ao concluir, aceite abrir o assistente, selecione o cliente e o servidor MCP
   e confira as confirmações de descoberta, aprovação inicial e configuração.
4. Reinicie as conexões do cliente e confira se o servidor MCP funciona pelo
   Sentry.

A instalação padrão fica em `%LOCALAPPDATA%\MCP-Sentry-Gateway`. Depois de
uma instalação nova concluída, o ZIP e a pasta extraída podem ser removidos.
Para proteger outro MCP ou atualizar, abra novamente o `INSTALAR.cmd` do pacote.

## Integridade do download

SHA-256 do ZIP 1.3.5:

```text
bf2998642c8f944469f5f07decb5036029297d21566cef730fbe07634518ea60
```

No PowerShell, na pasta do download:

```powershell
Get-FileHash .\mcp-sentry-1.3.5.zip -Algorithm SHA256
```

Compare o resultado com o valor acima. O instalador também confere as somas
dos arquivos internos. Essas somas detectam divergências; a confiança na
origem do download continua necessária.

## Ajuda e problemas

O ZIP contém `README.md` e a pasta `ajuda/`, com guias de configuração,
atualização, restauração, privacidade e solução de problemas.

Para relatar um problema, [abra uma issue](https://github.com/mcp-sentry-project/mcp-sentry/issues)
informando versão, Windows, cliente, etapa e mensagem de erro. Remova
credenciais e dados pessoais. Compartilhe somente os trechos necessários;
relatórios e arquivos de estado podem conter código ou dados locais.

## Testes e limites

A versão 1.3.5 passou por 222 testes automatizados do proxy (três ignorados)
e 30 do instalador, além de verificações de instalação, atualização e SDK MCP.

A demonstração manual registrada foi feita na versão 1.3.3, em um Windows
sem Python, confirmado limpo pelo operador: instalação do Python, do Sentry e
configuração no Codex. Ela não cobre a 1.3.5 nem todas as combinações de
clientes e arquiteturas.

O Sentry é um protótipo: depende de uma referência inicial e de um ambiente
confiáveis. Cobre a rota e os arquivos configurados; não é uma sandbox.
Conexões diretas ao servidor, sem passar pelo Sentry, ficam fora dessa
proteção. A IA pode errar na
revisão, e um parecer favorável sozinho não autoriza execução.

## Licença

O proxy, o instalador e os guias de uso são distribuídos sob a
[licença MIT](LICENSE).

## Autores

- [Davi Girardi Padilha](https://github.com/davi-padilha)
- [Pedro Henrique Astolfi Gonçalves](https://github.com/P3dro0406)

