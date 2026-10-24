# Plano do portfólio

## Etapa 1 — Fundação do portfólio

Status: fundação implementada após autorização explícita do usuário na conversa, no escopo provisório deste plano. Mapeamento ao PRD e validações adicionais continuam pendentes conforme descrito abaixo.

## Estado atual

- Na inspeção anterior à criação destes documentos, o repositório continha apenas `README.md` e `LICENSE`, no commit `aadd7ff`.
- O README define o projeto como um portfólio HTML e CSS.
- A licença é MIT, com copyright de Rogerio Campos, 2026, e deve ser preservada integralmente.
- Antes da implementação, não havia páginas ou estilos. Agora existem `index.html` e `css/styles.css`, sem dependências, scripts de build ou suíte de testes.
- A branch local encontrada é `work`; a seleção inicial do ambiente indicava `main`. Nenhuma troca de branch foi realizada.
- `AGENTS.md` e este `PLAN.MD` são documentos criados por solicitação do usuário. Não representam implementação da aplicação.

## Documentos ausentes e divergências

- Antes da criação destes documentos, não foram encontrados `AGENTS.md` aplicáveis. `docs/PRD.md` e `docs/PLAN.md` continuam ausentes.
- Este arquivo fica na raiz e tem o nome solicitado `PLAN.MD`; ele não substitui silenciosamente o documento ausente `docs/PLAN.md`.
- As orientações locais estão em `AGENTS.md`, na raiz do repositório.
- Sem PRD e plano oficial, não é possível mapear RF/RNF e critérios de aceitação oficiais. O usuário autorizou a implementação deste plano provisório; ele é a referência do escopo executado.

## Objetivo

Preparar uma base estática organizada, responsiva e acessível em HTML e CSS, respeitando o README e as decisões que forem confirmadas no PRD.

## Limites

- A estrutura semântica e os estilos base fazem parte da proposta.
- Conteúdo das seções, textos pessoais e identidade visual final dependem de confirmação. A base usa o nome existente no repositório, texto de portfólio em construção, cores neutras com destaque verde e fontes do sistema; não inclui biografia, projetos ou contatos fictícios.
- Não estão previstos frameworks, dependências, ferramenta de build, integrações, formulário funcional, deploy ou publicação.
- Não antecipar etapas posteriores nem alterar a licença.

## Tarefas propostas

1. Ler `docs/PRD.md` e `docs/PLAN.md` quando disponíveis, ou os requisitos substitutos explicitamente aprovados, e reconciliar este plano com a definição oficial da Etapa 1.
2. Confirmar os requisitos, critérios de aceitação e decisões visuais necessários; registrar divergências antes da implementação.
3. Confirmar a estrutura mínima `index.html` e `css/styles.css`, sem ferramenta de build.
4. Criar o HTML com idioma, codificação, viewport, título e estrutura semântica conforme o escopo aprovado.
5. Criar o CSS base com normalização mínima, tipografia, cores, espaçamento e layout responsivo conforme as decisões aprovadas.
6. Aplicar os fundamentos de acessibilidade pertinentes: títulos coerentes, contraste, uso por teclado e foco visível nos elementos interativos existentes.
7. Atualizar o README com estrutura, execução local e verificações manuais.
8. Executar as verificações, revisar o diff e registrar resultados, limitações e pendências.

## Arquivos da implementação

| Arquivo | Ação realizada |
| --- | --- |
| `index.html` | Criada a estrutura semântica, metadados e link para pular ao conteúdo |
| `css/styles.css` | Criados estilos base, foco visível e layout responsivo |
| `README.md` | Documentadas organização, execução e verificações |
| `AGENTS.md` | Atualizadas as instruções de verificação para a página existente |
| `skills/frontend/SKILLS.md` | Atualizado o contexto para refletir a implementação |
| `PLAN.MD` | Registrados autorização, resultados e pendências |

`LICENSE` foi preservado integralmente. Não foram criados manifestos de dependências, lockfiles ou configurações de publicação.

