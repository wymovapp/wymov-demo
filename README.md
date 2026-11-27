# WYMov — demo do app (apresentação)

Apresentação interativa do app, em **site estático**. É o que se mostra numa
reunião e se manda para a pessoa rever depois.

## O que é, e o que não é

- Uma página (`index.html`) com CSS e JavaScript embutidos, mais 10 capturas
  de tela em JPEG. **1,2 MB no total.**
- **Não** tem build, framework, Node, backend, banco, variável de ambiente,
  service worker nem chamada de API. Nenhuma requisição sai da página.
- **Não** é o app: as telas são capturas do build de preview do Flutter, com
  áreas clicáveis por cima. Clicar troca a imagem — parece o app, mas é
  imagem com JavaScript.
- Abre offline: dois cliques no `index.html` e funciona.

## Como publicar (Cloudflare Pages)

Projeto novo, separado da API e do painel.

| Campo | Valor |
|---|---|
| Build command | *(vazio)* |
| Build output directory | `/` (a raiz deste repositório) |
| Framework preset | None |

Ou, sem conectar repositório, pelo upload direto: **Workers & Pages → Create →
Pages → Upload assets** e arrastar os arquivos.

**O repositório pode (e deve) ser privado** — o Cloudflare Pages conecta em
repositório privado sem problema.

## Decisões que estão dentro do arquivo

- `robots.txt` e `_headers` com `noindex`: o endereço é para quem recebe o
  link, não para buscador.
- Sem domínio próprio por enquanto: `*.pages.dev` basta. `wymov.app` ainda não
  existe (sem registro de DNS em 27/11/2026).
- Telas em JPEG, não PNG: 3,9 MB → 1,2 MB, que é o que decide se abre rápido
  no 4G.

## Atualizar

Quem mantém o conteúdo é o Augusto. Chegando uma versão nova, é substituir o
`index.html` e a pasta `telas/` — não há passo de build.
