# CASTRO’S V4 — MASTER HANDOFF DE CONTINUIDADE

**Atualizado:** 2026-10-17 · Africa/Johannesburg  
**Repositório:** https://github.com/rightware-corporations/castro-service  
**Branch de continuidade documental:** `handoff/castros-v4-2026-10-17`  
**Estado:** baseline funcional remota preservada; recuperação/publicação do source V4 ainda pendente.  
**Destinatário:** colega/engenheiro que vai continuar o projeto.

## 0. Ler primeiro — não confundir documentação com source recuperado

Este é o documento principal de continuidade. [README.md](README.md) conserva a auditoria de recuperação anterior. Os documentos antigos de `docs/` continuam úteis para arquitetura e história, mas os seus antigos HEADs/PRs ativos não são o estado atual.

Esta branch contém:
1. A baseline funcional do PR #66, até `d646f1c9f2b9cb4df81cdb8d512e2db8a9777c28`.
2. O handoff de recuperação `e0630743facaade99f075ccd51a608cdc502e98e`.
3. Os commits documentais que publicam este master e atualizam o índice.

**Não contém a implementação V4 posterior, Scene Navigation v2 ou o polish final descritos no histórico deste chat.** Não é uma cópia da versão visual aprovada e não deve ser apresentada como tal.

A última validação remota voltou a confirmar:
- `main` permanece em `7f0d79ade32e500f3d2ee122d1a94ec9383d2c4a`.
- PR #66 continua draft no head `d646f1c9f2b9cb4df81cdb8d512e2db8a9777c28`.
- GitHub não encontra os commits `6b578c5` e `1f7921f`.
- Na árvore desta branch, antes de adicionar este master, não existem `SceneMorph`, `sceneIntent`, `useSceneNavigation`, `PracticeInteractions`, `v4-approved` ou o relatório final de polish.
- A branch V4 `feat/castros-v4-redesign` não estava publicada na auditoria de branches.
- O terminal deste chat falha antes de executar comandos: `setup refresh had errors`. O filesystem local não foi recuperado nem inspecionado com sucesso.

A ausência remota não prova perda dos ficheiros locais. Também não permite declarar que esses ficheiros estão guardados no GitHub.

## 1. Recuperar a branch e confirmar a identidade da cópia

Clonar para uma pasta nova evita sobrepor alterações de outro checkout:

```powershell
git clone --branch handoff/castros-v4-2026-10-17 https://github.com/rightware-corporations/castro-service.git castros-handoff
cd castros-handoff
git status --short --untracked-files=all
git branch --show-current
git log -12 --oneline
git rev-parse HEAD
git remote -v
```

A branch deve ser `handoff/castros-v4-2026-10-17`. O HEAD final inclui os commits de documentação posteriores a `e063074`; consultar o GitHub/log em vez de fixar o HEAD nesse commit antigo.

**Não fazer reset, clean, pull com sobrescrita ou troca de baseline sobre a cópia local que possa conter o V4.**

## 2. Commits mais recentes confirmados

Datas da tabela em Africa/Johannesburg (UTC+02:00). Ordem: mais recente primeiro. A tabela fotografa a branch antes do commit que introduz este documento; o próprio commit do master e o índice aparecem no `git log` depois desta publicação.

