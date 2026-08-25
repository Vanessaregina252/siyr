# Versão 5 — foto local, novos serviços e contato

- A foto profissional agora usa `assets/vanessa-regina.webp`, sem depender de hospedagem externa.
- O Instagram foi removido do contato.
- O telefone `(21) 97386-8126` foi incluído no botão de ligação e no rodapé.
- Foram incluídos os serviços do documento de alterações: cálculos revisionais/judiciais, benefícios previdenciários, Lei do Superendividamento, MEI, abertura/regularização de empresas e Imposto de Renda.
- Foi incluído o botão de avaliação no Google usando o segundo link fornecido no documento de alterações.

---

# Versão 3 — correção de imagens no Vercel

Nesta versão, a foto profissional usa diretamente o link hospedado informado e os logotipos visíveis foram incorporados dentro do próprio `index.html` como imagens `data:`. Isso evita erro 404 caso a pasta `assets/` não seja enviada ao GitHub/Vercel.

**Para atualizar um deploy existente:** substitua o `index.html` pelo desta versão e faça commit/push. Como o CSS foi versionado como `styles.css?v=3.0.0`, mantenha também o `styles.css` atual na raiz.

---

# Vanessa Contabilidade — Site institucional

Site estático, responsivo e pronto para ser versionado no GitHub e publicado na Vercel.

## Estrutura

- `index.html` — conteúdo e SEO
- `styles.css` — identidade visual, responsividade e acessibilidade
- `script.js` — menu mobile, animações e ativação dos canais de contato
- `site.config.js` — telefone/WhatsApp/e-mail (configure antes de publicar)
- `assets/` — logotipo, sublogo, foto profissional, favicon e imagem social
- `vercel.json` — configuração simples de cache para a Vercel

## 1. Configurar os contatos

Abra `site.config.js` e preencha:

```js
window.SITE_CONFIG = {
  phone: "5521973868126",
  whatsapp: "",
  email: ""
};
```

Telefone e WhatsApp, quando preenchidos, devem conter apenas números, com DDI + DDD + número.

## 2. Testar localmente

Na pasta do projeto:

```bash
python -m http.server 8000
```

Depois acesse `http://localhost:8000`.

## 3. Publicar no GitHub

Crie um repositório vazio e, dentro da pasta do projeto:

```bash
git init
git add .
git commit -m "Site Vanessa Contabilidade"
git branch -M main
git remote add origin URL_DO_REPOSITORIO
git push -u origin main
```

## 4. Vincular à Vercel

1. Na Vercel, escolha **Add New > Project**.
2. Importe o repositório do GitHub.
3. Framework Preset: **Other**.
4. Build Command: deixe vazio.
5. Output Directory: deixe vazio.
6. Clique em **Deploy**.

A cada novo `git push`, a Vercel fará um novo deploy automaticamente.

## Identidade visual

A paleta fornecida foi aplicada no site:

- Verde oliva: `#555B3B`
- Verde sálvia: `#C1C8B8`
- Rosa suave: `#E0BDBB`

A referência de tipografia do material utiliza Luxerie. Como o arquivo da fonte não foi fornecido, o site usa **Cormorant Garamond** como serifada de apoio e **DM Sans** para textos, mantendo o estilo elegante e profissional sem redistribuir fontes licenciadas.

## Observação de conteúdo

O texto foi organizado a partir do protótipo fornecido, preservando serviços, posicionamento, credenciais, atuação presencial/online e seção de credenciamento hospitalar/militar. Nenhum telefone, e-mail ou rede social foi inventado; esses dados devem ser preenchidos em `site.config.js`.

## Correção de layout — v2

Esta versão corrige o hero em telas desktop/intermediárias:

- título com escala responsiva mais controlada;
- colunas com `minmax(0, ...)` para evitar compressão inesperada;
- breakpoint do hero ajustado para empilhar antes de a coluna ficar estreita;
- foto com fallback JPG caso WebP não carregue;
- marca do cabeçalho mais legível;
- proteção contra overflow horizontal;
- query de versão em CSS/JS para reduzir problemas de cache após o redeploy.

Para atualizar um projeto já publicado, substitua **todos os arquivos do repositório** pelos desta pasta e faça um novo commit/push. A Vercel fará o deploy automaticamente se o repositório estiver conectado.


## Versão 4 — ajuste da foto no hero
A foto principal foi redimensionada para um cartão 4:5 mais compacto, sem o recorte alto em formato de arco. O objetivo é preservar a proporção natural do retrato, reduzir o efeito de zoom no rosto e equilibrar melhor a composição em notebooks e desktops.

## Atualização v6

- Foto da Vanessa substituída pelo arquivo enviado via Postimages, salva localmente em `assets/vanessa-regina.jpg` e com fallback para o link direto da imagem.
- Nova seção **Perfil da Empresa no Google** com as unidades de São João de Meriti e Vicente de Carvalho, mapas incorporados do Google Maps, endereço, horário, telefone, avaliação e links para perfil/rotas.
- Menu principal e rodapé receberam atalho para a seção Google.
- Título da seção introdutória foi reformatado para evitar quebras de linha ruins em telas desktop e mobile.
- CSS atualizado para a versão `6.0.0`.

## Versão 7

- Removida a foto do bloco principal (hero), evitando a área que vinha causando falhas visuais.
- Mantida apenas a foto da Vanessa na seção “Sobre”, em tamanho reduzido, com função de identificação profissional.
- Removido o mapa incorporado da unidade de Vicente de Carvalho; as informações e links do perfil permanecem disponíveis.
- WhatsApp configurado para **(21) 97386-8126**.
- E-mail configurado para **vanessacontabilidade@outlook.com** e exibido diretamente no botão de contato.


## Versão 8
- Revisão completa do layout responsivo para celulares.
- Cabeçalho e menu móvel mais compactos e seguros.
- Tipografia, espaçamentos, cards, Google Business e contato adaptados para telas estreitas.
- Quebra segura do e-mail no botão de contato.
- Cache-busting atualizado para CSS e JavaScript (v8.0.0).