## Requisitos e aceitação

Mapeamento RF/RNF: pendente do PRD. Nenhum identificador oficial foi atribuído. Os critérios provisórios abaixo foram usados na implementação e nas verificações.

Critérios provisórios adotados:

- A página inicial abre pelo servidor estático e carrega o CSS sem erros.
- O HTML contém metadados e estrutura semântica adequados ao conteúdo aprovado.
- O layout não apresenta rolagem horizontal indevida em telas pequenas e permanece legível no desktop.
- Elementos interativos, se previstos, funcionam por teclado e apresentam foco visível.
- O README permite reproduzir a execução local e as verificações.
- A licença permanece integralmente preservada.

Após a disponibilização do PRD, relacionar cada tarefa e critério aos identificadores RF/RNF reais e revisar divergências antes de ampliar o escopo.

## Verificações propostas

1. Iniciar o servidor estático e verificar HTTP 200 para a página e o CSS, conferindo o conteúdo retornado.
2. Inspecionar o carregamento de recursos no navegador e verificar arquivos ausentes.
3. Inspecionar o layout em larguras de celular e desktop, registrando as dimensões usadas.
4. Conferir idioma, hierarquia de títulos, contraste, ordem de navegação e foco por teclado.
5. Validar o HTML com ferramenta disponível, sem instalar dependências sem autorização.
6. Conferir `git diff --check`, o diff completo, o estado do checkout e a preservação de `LICENSE`.

## Resultados das verificações

- HTTP: raiz e CSS retornaram 200, tipos de conteúdo corretos e corpos idênticos aos arquivos locais.
- Chromium headless, via Playwright já instalado: título, idioma, metadados, um único `h1`, landmarks, CSS aplicado e destinos das duas âncoras verificados.
- Layout em 320, 375, 768 e 1280 pixels: sem overflow horizontal e com os elementos principais dentro da largura disponível. Revisão visual das capturas de 320 e 1280 pixels realizada.
- Texto ampliado a 200%, em 320 pixels: sem overflow horizontal ou sobreposição com o cabeçalho; captura também revisada. Essa verificação não equivale a testar zoom real em todos os navegadores.
- Teclado: link para pular ao conteúdo aparece ao receber foco, leva o foco ao `main` e o link de início funciona; ambos exibem contorno de foco.
- Contrastes calculados sobre o fundo: texto principal 13,53:1, secundário 5,70:1 e destaque 7,19:1, acima de 4,5:1.
- Nenhum erro de página, recurso HTTP ou requisição foi observado no Chromium durante a execução.
- Verificação de whitespace e revisão dos arquivos novos realizadas; licença comparada ao Git sem alterações.
- Não executados: validador HTML dedicado (não disponível), leitores de tela, outros navegadores e auditoria completa de acessibilidade. Não foram instaladas ferramentas ou dependências.

As verificações foram executadas com script temporário fora do checkout, em `/tmp/portfolio-etapa1`. O projeto continua sem suíte permanente de testes.

## Pendências e riscos que exigem decisão humana

- Disponibilizar o PRD e o plano oficial para reconciliar os requisitos com a fundação provisória implementada.
- Confirmar conteúdo e identidade visual antes de ampliar a página; a base visual inicial não representa uma identidade final aprovada.
- Confirmar a referência de base antes de futuras operações de Git devido à diferença entre `main` e a branch local `work`. A implementação permaneceu no checkout e na branch existentes.
- Decidir se o plano deve futuramente ser movido de `PLAN.MD` para `docs/PLAN.md`; essa alteração não faz parte da criação atual.

## Branch sugerida

`feat/etapa-1-fundacao-portfolio`

Nome apenas sugerido; nenhuma branch deve ser criada sem autorização.

## Aprovação

A implementação da Etapa 1 foi autorizada explicitamente pelo usuário na conversa. Essa autorização foi aplicada à fundação descrita neste plano, sem instalação de dependências ou operações de criação de branch, commits, Issues, Pull Requests, push ou publicação. Etapas seguintes dependem de nova definição de escopo.

