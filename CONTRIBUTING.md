# Contribuindo — Clube de Astronomia

Obrigado por querer contribuir! 🙌  
Este documento explica como enviar issues, abrir pull requests e trabalhar localmente no site (Eleventy). Siga os passos abaixo para facilitar a revisão e acelerar a integração das suas contribuições.

---

## Sumário rápido

- ✅ **Boas-vindas**: qualquer contribuição é bem-vinda (conteúdo, correções, design, acessibilidade).
- 🧭 **Onde colocar**: copie este arquivo para a raiz do repositório como `CONTRIBUTING.md`.
- 🛠️ **Primeiros passos**: veja a seção _Rodando localmente_.

---

## Regras de convivência

Trate todas as pessoas com respeito. Comentários hostis, ataques pessoais ou discriminação não serão tolerados.

---

## Como contribuir (visão geral)

Você pode contribuir de várias formas:

- Reportar bugs (issues claras e reproduzíveis).
- Sugerir melhorias ou ideias.
- Corrigir textos e ortografia.
- Adicionar/editar perfis de participantes.
- Melhorar estilos CSS/JS.
- Submeter posts para o blog.

Fluxo recomendado:

1. Fork do repositório.
2. Crie uma branch com nome descritivo.
3. Faça commits pequenos e claros.
4. Abra um Pull Request (`PR`) apontando para `main` (ou branch principal).
5. Aguarde revisão; responda comentários e faça ajustes.

---

## Rodando o projeto localmente (Eleventy)

Assumimos que você tem Node.js instalado.

```bash
# clonar (ou usar fork)
git clone https://github.com/ifrsrolante-astronomia/site
cd site

# instalar dependências
npm install

# rodar em modo desenvolvimento (live server)
npm run dev
# ou, se não houver script específico:
npx @11ty/eleventy --serve
```

Para gerar o build de produção:

```bash
npm run build
# ou
npx @11ty/eleventy
```

Se algo falhar, poste o erro completo na issue — facilita muito a ajuda.

---

## Padrões de branch e commits

**Nome de branch sugerido**

- `feat/nome-curto` — nova funcionalidade
- `fix/descricao-curta` — correção
- `docs/melhora-readme` — documentação
- `style/css-ux` — alteração visual sem lógica

**Mensagens de commit**
Adote mensagens curtas e descritivas. Sugestão (Conventional Commits simplificado):

```
feat: adicionar campo years no participante João
fix: corrigir layout do card no mobile
docs: atualizar contributing com instruções de imagem
```

Use o corpo do commit para explicar o porquê quando necessário.

---

## Como submeter conteúdo — participantes

Os participantes são arquivos Markdown com front matter. Exemplo de arquivo de participante (`src/participantes/joao.md`):

```md
---
layout: participant.njk
title: "João Silva"
role: "Observador"
photo: "/assets/img/participants/joao.jpg"
instagram: "joao"
linkedin: "joao"
years: "2023-Presente"
---

Breve biografia em Markdown. Pode conter links, listas e imagens.
```

Recomendações:

- Fotos: salve em `/img/participants/` (ou pasta que o projeto usa).
- Nomes de arquivo: use `kebab-case` (`joao-silva.md`).
- Sempre inclua `alt` nas imagens (ex.: `alt="João Silva, perfil"`).
- Evite HTML inline; prefira Markdown.

---

## Posts do blog

Se quiser enviar um post, crie um arquivo em `src/blog/` com front matter semelhante:

```md
---
title: "Título do post"
date: 2025-08-25
author: "Seu Nome"
layout: base.njk
---

Conteúdo em Markdown...
```

Padrões:

- Data no formato ISO (`YYYY-MM-DD`).
- Título claro e resumo no início, se possível.
- Se incluir imagens, otimize tamanho (>= 800px largura para destaque; use compressão).

---

## Formatação e qualidade

- Use ortografia correta e linguagem clara.
- Preferência por português brasileiro, se o projeto for majoritariamente em PT-BR.
- Acessibilidade: sempre alt para imagens; contrastes razoáveis.
- Código: siga o estilo existente — se for CSS, mantenha variáveis `--` já usadas; se for JS, evite novas dependências sem justificativa.

---

## Testes rápidos antes do PR

Execute localmente e verifique:

- `npm run dev` abre sem erros.
- Links internos funcionam (páginas de participantes e /sobre/).
- Layout em mobile e desktop (cheque visualmente).
- Não introduza console errors no browser.

---

## Checklist para Pull Request

Ao abrir um PR, inclua:

- [ ] Descrição curta do que foi feito.
- [ ] Comandos para reproduzir localmente (se aplicável).
- [ ] Screenshots (se mudou layout/design).
- [ ] Arquivos adicionados/alterados listados.
- [ ] Confirmação de que `npm run dev` roda sem erro.

Exemplo de descrição:

> **O que**: Adiciona perfil do João.
> **Por que**: Novo membro do clube.
> **Como testar**: `npm run dev` -> acessar `/participantes/joao-silva/`.

---

## Issues — como abrir uma boa issue

Ao abrir um issue inclua:

- Título descritivo.
- Passos para reproduzir (se bug).
- Resultado esperado vs. resultado atual.
- Versão do Node / comandos rodados (se for um erro de build).
- Link para screenshot ou console output (se relevante).

---

## Segurança e dados pessoais

- Não inclua informações sensíveis (senhas, tokens).
- Se alguém pedir remoção de dados pessoais, abra uma issue marcada como `privacy` ou fale diretamente com os mantenedores.

---

## Arquivos úteis (templates)

Você pode adicionar estes arquivos no repositório para facilitar:

### `.github/PULL_REQUEST_TEMPLATE.md` (exemplo)

```md
## Descrição

<!-- O que foi feito e por quê -->

## Como testar

1. rodar `npm install && npm run dev`
2. acessar...

## Checklist

- [ ] Build roda sem erros
- [ ] Documentação atualizada (se aplicável)
- [ ] Screenshots anexados (se UI)
```

### `.github/ISSUE_TEMPLATE/bug.md` (exemplo)

```md
name: Bug report
about: Reporta um bug no site
title: '[BUG] '
labels: bug

---

**Passos para reproduzir**

1. ...
   **Resultado esperado**
   **Resultado atual**
   **Ambiente**

- Node: ...
```

---

## Precisa de ajuda?

Se ficou em dúvida ou prefere que a gente faça a PR pra você, abra uma issue com o rótulo `help wanted` e descreva o que deseja contribuir. Podemos orientar passo a passo.

---

## Últimas observações

- Pequenas correções (typos, ajustes simples) podem ser aceitas com mais rapidez.
- Para mudanças grandes (estrutura, temas), abra uma issue antes para discutirmos a melhor abordagem.

Obrigado por colaborar com o Clube de Astronomia — sua contribuição faz o projeto melhor! 🌙✨x
