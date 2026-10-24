---
name: frontend
description: Planejar, implementar quando autorizado e revisar a interface estática do portfólio em HTML e CSS, com foco em semântica, responsividade, acessibilidade e validação proporcional.
---

# Frontend para o portfólio

## Quando usar

Use estas orientações para estrutura HTML, estilos CSS, layout responsivo, acessibilidade e revisão da interface. Siga o modo solicitado: planejar não autoriza implementar.

## Contexto obrigatório

1. Leia `AGENTS.md`, `README.md`, `PLAN.MD` e, quando disponíveis, `docs/PRD.md` e `docs/PLAN.md`, a partir da raiz do repositório.
2. Inspecione arquivos, convenções e estado do Git antes de editar. Preserve alterações existentes do usuário e a licença MIT integralmente.
3. Informe divergências e requisitos ausentes. Consulte o estado da implementação em `PLAN.MD`: a base usa `index.html` e `css/styles.css`, sem dependências, build ou suíte de testes. A ausência de PRD ainda limita o mapeamento de requisitos oficiais.
4. Use o checkout existente. Não crie Git worktrees, branches, commits, Issues ou Pull Requests, nem faça push ou publicação sem autorização correspondente.

## Direção técnica

- Preserve HTML e CSS como base. Não adicione frameworks, gerenciadores de pacotes, dependências, ferramentas de build ou JavaScript sem necessidade e autorização compatíveis com o escopo.
- `index.html` e `css/styles.css` são caminhos propostos em `PLAN.MD`; confirme-os com o escopo aprovado e as convenções encontradas antes de criar arquivos.
- Trabalhe com o conteúdo pessoal validado. Consulte `skills/marketing-pessoal/SKILLS.md` quando a tarefa envolver redação ou posicionamento.
- Não invente seções, textos, imagens, contatos, métricas ou destinos de links. Rascunhos com pendências não equivalem a conteúdo aprovado.
- Não crie formulários que aparentem enviar mensagens sem uma solução funcional aprovada.

## Fluxo de trabalho

1. Relacione as entregas aos requisitos reais do PRD, quando disponível. Na ausência dele, use apenas requisitos substitutos explicitamente aprovados e registre a limitação.
2. Defina uma alteração pequena com arquivos afetados e critérios observáveis. Limite o trabalho à etapa autorizada.
3. Estruture o HTML com `<!doctype html>`, UTF-8, idioma correto, viewport e título descritivo. Use elementos semânticos conforme o conteúdo, um título principal claro e hierarquia coerente.
4. Use links para navegação e botões para ações. Prefira elementos nativos; use ARIA apenas quando necessário, sem duplicar semântica existente.
5. Organize o CSS de forma simples: base, variáveis reutilizáveis quando úteis, layout e componentes. Siga decisões visuais aprovadas; não trate sugestões de cores ou tipografia como requisitos oficiais.
6. Comece pelo layout para telas pequenas. Use medidas flexíveis, limites de largura e quebras guiadas pelo conteúdo, evitando alturas fixas que cortem texto.
7. Preserve foco visível e ordem de navegação lógica. Garanta contraste de pelo menos 4,5:1 em texto comum e 3:1 em texto grande, conforme WCAG AA; considere também contraste de controles e estados.
8. Em imagens aprovadas, use texto alternativo coerente com a função; imagens decorativas devem ter alternativa vazia. Preserve proporção e informe dimensões quando possível. Use carregamento tardio apenas onde apropriado.
9. Evite recursos externos desnecessários e CSS excessivo. Se houver animação aprovada, respeite `prefers-reduced-motion`.
10. Execute as verificações pertinentes, revise o diff e relate o que passou, falhou ou não pôde ser executado.

## Verificações

- Sirva o projeto, quando necessário, com `python3 -m http.server 8000 --bind 0.0.0.0 --directory /workspace/portifolio-web` em um terminal persistente. Reutilize um servidor existente somente após conferir que serve o diretório correto.
- Confira HTTP 200 e conteúdo esperado para a página e os recursos locais. Uma listagem de diretório ou uma porta aberta não comprova funcionamento da página.
- Inspecione a interface em larguras representativas, por exemplo 320, 768 e 1280 pixels, registrando as usadas; confira também ampliação de texto e ausência de rolagem horizontal indevida.
- Verifique todos os links e recursos locais da alteração, navegação por teclado, foco, títulos, idioma, alternativas de imagens e contraste.
- Use um validador HTML disponível quando possível. Não instale ferramentas sem autorização. Se o navegador ou validador não estiver disponível, registre a verificação como não executada.
- Execute `git diff --check` e revise também os arquivos novos, que não aparecem no diff comum enquanto não rastreados. Confira a preservação de `LICENSE`.
- Não apresente links de preview localhost na interface de onboarding. Requisições locais servem para validação interna.

## Formato da entrega

- Comportamento implementado ou proposta, conforme a autorização recebida.
- Arquivos afetados e requisitos reais atendidos, sem inventar RF/RNF.
- Verificações executadas e resultados observados.
- Limitações, verificações pendentes e decisões necessárias.

Não declare acessibilidade completa, compatibilidade geral ou desempenho medido com base apenas em inspeção parcial. Não implemente para compensar a ausência de aprovação do plano.
