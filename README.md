# Korven

**Notas, reuniões e contexto pessoal em um só lugar. Com dados locais e uma estrutura preparada para agentes.**

O Korven é um aplicativo desktop para capturar, conectar e reencontrar as informações que atravessam o dia: uma conversa de trabalho, uma decisão de reunião, uma pessoa, um documento ou uma pendência pessoal.

Ele nasce de uma necessidade prática: administrar vários contextos sem precisar manter uma pilha de aplicativos e reconstruir, toda vez, o que aconteceu em cada um deles. A proposta é combinar o conforto de um editor de notas com informações estruturadas, gravação de reuniões e acesso por agentes de IA.

[Baixar a versão mais recente para Windows](https://github.com/VicSandoli/korven-releases/releases/latest)

## Por que construir o Korven?

Uma parte importante do nosso conhecimento fica espalhada entre notas, gravações, documentos e lembranças. Registrar ajuda, mas encontrar uma informação isolada nem sempre basta. Muitas vezes precisamos recuperar o contexto: quem participou, o que foi decidido, de onde veio uma tarefa e o que ainda está pendente.

O Korven busca reduzir esse esforço. Uma reunião pode aparecer dentro de uma nota; um trecho pode ser citado com sua origem; pessoas e tarefas podem se conectar às mesmas fontes. A organização cresce conforme a necessidade, sem exigir que tudo seja classificado antes de começar.

Um exemplo do fluxo que orienta o produto:

> Antes de uma reunião, recuperar o contexto anterior. Durante a conversa, gravar e anotar na mesma aplicação. Depois, usar um agente autorizado para produzir uma nota com referências às fontes e relacionar as pessoas e os próximos passos.

## O que já existe

- **Notas com editor de blocos:** texto rico, referências a objetos e blocos de reunião no corpo do documento.
- **Reuniões integradas:** captura de microfone e som do sistema em fontes separadas, transcrição ao vivo, anotações e reprodução do áudio.
- **Trechos com origem:** busca na transcrição e citações de passagens específicas da reunião.
- **Informação estruturada:** pessoas, grupos, tarefas, propriedades personalizadas, relações e Collections com visualizações em tabela.
- **Arquivos nas notas:** imagens no documento e anexos referenciáveis, incluindo PDFs.
- **Acesso por MCP:** agentes externos autorizados podem consultar a base e executar um conjunto controlado de criações e atualizações sobre as mesmas informações usadas pelo app.
- **Controle local:** base armazenada no computador, backup, restauração e exportação Markdown.
- **Atualizações pelo aplicativo:** consulta de novas releases e instalação de pacotes com assinatura verificada.

O projeto está em desenvolvimento ativo, com uso pessoal real orientando os ajustes. Os recursos atuais continuam recebendo validação e polimento.

## Inspirações

O Korven reúne ideias de aplicativos que ajudam a escrever, organizar e conectar conhecimento:

- **Notion:** inspiração para a autoria em blocos, composição de páginas e visualizações de informação estruturada.
- **SiYuan:** referência para blocos identificáveis, referências e uma experiência integrada sobre uma base local.
- **Obsidian:** inspiração para conexões entre informações, controle sobre o acervo e construção de uma base de conhecimento pessoal.

A combinação dessas ideias orienta uma experiência própria: capturar e escrever com fluidez, estruturar progressivamente e disponibilizar contexto confiável para agentes.

## Dados locais, contexto conectado

Notas, objetos, relações e transcrições são persistidos em uma base SQLite local. Áudios e anexos ficam em arquivos gerenciados junto dessa base. Essa estrutura permite consultar volumes maiores sem precisar abrir milhares de arquivos para reconstruir uma reunião.

Um objeto mantém a mesma identidade quando aparece em diferentes notas ou Collections. As apresentações apontam para a informação original, permitindo formar conexões sem multiplicar cópias.

Backup preserva a base e suas mídias; exportação Markdown permite levar o conteúdo para outros fluxos. A edição externa de Markdown com sincronização de volta ao app não faz parte da experiência atual.

O armazenamento é local. A transcrição atual utiliza um serviço externo configurado pelo usuário, e agentes ou provedores de IA podem receber o conteúdo compartilhado nos respectivos fluxos. Isso deve ser considerado ao escolher quais informações utilizar com esses serviços.

## Para onde queremos levar o produto

### Médio prazo

Consolidar o uso cotidiano de notas e reuniões, manter a aplicação fluida com acervos crescentes e melhorar a recuperação de contexto por agentes. O foco é combinar busca textual, filtros, relações e expansão de contexto com citações precisas e uso eficiente de tokens.

Também queremos tornar as visualizações e os fluxos pessoais mais adaptáveis, mantendo a organização simples e a origem das informações acessível.

### Longo prazo

Construir uma memória pessoal consultável e verificável: permitir que um agente autorizado reúna o contexto relevante de conversas, documentos, pessoas, decisões e pendências, com clareza sobre as fontes e sobre o que é uma interpretação.

Busca semântica, embeddings e recuperação híbrida fazem parte dessa direção, mas sua adoção depende de ganho medido sobre a busca existente. Escritas mais sensíveis deverão evoluir com propostas revisáveis, permissões, autoria e possibilidade de desfazer ações.

Essa é uma visão de evolução, não uma lista de recursos já entregues nem um compromisso de datas. O primeiro critério continua sendo resolver bem o trabalho pessoal do dia a dia.

## Sobre este repositório

Este é o espaço público de apresentação do Korven e distribuição dos instaladores. O código-fonte permanece em um repositório privado.

O projeto é criado e utilizado por [Victor Sandoli](https://github.com/VicSandoli), com evolução orientada pelas necessidades reais de uso. O alvo inicial é Windows x64.

## Instalar e atualizar

Baixe o instalador `.exe` na release mais recente. Para a instalação inicial, encerre gravações, feche o Korven e desconecte clientes MCP que estejam usando o executável a ser substituído.

A partir da versão 0.1.1, o aplicativo consulta novas releases ao abrir e periodicamente. Uma atualização disponível aparece na barra de status e em **Configurações → Atualizações**. Você escolhe quando baixar e instalar. O app salva os documentos e cria um backup da base antes de entregar ao instalador; gravações e ditado devem estar encerrados.

Instalações anteriores à 0.1.1 precisam receber esse primeiro instalador manualmente. Se o MCP estiver configurado para um executável do checkout de desenvolvimento, ajuste a conexão em **Configurações → MCP** usando o aplicativo instalado.

<details>
<summary>Arquivos da release e assinatura</summary>

- `.exe`: instalador Windows por usuário.
- `.exe.sig`: assinatura do pacote, verificada pelo updater.
- `latest.json`: manifesto utilizado pelo aplicativo.
- `SHA256SUMS.txt`: hashes para conferir o download.

A assinatura de update é diferente de Authenticode; o Windows pode exibir um aviso SmartScreen. As bases locais e as gravações não fazem parte do instalador. Se o app indicar que o servidor MCP está ocupado, desconecte temporariamente os clientes antes de atualizar.

</details>