## Etapa 2 — Apresentação e conteúdo

Status: implementada conforme a solicitação de avançar para a Etapa 2, usando as informações públicas do GitHub solicitadas pelo usuário e aceitas na conversa.

### Objetivo e limites

Substituir o aviso de construção por apresentação, Sobre, projetos e acesso ao perfil no GitHub. Preservar HTML/CSS, paleta, tipografia, responsividade e acessibilidade da fundação.

Não incluir histórico profissional, formação, senioridade, métricas de impacto, contatos adicionais, formulário, integrações, JavaScript, dependências ou publicação. O PRD continua ausente; não foram atribuídos identificadores RF/RNF.

### Tarefas concluídas

1. Consultar perfil público e READMEs, distinguindo informações documentadas de afirmações não verificadas.
2. Adicionar apresentação e Sobre com tecnologias presentes nos projetos, sem atribuir nível de domínio.
3. Criar três cartões de projetos com descrições e links reais.
4. Adicionar navegação Sobre, Projetos e Contato, chamadas para ação e retorno ao início.
5. Adaptar o CSS para as novas seções e cartões, sem alterar a base visual.
6. Atualizar descrição da página, README e este plano, registrando fontes, escopo e resultados.

### Fontes e uso

| Fonte pública | Uso no portfólio |
| --- | --- |
| https://github.com/RogerioCampos07 | Nome Rogerio Campos, bio “Amo tecnologia” e destino do perfil |
| https://github.com/RogerioCampos07/docpipe-ingestion | Recebimento, validação, armazenamento de documentos e eventos; Python, FastAPI e RabbitMQ |
| https://github.com/RogerioCampos07/rag_agent | Agente de suporte com RAG; LangChain, ChromaDB, Streamlit, Python e Docker |
| https://github.com/RogerioCampos07/DjangoAdminStock | Produtos, fornecedores, movimentações e saldo de estoque com Python e Django |

As descrições são sínteses dos READMEs. Esses projetos não foram executados durante a implementação do portfólio; sua presença não comprova experiência comercial ou uso em produção. Não foram usados forks para atribuir autoria de terceiros ao usuário.

### Arquivos alterados

- `index.html`: apresentação, navegação, Sobre, três projetos, Contato e metadados.
- `css/styles.css`: layouts de seções e cartões, links e adaptação responsiva.
- `README.md`: estado, fontes e verificações das novas seções.
- `PLAN.MD`: escopo e evidências da Etapa 2.

### Critérios e verificações

- Página e CSS retornaram HTTP 200, com conteúdo idêntico aos arquivos locais.
- Três projetos, um único `h1`, idioma `pt-BR`, navegação nomeada e destinos das âncoras conferidos no Chromium headless via Playwright já disponível.
- Layout em 320, 375, 768 e 1280 pixels sem overflow horizontal; revisão visual das capturas de 320 e 1280 pixels realizada.
- Texto ampliado a 200% em 320 pixels sem overflow horizontal; não equivale a teste de zoom real em todos os navegadores.
- Os 12 links foram alcançados por Tab com foco visível; link para pular ao conteúdo transferiu foco ao `main`. As três opções do menu navegaram para as respectivas seções.
- Perfil e três repositórios retornaram HTTP 200 na consulta pública.
- Nenhum erro de página ou recurso HTTP foi observado na execução do navegador.
- A paleta preserva os contrastes de texto calculados na Etapa 1; botões usam destaque verde e fundo claro em contraste inverso.
- Script de validação e capturas em `/tmp/portfolio-etapa2`, fora do checkout. Nenhuma dependência instalada.

### Limitações e pendências

Validador HTML dedicado, outros navegadores, leitores de tela e auditoria completa de acessibilidade não foram executados. Conteúdo e tecnologias devem ser revisados quando os repositórios de origem mudarem. E-mail, LinkedIn e formulário dependem de informações e escopo adicionais; não são necessários para os links de GitHub entregues nesta etapa.

