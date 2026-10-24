# portifolio-web

Portfólio pessoal de Rogerio Campos, desenvolvido com HTML e CSS.

## Estado do projeto

A Etapa 1 entrega a fundação estática: documento semântico, estilos responsivos,
metadados e navegação por teclado. A Etapa 2 acrescenta apresentação, Sobre,
três projetos públicos e acesso ao perfil no GitHub, com navegação entre seções.
O conteúdo foi reunido do perfil e dos READMEs públicos e aprovado na conversa.
Não inclui histórico profissional, resultados comerciais ou contatos não confirmados.

A Etapa 3 prepara a publicação estática no GitHub Pages, pela raiz da branch
`main`, sem build de aplicação ou dependências. A ativação e a publicação no
GitHub ainda não foram realizadas.

O escopo segue `PLAN.MD`, aprovado para implementação na conversa. `docs/PRD.md`
e `docs/PLAN.md` ainda não existem, portanto o mapeamento de RF/RNF e as decisões
finais de conteúdo e identidade visual continuam pendentes. As cores e fontes
locais são uma base inicial ajustável.

## Estrutura

```text
index.html                          Página inicial
.nojekyll                           Desativa o processamento Jekyll no Pages
css/styles.css                      Estilos base e layout responsivo
AGENTS.md                           Orientações para trabalhar no projeto
PLAN.MD                             Escopo e acompanhamento das etapas
skills/frontend/SKILLS.md            Orientações de frontend
skills/marketing-pessoal/SKILLS.md   Orientações de conteúdo
LICENSE                             Licença MIT
```

## Executar localmente

Não há dependências para instalar nem etapa de build. Com Python 3 disponível,
execute na raiz do repositório:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Abra o servidor na porta 8000 em seu navegador local. Encerre com `Ctrl+C`.
No ambiente de nuvem, use `--bind 0.0.0.0` se necessário; processos devem ser
reiniciados após restauração. Não é necessário modificar arquivos para iniciar.

## GitHub Pages

Destino previsto: `https://rogeriocampos07.github.io/portifolio-web/`.
Esse endereço é o destino planejado, não uma confirmação de site ativo.

O CSS usa o caminho relativo `css/styles.css`, e os links internos usam âncoras
como `#projetos`. Preserve esse padrão para funcionar sob `/portifolio-web/`;
caminhos como `/css/styles.css` apontariam para a raiz do domínio.
`.nojekyll` mantém a publicação como arquivos estáticos, sem Jekyll.
Não é necessário criar workflow próprio de deploy ou instalar ferramentas.

Após autorização para versionar e publicar:

1. Garanta que `index.html`, `css/styles.css` e `.nojekyll` estejam na raiz da
   branch remota `main`. A branch local encontrada é `work`; a entrega à `main`
   deve ser tratada separadamente, preservando o trabalho existente.
2. No GitHub, abra **Settings → Pages → Build and deployment**.
3. Em **Source**, selecione **Deploy from a branch**.
4. Selecione a branch **main**, pasta **/ (root)**, e salve.
5. Aguarde a execução de publicação do GitHub Pages terminar com sucesso.
6. Confira o endereço informado pelo GitHub: a página e
   `/portifolio-web/css/styles.css` devem retornar HTTP 200. Teste a navegação
   entre seções, os projetos e a atualização sem cache.

A origem é a raiz do repositório: documentos de desenvolvimento não ocultos
também podem ficar acessíveis por URL. Não coloque credenciais ou conteúdo
privado nessa pasta. Não há domínio personalizado ou arquivo `CNAME` configurado.

### Simular o caminho do Pages localmente

Execute a partir da pasta que contém o checkout `portifolio-web`. No ambiente
de nuvem, essa pasta é `/workspace`:

```sh
python3 -m http.server 8001 --bind 127.0.0.1 --directory /workspace
```

No navegador local, abra o caminho `/portifolio-web/` na porta 8001. Confira que
o CSS carrega de `/portifolio-web/css/styles.css` e que os links do menu preservam
esse prefixo. Use somente para validação local e encerre com `Ctrl+C`; não exponha
a pasta `/workspace` publicamente. Em outra máquina, substitua `/workspace`
pela pasta que contém o checkout.

## Verificações manuais

1. Confira que a raiz retorna a página e que `css/styles.css` carrega com HTTP 200.
2. Inspecione o layout em larguras de 320, 768 e 1280 pixels: texto legível,
   sem cortes nem rolagem horizontal indevida.
3. Amplie texto ou zoom para 200% e confira a leitura e o acesso aos links.
4. Use `Tab`: o primeiro link deve revelar “Pular para o conteúdo”. Ative-o com
   `Enter` e confirme que o foco chega ao conteúdo principal. Confira também o
   foco visível e a navegação do link de início.
5. Confira o idioma `pt-BR`, o título da página, um único `h1`, os destinos dos
   links e o contraste dos textos. Teste Sobre, Projetos, Contato e o retorno
   ao início; confira os links dos três projetos e do perfil no GitHub.
6. Execute `git diff --check`, revise os arquivos novos e confirme que `LICENSE`
   não foi alterado.

Não existe uma suíte de testes ou ferramenta de build no projeto. A validação
do navegador e eventuais verificações automatizadas devem ter seus resultados
e limitações registrados, sem instalar ferramentas apenas para executar a página.

## Fontes do conteúdo

- [Perfil de Rogerio Campos](https://github.com/RogerioCampos07): nome e bio.
- [DocPipe Ingestion](https://github.com/RogerioCampos07/docpipe-ingestion): recebimento, validação e armazenamento de documentos com FastAPI e eventos RabbitMQ.
- [RAG Agent](https://github.com/RogerioCampos07/rag_agent): agente com RAG, LangChain, ChromaDB e Streamlit.
- [Django Admin Stock](https://github.com/RogerioCampos07/DjangoAdminStock): gestão de estoque pelo Django Admin.

As descrições refletem os READMEs consultados, não uma execução ou auditoria
dos projetos. Não há formulário de envio: a seção Contato leva ao perfil público.

## Licença

MIT, conforme o arquivo `LICENSE`, preservado integralmente.