| Commit | Data/hora local | Alteração |
| --- | --- | --- |
| [`e063074`](https://github.com/rightware-corporations/castro-service/commit/e0630743facaade99f075ccd51a608cdc502e98e) | 2026-10-17 01:49 | docs(handoff): preserve remote baseline and document V4 recovery gaps |
| [`d646f1c`](https://github.com/rightware-corporations/castro-service/commit/d646f1c9f2b9cb4df81cdb8d512e2db8a9777c28) | 2026-09-23 18:19 | Revalidate resource and slot on booking details and review entry |
| [`5a74d13`](https://github.com/rightware-corporations/castro-service/commit/5a74d130ddf6015aaf62c92a394d023547f0481e) | 2026-09-23 18:05 | Revalidate selected booking slots before continuing |
| [`99a2e4f`](https://github.com/rightware-corporations/castro-service/commit/99a2e4f0a778cd34045c340f31a590f43a6eb571) | 2026-09-23 06:47 | Show booking confirmation only from verified lookup state |
| [`57a4c72`](https://github.com/rightware-corporations/castro-service/commit/57a4c72e5f572b9812e2b0c498f878e216f42038) | 2026-09-23 06:38 | Stabilize public context, navigation and deferred space routes |
| [`f254219`](https://github.com/rightware-corporations/castro-service/commit/f2542190ceceb0b5f1b5579d9cc305c70bbe3f7f) | 2026-09-16 22:36 | Align panorama points with image crop and preserve explorer focus |
| [`3ca4803`](https://github.com/rightware-corporations/castro-service/commit/3ca4803bd48c140bbc8a8a252eb91bfa8e11e08c) | 2026-09-16 22:24 | Add space focus and recover from unavailable real media |
| [`bf78f61`](https://github.com/rightware-corporations/castro-service/commit/bf78f6147ff802ec796df3c5010bbc8f0c5f93e4) | 2026-09-16 15:53 | Add published catalog focus and accessible training registration |
| [`deebe51`](https://github.com/rightware-corporations/castro-service/commit/deebe51e0d1fd091e44f88379568ee00c86cf48c) | 2026-09-16 11:42 | Implement continuous Home practice and closing states H06–H12 |
| [`7cfc2e1`](https://github.com/rightware-corporations/castro-service/commit/7cfc2e1e958be895a14778006fabfb7a407e3cb7) | 2026-09-15 23:34 | Implement public foundations and continuous Home entry |
| [`7f0d79a`](https://github.com/rightware-corporations/castro-service/commit/7f0d79ade32e500f3d2ee122d1a94ec9383d2c4a) | 2026-09-09 17:59 | Merge pull request #65 from rightware-corporations/rightware-corporations-patch-3 |

### O que representam

- `e063074`: documentação/auditoria de recuperação. Não é um commit do código V4.
- `d646f1c`: revalida recurso e slot em entrada direta nos detalhes/revisão da reserva.
- `5a74d13`: exige revalidação do slot selecionado antes de continuar.
- `99a2e4f`: confirmação de reserva depende de lookup real e validado.
- `57a4c72`: contexto público, navegação e rotas diferidas de Espaços.
- `f254219` / `3ca4803`: coordenadas de panorama, foco e falhas de media em Espaços.
- `bf78f61`: catálogo publicado e inscrição acessível em Formação.
- `deebe51` / `7cfc2e1`: implementação Home/contrato público anterior ao novo redesign V4.
- `7f0d79a`: atual main, merge do PR #65; não contém o trabalho posterior do #66.

O facto de a baseline antiga já ter estados H06–H12 não significa que seja o redesign V4, os seus assets ou o controlador v2.

## 3. Baselines V4 históricas ainda por recuperar

| Referência | Significado no trabalho anterior | Presença remota nesta verificação |
| --- | --- | --- |
| `6b578c5` | `refine(home): approve H05 responsive practice layout` | Não encontrada |
| `1f7921f8f9fe9c6969f10b42801d09c904b28b70` | `feat(home): build V4 H05 to H06 consulting chapter` | Não encontrada |
| `feat/castros-v4-redesign` | Branch local V4 aprovada no trabalho anterior | Não publicada na auditoria |

No último estado local historicamente verificado, o HEAD era `1f7921f` e havia alterações posteriores ainda sem commit. Não foi possível confirmar o estado atual desse checkout.

**Não usar `8fed4a9` como baseline. Não reconstruir a versão aprovada a partir de screenshots, memória ou descrição.**

## 4. Auditoria remota e PRs que o colega precisa conhecer

Antes de criar a branch deste handoff, foram comparadas 68 branches com main:
- 60 já contidas no histórico de main;
- sete com commits fora de main;
- a própria main.

A branch documental agora acrescentada altera essa contagem; o número acima é a fotografia da auditoria original, não um contador permanente.

| PR / branch | Estado auditado | Ação correta |
| --- | --- | --- |
| [#66](https://github.com/rightware-corporations/castro-service/pull/66) · `feat/castros-contract-v1-foundations` | Draft; +9 / -0 contra main; CI 3/3 verde | Preservar contratos funcionais. Não confundir com V4 nem marcar como aceite visualmente. |
| [#62](https://github.com/rightware-corporations/castro-service/pull/62) · `feat/castros-v3-operational-spatial-refinement` | Aberto; +37 / -4; CI 3/3 verde | Auditar apenas funcionalidade única que falte em main/#66. Não integrar inteiro. |
| [#11](https://github.com/rightware-corporations/castro-service/pull/11) · `feature/authentication-hardening` | Aberto; +5 / -392; conflitos | Auditoria de segurança própria antes de descartar ou portar alterações. |
| [#13](https://github.com/rightware-corporations/castro-service/pull/13) · `feature/access-security` | Aberto; +6 / -386; conflitos | Auditar passwords, autorização e revogação de sessões; não fazer merge cego. |
| [#63](https://github.com/rightware-corporations/castro-service/pull/63) · `rightware-corporations-patch-2` | Aberto; +1 / -4; conflitos | `images/image1` é uma quebra de linha, não uma imagem. Em main, `public/images` é também um ficheiro, não uma pasta. Não usar como media. |
| `feature/training-system-completion` | +1 / -167; PR #39 já merged | Há alteração posterior de tipografia para avaliar; não restaurar UI antiga automaticamente. |
| `fix/experience-2-visible-home-change` | +2 / -27; PR #60 fechado sem merge | CSS visual antigo; não reintegrar no V4 automaticamente. |

O `SessionRevocationService` e o teste `UserAccountSessionSerializationTest` propostos nos PRs antigos não existem nos paths correspondentes de main. Isto exige revisão funcional; não constitui uma auditoria completa de toda a arquitetura de segurança.

Não foram fechados PRs, apagadas branches, resolvidos conflitos ou integradas funcionalidades nesta entrega documental.

## 5. CI: evidência remota vs QA histórica

### CI remoto efetivamente confirmado

- Baseline #66, head `d646f1c`: Frontend + Backend + PostgreSQL passaram no [run 35887959864](https://github.com/rightware-corporations/castro-service/actions/runs/35887959864).
- #62, head `98d98d3`: três gates passaram no [run 34782576365](https://github.com/rightware-corporations/castro-service/actions/runs/34782576365).
- Main `7f0d79a`: três gates passaram no [run 34373865421](https://github.com/rightware-corporations/castro-service/actions/runs/34373865421).
- O run mais recente de #66 não disponibiliza artifacts.
- Não foram encontradas tags/releases na auditoria.

**Esses resultados pertencem aos SHAs acima. Não validam o source V4 em falta nem estes novos commits documentais. Não foram reexecutados os testes da aplicação para editar este handoff.**

### QA local histórica do polish, apenas registada no chat

A passagem anterior registou:
- 47 ficheiros / 226 testes passaram.
- TypeScript, lint e production build passaram.
- Chrome nos cinco tamanhos: 1440x900, 1024x768, 768x1024, 390x844, 320x568.
- Sete cenas estáveis sem scroll horizontal: `document.documentElement.scrollWidth === document.documentElement.clientWidth`.
- Dialogs centrados, teclado, Tab/Shift+Tab, Escape, close/backdrop e restauração de foco.
- Primeiro intent mantém a cena; segundo independente confirma; reversão, expiração, inércia, teclado e swipe verificados.
- Reduced motion e zoom nativo Chrome 200%.
- Deep-links dos quatro serviços, /formacao e explorador real.
- Onze PNG aprovados com hashes preservados.
- Última galeria: 127 capturas e três vídeos.

Os logs, capturas e o source respetivo precisam de ser recuperados para inspeção independente. Não afirmar que esta QA passou sobre o source desta branch.

Limitações históricas:
- Catálogo de cursos vazio no preview; estado vazio verdadeiro, sem cursos ou disponibilidade inventados.
- Warning em CourseSettingsPage.tsx:82, advisory de bundle >500 kB e favicon 404.
- Sem validação física de trackpad, Safari/iOS ou hardware mobile.
- Sem aceitação visual final confirmada.

## 6. Estado de produto e arquitetura a preservar

Monorepo:
- `frontend/`: React + TypeScript + Vite.
- `backend/`: Spring Boot + PostgreSQL/Flyway.
- `infra/`: infraestrutura.
- `docs/`: arquitetura e histórico.
- `handoff/`: esta continuidade e auditoria.

Quatro experiências estabelecidas:
1. Cliente público, sem login interno obrigatório.
2. Secretária / Operations em /app.
3. CEO / Owner em /owner.
4. RIGHTWARE Super Admin em /platform.

Não inventar uma quinta persona "Gestor". Preservar isolamento de organizações, autenticação de sessão/CSRF e distinção entre tenant e plataforma.

Contratos funcionais críticos:
- API tipada /api/v1 e backend como autoridade dos dados/availability.
- Booking exige recurso publicado e capacidade de reserva, duração e slot exato disponíveis; loading/refetch/error bloqueiam progressão insegura.
- Entrada direta em detalhes/revisão revalida recurso e slot sem perder dados do cliente.
- Confirmação exige lookup real; referências desconhecidas/erros não simulam sucesso.
- Retry preserva idempotency key; lookup não cria reserva.
- Formação usa dados/sessões reais; inscrição não equivale a reserva exclusiva do motor SERVICE/SPACE.
- Contexto de serviço/curso/espaço e seleção devem sobreviver à navegação.
- Não inventar preços, clientes, testemunhos, estatísticas ou disponibilidade.

## 7. Contrato visual V4 e última autorização do proprietário

Autoridade: instruções humanas mais recentes, pacote mestre V4 e delta Scene Navigation v2. Para a composição final, procurar:
- `09_FINAL_IMPLEMENTATION_WIREFRAMES/FINAL_IMPLEMENTATION_WIREFRAMES.drawio`;
- `03_RESPONSIVE_SYSTEM/HOME_MASTER_WITH_RESPONSIVE_SYSTEM.drawio`;
- board H03/H04/H05 aprovado;
- Master UX, Responsive Translation System, Interaction Contract e Asset Manifest dos pacotes originais.

O último pedido de implementação foi polish visual, ocupação do frame e legibilidade narrativa; o último estado terminou para revisão humana. A publicação do handoff não equivale a aprovação visual.

### Sequência e interações

- Um sistema de homepage e um controlador de cenas; não criar um sistema paralelo.
- Cenas estáveis: H03, H05, H06, H08, H10, H11, H12.
- H04/H07/H09 são transferências, não destinos de repouso.
- Primeiro scroll/swipe/key intent prepara; segundo intent independente confirma.
- Preservar exit/reentry, teclado, foco, skip link e reduced motion.
- H03: Elizabeth central/bem enquadrada, menos zoom, texto legível e mãos/rosto íntegros.
- H04: origem óbvia no símbolo real CASTRO’S, alongamento antes de separar; mesma media continua até os três cards. Último timing registado: 2,8 segundos.
- H05: três authored media cards — Consultoria / Formação / Espaços. O último pedido autorizou melhorar fitting/ocupação sem crop destrutivo.
- H06: quatro hotspots textless em todos os viewports. Primeiro clique abre dialog contextual central; CTA leva ao serviço real relevante.
- H08: usar cena F02 aprovada. Cursos em destaque abre dialog central com HTML/dados reais; segundo hotspot navega diretamente para /formacao. Não regressar ao board-overlay nem usar F02-B/F02-BM como interface principal.
- H10: porta como hotspot principal; primeiro clique abre dialog; "Explorar o espaço" usa rota real /espacos/<slug>/explorar. Último polish registou avanço visual de 1 segundo antes da rota, Escape cancela; reduced motion navega sem dolly.
- Elizabeth não aparece na cena de Espaços.
- H11: philosophy/proof primeiro, sem inventar prova social. O pedido mais recente autorizou foto original/aprovada da fundadora junto ao texto.
- H12: minimal, statement forte e CTA principal /contacto.

### Media e fitting

Apenas assets aprovados:
- Consultoria: C01-D/T/M e C01-S como guia de safe zones, não superfície decorativa inventada.
- Formação: F02-D/T/M e F02-B/BM disponíveis segundo contrato; clean boards não são a interface principal da cena v2.
- Espaços: E03-D/T/M.
- Retrato original já existente: IMG_3376.JPG.jpeg.
- Símbolo/logo original já fornecido.

Não usar `99_ARCHIVE_REJECTED_NOT_FOR_IMPLEMENTATION/`. Não gerar pessoas de substituição nem alterar a identidade de Elizabeth.

Fotos completas, sem crop de rosto/mãos/quadro/letreiro/porta. A ocupação deve usar melhor o frame abaixo da navbar. O último polish registou foreground com contain e luz difusa derivada da própria imagem nas bordas incompatíveis; requer revisão visual, não aceitação presumida. O zoom temporário de entrada em Espaços é um efeito de navegação, não um novo crop estático do asset.

Copy pública: "Treino Corporativo Personalizado"; o slug `treinamento-corporativo-personalizado` pode permanecer. Não alterar rotas/APIs/slugs para corrigir texto visível.

## 8. Recuperação do source e artefactos — prioridade P0

Pasta indicada pelo proprietário:
`C:\Neneco\codes\codes1\castro-service-main`

Workspace antigo registado:
`C:\Users\administrator\Documents\Codex\2026-09-15\figma-plugin-figma-openai-curated-remote`

Dentro do workspace antigo procurar:
- `work/castro-service/`, incluindo .git e ficheiros não rastreados.
- `outputs/v4-visual-polish/`.
- `outputs/CASTROS_V4_VISUAL_POLISH_REVIEW.zip`.
- `outputs/v4-scene-v2/`.
- `outputs/CASTROS_V4_SCENE_NAVIGATION_V2_VISUAL_REVIEW.zip`.
- `docs/V4_VISUAL_POLISH_REVIEW.md`, `docs/V4_SCENE_NAVIGATION_V2_REVIEW.md` e `docs/V4_MASTER_FINAL_REVIEW.md` no checkout anterior.

Esses paths são pistas históricas, não ficheiros atualmente confirmados. Não confundir URLs localhost:5173/5176 com backup público ou source publicado.

Pacotes originais a procurar:
- CASTROS_V4_BATCH01_APPROVED_6b578c5.bundle.
- CASTROS_V4_BATCH01_APPROVED_SOURCE_6b578c5.zip.
- CASTROS_V4_MASTER_HANDOFF_FINAL_WITH_WIREFRAMES_2026-09-30.zip.
- CASTROS_V4_SCENE_NAVIGATION_V2_PACKAGE.zip.

### Inspeção local, sem destruir dados

```powershell
git -C "C:\Neneco\codes\codes1\castro-service-main" status --short --untracked-files=all
git -C "C:\Neneco\codes\codes1\castro-service-main" branch -avv
git -C "C:\Neneco\codes\codes1\castro-service-main" log --all --oneline -40
git -C "C:\Neneco\codes\codes1\castro-service-main" stash list
git -C "C:\Neneco\codes\codes1\castro-service-main" reflog --all -40
git -C "C:\Neneco\codes\codes1\castro-service-main" remote -v
```

Verificar alterações em:
- HomeEntry.tsx / home-entry.css / HomePublic.tsx / HomeSpaces.tsx.
- SceneMorph.tsx / PracticeInteractions.tsx / useSceneNavigation.ts / sceneIntent.ts.
- Testes Home, Spaces, intents, qualidade de dados e catálogo.
- publicCopy.ts / ServicesPublic.tsx / Layouts.tsx.
- frontend/public/v4-approved/ e retrato/logo reais.
- Docs, source-snapshot, patches, logs, manifestos e captures dos dois ciclos.

Um source-snapshot parcial não é prova de repositório completo. Preservar a cópia original, incluindo untracked/stashes, antes de restaurar ou integrar qualquer coisa. O bundle 6b não contém automaticamente 1f7921f nem os ajustes posteriores.

## 9. Arranque e QA depois de confirmar o source correto

Ler primeiro README.md, AGENTS.md e manifests reais do checkout. Comandos padrão do repositório:

```powershell
cd frontend
npm ci
npm run dev
```

O modo de preview/mock e o URL do backend devem seguir a configuração real e os exemplos .env existentes. Não copiar segredos para documentação. Um preview com dados mock não prova funcionamento no backend real.

Checks frontend:

```powershell
npm run typecheck
npm run lint
npm run test
npm run build
```

Backend, em terminal próprio:

```powershell
cd backend
.\mvnw.cmd clean verify
```

Confirmar disponibilidade/configuração do PostgreSQL antes dos testes integrados. Não alterar a configuração da aplicação para contornar limitações de uma máquina de desenvolvimento.

O esbuild WASM preload usado no sandbox anterior era um auxílio local fora do projeto; não o tratar como dependência obrigatória do colega.

QA visual:
- 1440x900 / 1024x768 / 768x1024 / 390x844 / 320x568.
- H03/H05/H06/H08/H10/H11/H12 estáveis.
- Momentos intermédios H04/H07/H09 e entrada em Espaços.
- Redução de dead space, hero íntegro, logo legível, três cards fortes, porta/quadro/letreiro preservados.
- Sem horizontal scroll; medir scrollWidth === clientWidth.
- Hotspots, dialogs, Escape/close, Tab/Shift+Tab e restauração do foco.
- Primeiro intent não muda de frame; segundo independente confirma.
- Reduced motion, zoom 200%, deep-links e estados loading/error/empty.
- Hashes dos assets aprovados; nenhum asset rejeitado importado.
- Browser console; dados dinâmicos de Formação; distinção preview vs backend.
- Produzir capturas e parar para revisão humana.

A execução anterior separou testes, gravação e input de scroll após timeouts sob carga. Não modificar o contrato de duas intenções só para fazer passar um teste cuja gravação atrasa os eventos.

## 10. Backlog imediato e critérios de passagem

### P0 — Guardar a versão real
- [ ] Confirmar checkout local e HEADs/stashes/untracked.
- [ ] Encontrar source exato 1f7921f + alterações posteriores, ou cópia completa equivalente verificável.
- [ ] Preservar cópia de recuperação antes de qualquer troca de branch.
- [ ] Publicar source, assets aprovados e evidências relevantes numa branch de trabalho.
- [ ] Confirmar SHAs no remoto e atualizar este master.

### P1 — Validar a continuidade
- [ ] Comparar contratos com o #66 sem descartar trabalho V4.
- [ ] Executar QA atual e disponibilizar os artefactos.
- [ ] Revisão visual humana do último polish.
- [ ] Auditar funcionalidade única do #62 e pendências #11/#13, sem merges cegos.
- [ ] Decidir o destino do PR vazio #63 e branches antigas por instrução do proprietário.

### P2 — Entrega ao colega
- [ ] Instruções de arranque verificadas numa cópia nova.
- [ ] Lista exata de commits, ficheiros e limitações.
- [ ] Source recuperável pelo colega sem depender de paths locais do autor.
- [ ] CI verde nos SHAs realmente entregues.
- [ ] Nenhuma promessa de "tudo salvo" enquanto P0 estiver incompleto.

## 11. Atualizar este master a cada passagem

Registar sempre:
- Data/hora e timezone.
- Repo, branch, HEAD completo, commits novos e PRs.
- O que foi realmente alterado e onde.
- Testes executados, resultados e links para logs/captures.
- O que foi apenas histórico/referência.
- Bloqueios, dados/media em falta e próximo passo verificável.
- Estado de revisão humana e autorizações.

Não colocar passwords, tokens, .env reais, browser profiles, caches ou node_modules no Git. Não apagar CSS legado sem provar ausência de consumidores. Não fazer force-push ou merge/deploy como parte de uma simples passagem de handoff.

## 12. Prompt curto para a próxima pessoa/agente

> Abre rightware-corporations/castro-service na branch handoff/castros-v4-2026-10-17 e lê handoff/MASTER_CONTINUATION.md e handoff/README.md. Confirma o HEAD real. A branch preserva #66 e documentação, mas o source V4 posterior ainda precisa de recuperação local. Não reconstruas a versão aprovada por screenshots ou memória, não uses 8fed4a9 e não integres #62 inteiro. Primeiro localiza/verifica 1f7921f, os uncommitted posteriores, assets e artefactos; preserva a cópia e publica o source real. Depois executa QA atual, atualiza este master e para para revisão visual humana. Não declarar a versão final recuperada, testes atuais verdes ou tudo salvo sem evidência.
