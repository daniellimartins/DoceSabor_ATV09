# 🍰 Doce Sabor

Site da confeitaria de bairro **Doce Sabor**, criado como **Caderno de Pesquisa** da U.C. de Linguagem de Marcação (Técnico em Desenvolvimento de Sistemas, 2º semestre, Escola SENAI "A. Jacob Lafer" CFP 1.18).

A Doce Sabor vende bolos, doces e salgados. Os pedidos chegavam por mensagem no celular e muita coisa se perdia, então o site reúne cardápio, perguntas frequentes, localização e um formulário de encomenda.

## 📁 Arquivos

| Arquivo | Descrição |
|---|---|
| `doce_sabor.html` | Página inicial: logo, slogan, bolo do mês, cardápio, perguntas frequentes e rodapé |
| `cardapio.html` | Página do cardápio com tabela de preços e formulário de encomenda |
| `estilo.css` | Estilo da página inicial |
| `estiloCardapio.css` | Estilo da página do cardápio (tabela, formulário e botões) |

## 🧱 Estrutura e semântica

Estrutura base de cada página:

- `<html lang="pt-br">` informa o idioma ao navegador e ao leitor de tela.
- `<meta charset="UTF-8">` garante os acentos corretos.
- `<meta name="viewport" ...>` deixa a página ajustada ao celular.
- `<link rel="stylesheet" ...>` carrega o CSS.

Tags semânticas usadas:

| Bloco | Tag | Conteúdo |
|---|---|---|
| Logo e slogan | `<header>` | `<img>`, `<h1>`, `<p>` |
| Bolo do mês | `<article>` | `<h2>`, `<img>`, `<p>`, `<time>` |
| Cardápio | `<section>` | `<h2>` e os cards (cada um um `<article>`) |
| Perguntas frequentes | `<section>` | `<h2>`, `<details>`, `<summary>`, `<p>` |
| Rodapé | `<footer>` | `&copy;`, `<address>` com `mailto:` e `tel:` |

**Por que `<article>` e `<section>`?** O bolo do mês é um conteúdo independente, que faria sentido sozinho fora da página (`<article>`). O cardápio agrupa itens do mesmo assunto dentro da página (`<section>`).

**Acessibilidade:** `<header>`, `<main>` e `<footer>` no lugar de `<div>` ajudam o leitor de tela a identificar as partes do site. O `<strong>` indica importância (o `<b>` é só visual), e o `<iframe>` precisa de `title` para o leitor dizer o que ele mostra.

## 📝 Formulário de encomenda

- Enviado com `method="post"` para `action="/encomendas"`.
- Campos: nome e e-mail (obrigatórios), sabor do bolo (`<select>` com `value`), data de retirada (`type="date"`) e forma de recebimento (`type="radio"`, retirar na loja ou entrega, com o mesmo `name`).
- Todo campo tem um `<label for="...">` ligado ao `id` do campo.
- Botões de envio e de limpar (`type="reset"`).

## 🎨 Estilo (CSS)

Paleta da Doce Sabor:

| Cor | Código | Uso |
|---|---|---|
| Rosa | `#eb98aa` | Header, footer, cabeçalho da tabela e botões |
| Creme | `#ede0c7` | Fundo da página |
| Creme claro | `#f7eae0` | Cartões (`section`) |
| Marrom | `#4e1410` | Texto |
| Marrom escuro | `#4A3207` | Títulos `h2` |

Na página do cardápio, o CSS estiliza a tabela (linhas alternadas e destaque ao passar o mouse), os campos do formulário (borda rosa e foco), os botões (hover e visual de contorno para o "Limpar") e o rodapé.

Técnicas trabalhadas na atividade:

- **Variáveis CSS** (`:root` e `var()`): para trocar o rosa por lilás, basta mudar em um só lugar.
- **Grid:** `grid-template-columns: 1fr 1fr 1fr` cria 3 colunas iguais, `gap` define o espaço entre elas e `grid-column: 1 / -1` faz o item ocupar todas as colunas.
- **Media query:** com `@media (max-width: 768px)` o cardápio passa para 1 coluna no celular.
- **Header fixo:** `position: sticky` com `backdrop-filter: blur()` para o efeito de vidro fosco.
- **Botão `.btn-pedido`:** `transition` com `transform: scale()` no `:hover` para crescer de forma suave.

## 🗺️ Outros recursos

- **Perguntas frequentes** com `<details>` e `<summary>`, sem JavaScript. A segunda pergunta começa aberta com o atributo `open`.
- **Mapa da loja** com `<iframe>` do Google Maps: `src` (endereço do mapa), `width` e `height` (tamanho) e `title` (descrição para leitor de tela).
- **Contato** no rodapé com `mailto:` (abre o e-mail) e `tel:` (abre a ligação no celular).

## ▶️ Como usar

1. Baixe os arquivos na mesma pasta.
2. Abra o `doce_sabor.html` no navegador (ou no [VS Code Online](https://vscode.dev/?vscode-lang=pt)).
3. Navegue pelo link do rodapé para o cardápio.

## 📚 Fontes consultadas

- [MDN Web Docs](https://developer.mozilla.org/pt-BR/)
- [W3Schools](https://www.w3schools.com/)
- [Validador do W3C](https://validator.w3.org/)
