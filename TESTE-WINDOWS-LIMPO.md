# Teste em Windows limpo

**Estado: pendente de execução.** Este roteiro não é evidência de aprovação.

Já houve instalação limpa do Sentry em ambientes novos na máquina de
desenvolvimento, usando Python existente. Este roteiro cobre a etapa adicional
de instalar Python de fato em um Windows sem Python e usar os clientes reais.

Use uma VM ou máquina descartável sem Python instalado, com internet e um
cliente compatível. Anote versão e arquitetura do Windows, versão do cliente
e data. Preserve um snapshot inicial para repetir o teste.

1. Prepare um servidor MCP de teste sem dados pessoais ou credenciais reais,
   usando um runtime que não instale Python. Confirme uma chamada direta no cliente.
2. Baixe o ZIP 1.3.5 da release e confira seu SHA-256.
3. Extraia em um caminho com espaços e abra `INSTALAR.cmd` por duplo clique.
4. Primeiro recuse o download do Python. Confira a mensagem e a saída sem
   instalação. Abra novamente e aceite o download.
5. Confira a verificação de hash e assinatura, a instalação efetiva do Python
   no perfil do usuário e a continuação da instalação do Sentry.
6. Configure o MCP pelo assistente. Confira as confirmações e o backup do
   cliente; reinicie as conexões e faça uma chamada pelo Sentry.
7. Altere um arquivo do servidor de teste. Reconecte e confira o bloqueio e
   a disponibilidade da revisão. Registre que o backend alterado não iniciou.
8. Leia as evidências, conclua a decisão explícita do operador e confira
   a retomada. Um parecer da IA sem autorização deve manter o bloqueio.
9. Reabra o instalador e confira o menu de proteger outro MCP, atualizar e sair.
10. Remova o ZIP e a pasta extraída e confira o funcionamento da instalação nova.

Repita a configuração para cada cliente que desejar declarar validado.
Não declare outras arquiteturas testadas com base em uma execução única.

Registre para cada etapa: resultado esperado, resultado observado, aprovado
ou reprovado, mensagens e logs necessários sem segredos. Se ocorrer reinício,
confira também a retomada após reiniciar. Atualize `VALIDACAO.md` somente
com resultados efetivamente observados, indicando ambiente e limitações.
