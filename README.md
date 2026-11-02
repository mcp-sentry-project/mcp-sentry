# MCP Sentry

Gateway local que verifica alterações em servidores MCP antes de iniciá-los.
Quando encontra uma mudança em relação à referência aprovada, bloqueia a
execução e oferece evidências para revisão assistida por IA. A decisão de
autorizar permanece com o operador.

**Distribuição experimental 1.3.4 para Windows.** Este repositório publica
os pacotes de instalação e as informações de uso do projeto. O repositório
permanece privado durante a preparação; sua abertura será decidida depois.

## Download

**[Baixar MCP Sentry 1.3.4](https://github.com/davi-padilha/mcp-sentry/releases/download/v1.3.4/mcp-sentry-1.3.4.zip)**

[Releases e notas de versão](https://github.com/davi-padilha/mcp-sentry/releases)

Baixe o arquivo `mcp-sentry-1.3.4.zip` anexado à release. Os arquivos
automáticos “Source code” do GitHub contêm os documentos deste repositório;
o instalador está no pacote com o nome acima.

## Requisitos

- Windows com PowerShell.
- Cliente de IA com suporte a MCP local por `stdio`. O assistente oferece
  configuração para Codex e Claude Desktop; outros clientes exigem configuração manual.
- Servidor MCP de sua escolha já funcionando, com seu runtime e credenciais.
- Python 3.11+ com pip/venv. Se faltar, o instalador oferece baixar e instalar
  Python oficial, mediante confirmação, conferindo SHA-256 e assinatura.
  Esse download exige internet.

O pacote inclui o gateway, instalador e guias. Não inclui o servidor MCP
protegido, seu runtime, suas credenciais ou o instalador do Python.

## Instalação

1. Baixe o ZIP e extraia todo o seu conteúdo.
2. Abra a pasta `instalar-mcp-sentry` e execute `INSTALAR.cmd`.
3. Ao concluir, aceite abrir o assistente, selecione o cliente e o servidor MCP
   e confira as confirmações de descoberta, aprovação inicial e configuração.
4. Reinicie as conexões do cliente e confira o funcionamento pelo Sentry.

A instalação padrão fica em `%LOCALAPPDATA%\MCP-Sentry-Gateway`.
Depois de uma instalação nova concluída, o ZIP e a pasta extraída podem ser removidos.
Para proteger outro MCP ou atualizar, abra novamente o `INSTALAR.cmd` do pacote.

## Integridade do download

SHA-256 do ZIP 1.3.4:

```text
a186679bd77f35953882d82ae3925955b38a0f4194c3c88fc5314659bf1c8c63
```

No PowerShell, na pasta do download:

```powershell
Get-FileHash .\mcp-sentry-1.3.4.zip -Algorithm SHA256
```

Compare o resultado com o valor acima. O instalador também confere as somas
dos arquivos internos. Essas somas detectam divergências; a confiança na
origem do download continua necessária.

## Ajuda e problemas

O ZIP contém `README.md` e a pasta `ajuda/`, com guias de configuração,
atualização, restauração, privacidade e solução de problemas.

Para relatar um problema, [abra uma issue](https://github.com/davi-padilha/mcp-sentry/issues)
informando versão, Windows, cliente, etapa e mensagem de erro. Remova
credenciais e dados pessoais. Compartilhe somente os trechos necessários;
relatórios e arquivos de estado podem conter código ou dados locais.

## Estado e limites

Consulte o [resumo de validação](VALIDACAO.md) e o
[roteiro de teste em Windows limpo](TESTE-WINDOWS-LIMPO.md).

O Sentry é um protótipo: depende de uma referência inicial e de um ambiente
confiáveis. Cobre a rota e os arquivos configurados; não é uma sandbox.
Conexões diretas paralelas ficam fora dessa proteção. A IA pode errar na
revisão, e um parecer favorável sozinho não autoriza execução.

A instalação efetiva do Python em um Windows sem Python e o fluxo completo
nas interfaces gráficas dos clientes em outra máquina ainda não foram
validados. Não há declaração de compatibilidade universal com versões de
Windows ou clientes.

## Licença

O gateway, o instalador e os guias de uso são licenciados sob a
[MIT](LICENSE), que permite inclusive uso comercial e versões modificadas
fechadas, preservando os avisos exigidos. O wheel inclui os módulos Python
do gateway. A licença é incluída nos pacotes a partir da versão 1.3.4.

## Autores

- [Davi Padilha](https://github.com/davi-padilha)
- [Pedro Henrique Astolfi Gonçalves](https://github.com/P3dro0406)