## Etapa 3 — Preparação para GitHub Pages

Status: preparação local implementada conforme o escopo combinado na conversa. Ativação e publicação no GitHub não realizadas.

### Objetivo e limites

Preparar a hospedagem estática em `https://rogeriocampos07.github.io/portifolio-web/`, pela raiz da branch `main`, sem build de aplicação ou dependências. Preservar o conteúdo e a base visual existentes. O destino indicado é planejado; não representa um endereço publicado e validado.

Não criar workflow de deploy, domínio personalizado, framework ou novas funcionalidades. Não criar branches, commits ou Pull Requests, não fazer push nem alterar as configurações remotas do Pages. O PRD permanece ausente; o escopo definido na conversa orienta esta etapa, sem inventar RF/RNF.

### Tarefas concluídas

1. Inspecionar os caminhos de recursos e links: o CSS relativo e as âncoras existentes já são compatíveis com `/portifolio-web/`; nenhuma alteração de HTML ou CSS foi necessária.
2. Criar `.nojekyll` vazio na raiz para desativar o processamento Jekyll e servir os arquivos diretamente.
3. Documentar no README a origem `main` / `/ (root)`, a configuração **Deploy from a branch**, o endereço previsto e a conferência após publicação.
4. Documentar e executar simulação local com o mesmo prefixo do Pages, usando servidor Python em loopback, sem instalar dependências.
5. Validar carregamento, metadados, navegação, teclado e responsividade no caminho-base de publicação.

### Arquivos alterados

- `.nojekyll`: criado na raiz; deve acompanhar os arquivos do site na branch de publicação.
- `README.md`: procedimento do GitHub Pages, simulação local e verificações após ativação.
- `PLAN.MD`: registro do escopo executado, evidências e pendências.

### Critérios de aceitação e resultados

- Página, CSS e `.nojekyll` retornaram HTTP 200 sob `/portifolio-web/`, com corpos idênticos aos arquivos locais.
- Chromium via Playwright já disponível: CSS carregado de `/portifolio-web/css/styles.css`, sem erros nos recursos declarados pela página e sem requisições monitoradas escapando do prefixo. O log do servidor registrou uma consulta automática a `/favicon.ico` com 404; não há favicon declarado, e isso não impediu o carregamento da página ou do CSS.
- Idioma `pt-BR`, título, um único `h1`, três projetos e destinos das âncoras verificados.
- Layout em 320, 375, 768 e 1280 pixels sem overflow horizontal; texto ampliado a 200% em 320 pixels também sem overflow.
- Os 12 links foram alcançados por Tab com foco visível; o link para pular ao conteúdo transferiu foco ao `main`.
- Sobre, Projetos, Contato e retorno ao início preservaram `/portifolio-web/` ao navegar.
- A paleta e os estilos não foram alterados; permanecem os contrastes calculados na Etapa 1.
- Verificados whitespace dos arquivos envolvidos e preservação de `LICENSE`. Scripts temporários e capturas ficaram fora do checkout, em `/tmp/portfolio-etapa3`.

### Pendências para publicação

Após autorização específica, entregar os arquivos à branch remota `main` e configurar o Pages conforme o README. A branch local continua `work`; não foi renomeada ou substituída. Muitos arquivos novos ainda estão sem rastreamento no Git e precisarão integrar a entrega, inclusive `.nojekyll`.

A validação local não testa a infraestrutura do GitHub Pages. É necessário aguardar o deploy real e conferir HTTP, CSS e links no endereço fornecido pelo GitHub. Não foram executados validador HTML dedicado, outros navegadores, leitor de tela ou auditoria completa de acessibilidade; ampliação de texto não equivale a zoom real em todos os navegadores.

A publicação pela raiz também pode expor os documentos não ocultos do repositório. Não foram adicionados segredos, formulário ou contatos novos nesta etapa.
