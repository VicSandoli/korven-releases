# Korven

Aplicativo local para notas, reuniões, transcrições e relações entre informações.

Este repositório contém apenas os instaladores assinados e as notas de release para Windows x64. O código-fonte é mantido em um repositório privado.

## Instalar e atualizar

Baixe o instalador `.exe` na [release estável mais recente](https://github.com/VicSandoli/korven-releases/releases/latest). Feche o Korven antes da instalação inicial.

A partir da versão 0.1.1, o aplicativo consulta novas releases ao abrir e periodicamente. Uma atualização disponível aparece na barra de status e em **Configurações → Atualizações**. Você escolhe quando baixar e instalar. O app salva os documentos e cria um backup da base antes da instalação; encerre gravações e ditado antes de atualizar. Desconecte temporariamente os clientes MCP se o app indicar que o servidor está ocupado.

Instalações anteriores à 0.1.1 precisam receber este primeiro instalador manualmente. Depois, as atualizações são oferecidas pelo próprio app. Se o MCP estiver configurado para um executável do checkout de desenvolvimento, ajuste a conexão em **Configurações → MCP** usando o aplicativo instalado.

## Arquivos da release

- `.exe`: instalador Windows por usuário.
- `.exe.sig`: assinatura do pacote, verificada pelo updater.
- `latest.json`: manifesto utilizado pelo aplicativo.
- `SHA256SUMS.txt`: hashes para conferir o download.

A assinatura de update é obrigatória e diferente da assinatura Authenticode do Windows. O Windows pode exibir um aviso SmartScreen. As bases locais e as gravações não fazem parte do instalador.
