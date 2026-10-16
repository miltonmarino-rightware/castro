# CASTRO’S V4 — COMEÇAR AQUI

## Handoff mestre de continuidade

**Ler primeiro:** [MASTER_CONTINUATION.md](MASTER_CONTINUATION.md)

- Repo: [rightware-corporations/castro-service](https://github.com/rightware-corporations/castro-service)
- Branch: `handoff/castros-v4-2026-10-17`
- Master publicado no commit [f864607](https://github.com/rightware-corporations/castro-service/commit/f8646072ad0ac3fbb87d8cff1ce54d767e3658fe).
- Auditoria de recuperação inicial: [e063074](https://github.com/rightware-corporations/castro-service/commit/e0630743facaade99f075ccd51a608cdc502e98e).
- Baseline funcional preservada: `d646f1c9f2b9cb4df81cdb8d512e2db8a9777c28` (PR #66).
- Para o HEAD mais recente, consultar o [histórico desta branch](https://github.com/rightware-corporations/castro-service/commits/handoff/castros-v4-2026-10-17) ou executar `git log -5 --oneline`.

O master reúne commits recentes, arquitetura, contratos, PRs, QA comprovada vs histórica, pistas de recuperação, comandos e backlog P0/P1/P2.

**O source V4 posterior continua por recuperar/publicar.** Estes commits de documentação não incorporam ficheiros locais que o chat não conseguiu ler. Não confundir a baseline remota #66 com a versão visual V4 aprovada.

## Auditoria inicial preservada

O conteúdo abaixo conserva o diagnóstico original. Para continuidade atual, o master acima tem precedência sobre as referências de estado deste arquivo.

---

# CASTRO’S V4 — HANDOFF DE RECUPERAÇÃO
Data: 2026-10-17 (Africa/Johannesburg)
Repositório: https://github.com/rightware-corporations/castro-service
Branch deste handoff: handoff/castros-v4-2026-10-17

## 1. Ler primeiro: o que está efetivamente guardado

Esta branch preserva a baseline remota do PR #66 em
d646f1c9f2b9cb4df81cdb8d512e2db8a9777c28
e acrescenta este handoff.

**Esta branch NÃO contém a implementação local posterior do CASTRO’S V4, Scene Navigation v2 ou o polish final. Não a apresentar como a versão visual aprovada.**

A publicação deste documento é uma entrega parcial de recuperação. Não significa que todas as alterações locais foram commitadas. O terminal do chat falha antes de executar comandos, com "setup refresh had errors". O acesso alternativo ao filesystem também falhou. Não foi possível verificar o checkout local indicado pelo proprietário:
C:\Neneco\codes\codes1\castro-service-main

Nenhum ficheiro local foi sobrescrito, descartado ou reconstruído para produzir este handoff. Nenhuma integração em main ou deployment foi efetuada.

## 2. Como recuperar esta entrega remota

Num diretório novo:

    git clone --branch handoff/castros-v4-2026-10-17 https://github.com/rightware-corporations/castro-service.git castros-handoff
    cd castros-handoff
    git log -1 --oneline

Esta cópia serve para inspecionar os contratos funcionais preservados e este documento. Ainda é necessário recuperar o source V4 local antes de continuar a implementação visual.

## 3. Auditoria remota verificada antes de criar esta branch

- main: 7f0d79ade32e500f3d2ee122d1a94ec9383d2c4a, de 2026-09-09.
- Último push então registado: 2026-09-23.
- 68 branches: 60 contidas no histórico de main, sete com commits exclusivos e a própria main.
- Cinco PRs abertos; apenas #66 está em draft.
- feat/castros-v4-redesign não existia no remoto.
- GitHub não conseguiu resolver 6b578c5 nem 1f7921f.
- Nenhuma tag ou release encontrada.
- O workflow mais recente do #66 não tem artifacts disponíveis.
- main e a branch do #66 não têm o diretório frontend/public/v4-approved, os novos componentes SceneMorph/PracticeInteractions/useSceneNavigation/sceneIntent ou os relatórios finais V4.
- Os handoffs históricos em docs apontam para estados de setembro e não substituem este diagnóstico.

### PRs abertos

| PR | Branch / estado | Situação |
| --- | --- | --- |
| #66 | feat/castros-contract-v1-foundations; draft | 9 commits à frente de main, 0 atrás; sem conflitos; Frontend, Backend e PostgreSQL verdes no head d646f1c. Baseline funcional disponível, não o V4 posterior. |
| #62 | feat/castros-v3-operational-spatial-refinement | 37 à frente, 4 atrás; sem conflitos com main; CI 3/3 verde. Diverge do #66. Auditar apenas funcionalidade única; não integrar a branch inteira. |
| #11 | feature/authentication-hardening | 5 à frente, 392 atrás; conflitos. Revisar funcionalidades de sessões antes de considerar redundante. |
| #13 | feature/access-security | 6 à frente, 386 atrás; conflitos. Revisar política de passwords/revogação de sessões. |
| #63 | rightware-corporations-patch-2 | 1 à frente, 4 atrás; conflitos. frontend/public/images/image1 contém só uma quebra de linha, não uma imagem. Em main, frontend/public/images é também um ficheiro de uma quebra de linha, não uma pasta. |

O SessionRevocationService e UserAccountSessionSerializationTest propostos nos PRs de segurança não foram encontrados nos paths correspondentes de main. Não concluir que a segurança está completa apenas por CI verde. Não se realizou auditoria funcional exaustiva de segurança nesta passagem.

Outras branches com commits fora de main:
- feature/training-system-completion: 1 à frente, 167 atrás; alteração de tipografia posterior ao trabalho integrado pelo PR #39.
- fix/experience-2-visible-home-change: 2 à frente, 27 atrás; PR #60 fechado sem merge, CSS visual antigo. Não reintegrar automaticamente no V4.

Links:
- PR #66: https://github.com/rightware-corporations/castro-service/pull/66
- CI #66: https://github.com/rightware-corporations/castro-service/actions/runs/35887959864
- PR #62: https://github.com/rightware-corporations/castro-service/pull/62
- CI #62: https://github.com/rightware-corporations/castro-service/actions/runs/34782576365
- CI main: https://github.com/rightware-corporations/castro-service/actions/runs/34373865421
- PR #11: https://github.com/rightware-corporations/castro-service/pull/11
- PR #13: https://github.com/rightware-corporations/castro-service/pull/13
- PR #63: https://github.com/rightware-corporations/castro-service/pull/63

Os PRs acima não foram alterados, fechados ou integrados para produzir este documento.

## 4. Estado V4 conhecido apenas pelo trabalho anterior deste chat

Baselines históricas:
- 6b578c5: refine(home): approve H05 responsive practice layout
- 1f7921f8f9fe9c6969f10b42801d09c904b28b70: feat(home): build V4 H05 to H06 consulting chapter

O último HEAD local então verificado era 1f7921f, na branch feat/castros-v4-redesign, com alterações posteriores ainda sem commit. A existência atual dessa cópia local NÃO foi confirmada.

Depois desse commit, o chat implementou:
- Continuação dos capítulos H06–H12.
- Scene Navigation v2: um controlador, duas intenções independentes para wheel/swipe/teclado; primeiro gesto prepara, segundo confirma.
- H04/H07/H09 como transferências temporizadas, não secções de repouso.
- H05 com três authored media cards: Consultoria / Formação / Espaços.
- H06 com quatro hotspots textless, sem substituir por listas no mobile.
- H08 com fotografia aprovada e dialog central de cursos dinâmicos; sem board-overlay.
- H10 com porta interativa e dialog; CTA navega à rota real do explorador.
- Focus, Escape/close, restauração de foco, reduced motion, estados loading/error/empty e contratos de rotas preservados.
- Último polish: hero com retrato completo; fitting contain; cards maiores; símbolo real do logo antes de alongar; H04 de 1,1 para 2,8 segundos.
- Entrada visual em Espaços de 1 segundo, cancelável por Escape; reduced motion e cliques modificados seguem navegação nativa.
- Foto original de Elizabeth no capítulo da fundadora, por autorização posterior explícita; H12 minimal com CTA /contacto.

Esses itens são histórico de trabalho, NÃO descrição do source presente nesta branch.

### QA histórica registada no chat

Na cópia anterior, foram registados:
- 47 ficheiros / 226 testes passaram.
- TypeScript, lint e production build passaram.
- Cinco viewports: 1440x900, 1024x768, 768x1024, 390x844, 320x568.
- Zoom nativo Chrome 200%, teclado/foco, dialogs, Escape, restauração do foco, reduced motion e deep-links.
- scrollWidth === clientWidth nas sete cenas estáveis.
- 11 PNG aprovados com hashes preservados.
- 127 capturas e três vídeos na última galeria.
- Persistiam warning de lint em CourseSettingsPage.tsx:82, advisory de bundle >500 kB e favicon 404.
- Catálogo de cursos do preview vazio; não inventar cursos, datas ou disponibilidade.
- Sem testes físicos de trackpad, Safari/iOS ou hardware mobile.
- Estado final: parar para revisão humana; sem aceitação visual final confirmada.

**Não foram executados esses testes sobre a branch deste handoff.** Os logs e captures precisam de ser recuperados para inspeção independente.

## 5. Onde procurar a recuperação local

Diretório indicado pelo proprietário:
C:\Neneco\codes\codes1\castro-service-main

Workspace antigo registado no chat:
C:\Users\administrator\Documents\Codex\2026-09-15\figma-plugin-figma-openai-curated-remote

Dentro do workspace antigo, procurar:
- work/castro-service/ — checkout completo, incluindo .git, ficheiros rastreados e não rastreados.
- outputs/v4-visual-polish/ — capturas, vídeos, REVIEW.md, logs, manifesto, patch e source-snapshot.
- outputs/CASTROS_V4_VISUAL_POLISH_REVIEW.zip
- outputs/v4-scene-v2/ — snapshot e artefactos da passagem v2 anterior.
- outputs/CASTROS_V4_SCENE_NAVIGATION_V2_VISUAL_REVIEW.zip
- work/castro-service/docs/V4_VISUAL_POLISH_REVIEW.md
- work/castro-service/docs/V4_SCENE_NAVIGATION_V2_REVIEW.md

Os paths são referências históricas, não ficheiros confirmados no PC atual. URLs localhost:5173/5176 são locais e não permitem ao colega recuperar o source pela Internet.

Pacotes anteriormente fornecidos pelo proprietário, úteis para procurar o material original:
- CASTROS_V4_BATCH01_APPROVED_6b578c5.bundle
- CASTROS_V4_BATCH01_APPROVED_SOURCE_6b578c5.zip
- CASTROS_V4_MASTER_HANDOFF_FINAL_WITH_WIREFRAMES_2026-09-30.zip
- CASTROS_V4_SCENE_NAVIGATION_V2_PACKAGE.zip

O bundle 6b578c5 não substitui o source de 1f7921f e as alterações posteriores.

## 6. Primeiros passos do colega

1. Inspecionar a pasta local antes de alterar branches ou fazer pull.
2. Executar comandos de leitura:

       git status --short --untracked-files=all
       git branch -avv
       git log --all --oneline -30
       git stash list
       git reflog --all -30
       git remote -v

3. Procurar 1f7921f e a branch feat/castros-v4-redesign; comparar os ficheiros reais com os snapshots, incluindo assets e testes.
4. Preservar integralmente a cópia recuperada e os artefactos antes de qualquer limpeza, reset ou troca de baseline.
5. Se o source exato estiver ausente, pedir a cópia completa/bundle correto. Não reconstruir a versão aprovada a partir de screenshots, documentação ou memória.
6. Auditar segredos e ficheiros temporários; versionar source, assets aprovados, documentos e evidências relevantes. Não versionar passwords, .env reais, node_modules, browser profiles ou caches.
7. Commitar/publicar a versão V4 real numa branch de trabalho e registar o hash exato no handoff.
8. Executar novamente o QA e atualizar este documento com evidência atual.
9. Parar para revisão visual humana antes de dar o trabalho como aprovado. Não fazer merge ou deploy sem instrução explícita.

Não substituir este diagnóstico por "tudo salvo" enquanto o source local não tiver sido recuperado e verificado.

## 7. Contratos a preservar

- Não criar outro sistema de homepage nem novas layers globais de override.
- Não alterar backend/APIs, rotas ou slugs para corrigir copy visível.
- Treino Corporativo Personalizado é copy pública; treinamento-corporativo-personalizado pode continuar como slug interno.
- Usar apenas os assets aprovados C01/F02/E03; não usar a pasta de rejeitados nem alterar a identidade de Elizabeth.
- Não inventar conteúdo, clientes, testemunhos, métricas, disponibilidade ou urgência.
- Formação continua dinâmica em HTML/dados reais; F02-B/F02-BM não voltam a ser a interface principal da cena.
- Imagens completas, sem crop destrutivo; preservar rosto, mãos, quadro, letreiro, porta e hotspots.
- H05 mantém três cards, não uma lista editorial.
- Hotspots espaciais em todos os viewports, com nomes acessíveis e hit targets adequados.
- Preservar skip link, teclado, foco, Escape/close/focus restoration, reduced motion e state machine.
- Não integrar PR #62 inteiro.
- Não tratar o commit de documentação deste handoff como o commit do V4 que continua em falta.

