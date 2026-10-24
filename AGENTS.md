# Orientações para trabalhar no portfólio

## Contexto e fontes

- O README descreve um portfólio em HTML e CSS. Preserve essa escolha enquanto não houver uma decisão explícita em contrário.
- Preserve integralmente `LICENSE`, incluindo a licença MIT e o copyright existente.
- Antes de planejar ou implementar, leia as instruções `AGENTS.md` aplicáveis, este arquivo, `README.md`, `docs/PRD.md` e `docs/PLAN.md`, quando disponíveis.
- No momento da criação deste documento, `docs/PRD.md` e `docs/PLAN.md` não existem. O plano provisório está em `PLAN.MD`, na raiz.
- Informe documentos ausentes e divergências antes de propor mudanças. Não invente identificadores RF/RNF, critérios oficiais, conteúdo pessoal ou decisões de produto.

## Escopo e autorização

- A implementação da Etapa 1 depende de aprovação explícita do plano. A criação destes documentos não autoriza implementar a aplicação.
- Em tarefas de planejamento, não altere arquivos, instale dependências ou execute ações de implementação, salvo autorização específica.
- Não crie branches, commits, Issues ou Pull Requests, nem faça push ou publicação sem autorização para a ação correspondente.
- Use o checkout existente. O ambiente de nuvem já é isolado; não crie Git worktrees sem solicitação explícita.

## Convenções propostas para a Etapa 1

- Prefira HTML semântico e CSS simples, sem frameworks, dependências ou ferramenta de build, salvo requisito aprovado.
- Use UTF-8, idioma correto no documento, metadados essenciais e hierarquia coerente de títulos.
- Considere responsividade, contraste e uso por teclado desde a base; elementos interativos devem apresentar foco visível.
- Mantenha mudanças pequenas e limitadas à etapa aprovada. Preserve decisões existentes compatíveis com o PRD quando ele estiver disponível.
- Antes de editar, confira o estado do Git e os arquivos existentes. Preserve alterações do usuário e não sobrescreva arquivos sem inspeção.

## Execução e verificação

- Para servir arquivos estáticos, quando necessário: `python3 -m http.server 8000 --bind 0.0.0.0 --directory /workspace/portifolio-web`.
- A página inicial está em `index.html`, com estilos em `css/styles.css`. A raiz do servidor deve retornar essa página, não uma listagem de diretório.
- Verifique respostas HTTP, carregamento do CSS, comportamento em celular e desktop, estrutura semântica e navegação por teclado.
- Confira o diff e execute `git diff --check` ao concluir alterações.
- Relate verificações executadas, resultados e limitações. Não declare testes ou critérios como atendidos sem evidência.
