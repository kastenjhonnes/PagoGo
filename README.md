# PagoGo — Portal de Mobilidade e Transporte Interurbano

## Apresentação e Descrição

O **PagoGo** é um portal informativo e integrador voltado para facilitar a consulta de
itinerários, modais de transporte (ônibus, trem e avião) e rotas interurbanas. O objetivo
central é reunir em um só lugar informações acessíveis sobre opções de deslocamento,
horários e dicas de viagem.

## Justificativa do Tema

A escolha do tema de mobilidade urbana e interurbana justifica-se pela constante necessidade
das pessoas de planejarem viagens e trajetos diários com eficiência. Um portal centralizado
simplifica a comparação de modais e melhora a experiência de navegação do usuário que busca
praticidade.

## Objetivo

Prover uma interface limpa, semântica, responsiva e de fácil navegação para que passageiros
possam pesquisar rotas de transporte, conhecer as opções disponíveis e entrar em contato
com a equipe de suporte ou envio de sugestões.

## Público-Alvo

Viajantes, estudantes, trabalhadores intermunicipais e turistas que utilizam transporte
coletivo ou interurbano e buscam informações rápidas sobre trajetos e modais de viagem.

## Autoria

- **Estudante:** Kasten Correa
- **Instituição:** Instituto Federal Catarinense (IFC) — Campus Araquari
- **Curso:** Redes de Computadores

## Links do Projeto

- **Repositório GitHub:** <https://github.com/kastencorrea/PagoGo>
- **Publicação (GitHub Pages):** <https://kastencorrea.github.io/PagoGo/>

---

## Estrutura do Projeto e Mapa de Páginas

### Estrutura de Arquivos

```text
PagoGo/
├── index.html          # Página inicial com destaques e modais
├── rotas.html          # Listagem de rotas e modais de transporte
├── contato.html        # Formulário de contato e suporte
├── assets/
│   ├── css/
│   │   └── global.css  # Estilização global com Flexbox e media queries
│   └── js/
│       └── script.js   # Reserva para scripts da Versão 2 (vazio nesta versão)
├── imagens/            # Mídias e ilustrações (aviao, onibus, trem)
└── README.md           # Documentação do projeto
```

### Mapa de Páginas

O portal é composto por três páginas HTML interligadas por um menu de navegação global
presente no cabeçalho de todas elas:

- **index.html** — Página inicial com hero, formulário de busca, cards de rotas populares
  e seção de benefícios do portal.
- **rotas.html** — Guia comparativo dos modais de transporte (ônibus, trem, avião) com
  matriz de custo, impacto ambiental e flexibilidade.
- **contato.html** — Formulário de contato e solicitação de roteiro personalizado.

A navegação entre as três páginas é feita pelo menu no cabeçalho (`<nav class="nav-menu">`),
com indicação visual da página ativa pela classe `.active`.

---

## Planejamento Visual (Wireframe)

O planejamento visual foi feito com base em um layout de três zonas verticais:

1. **Cabeçalho fixo no topo** — logo à esquerda, menu à direita (Flexbox com
   `justify-content: space-between`).
2. **Conteúdo principal** — dividido em seções empilhadas:
   - Hero com título, subtítulo e formulário de busca.
   - Grid de cards com 3 colunas em desktop (Flexbox com `flex-wrap`).
   - Seção de benefícios com 3 itens alinhados horizontalmente.
3. **Rodapé** — faixa escura com texto de copyright centralizado.

Em telas menores que 768 px, o layout reorganiza-se em coluna única: menu empilhado,
cards em coluna, formulário de busca em coluna. Em telas até 480 px, a tipografia é
reduzida e o botão do formulário ocupa 100 % da largura.

---

## Tecnologias Utilizadas

- **HTML5** — estruturação semântica (`<header>`, `<nav>`, `<main>`, `<section>`,
  `<article>`, `<aside>`, `<footer>`).
- **CSS3** — variáveis CSS (`:root`), Flexbox, media queries, estados `:hover` e `:focus`,
  transições suaves.
- **Git / GitHub** — versionamento e publicação via GitHub Pages.

Não há uso de JavaScript nesta versão (conforme escopo da Versão 1).

---

## Funcionalidades Implementadas (Versão 1)

- Navegação funcional entre três páginas.
- Menu global com indicação de página ativa.
- Formulário de busca na página inicial (redireciona para `rotas.html`).
- Formulário completo de contato com validação HTML nativa (`required`).
- Cards informativos com imagens, badges e preços.
- Matriz comparativa de modais em lista (`<ul class="info-list">`).
- Bloco `<aside>` com dica de logística sustentável.
- Layout responsivo com media queries em 768 px e 480 px.
- Identidade visual consistente via variáveis CSS.
- Estados `:hover` e `:focus` visíveis em links, botões e campos.

---

## Funcionalidades Planejadas para a Versão 2

As funcionalidades abaixo serão implementadas com JavaScript na próxima versão.
Nenhuma delas está ativa nesta entrega — são apenas planejadas e registradas aqui.

| Funcionalidade | Página | Elementos envolvidos | Ação do usuário | Comportamento esperado | Contribuição para o portal |
|---|---|---|---|---|---|
| **Filtro de rotas por modal** | `rotas.html` | Botões de filtro (`<button>`) + cards (`.card`) | Clicar em "Ônibus", "Trem" ou "Avião" | Exibir somente os cards do modal escolhido, ocultando os demais | Facilita a comparação e reduz a sobrecarga visual |
| **Validação do formulário de contato** | `contato.html` | Campos `#nome`, `#email`, `#preferencia`, `#mensagem` e botão de envio | Preencher e enviar o formulário | Validar formato de e-mail e campos obrigatórios, exibindo mensagens de erro/sucesso sem recarregar a página | Evita envio de dados inválidos e melhora a experiência do usuário |
| **Estimativa de pegada de CO₂** | `index.html` | Campos de origem/destino (`.search-box`) + área de resultado | Preencher origem e destino e clicar em "Pesquisar Rotas" | Calcular e exibir uma estimativa aproximada de emissão de CO₂ por modal | Reforça a proposta sustentável do portal e diferencia a plataforma |

### Detalhamento das funcionalidades planejadas

#### 1. Filtro de rotas por modal

- **Página:** `rotas.html`
- **Elementos envolvidos:** botões de filtro, cards `.card` com atributo `data-modal`
- **Ação do usuário:** selecionar o modal desejado
- **Comportamento esperado:** os cards exibidos são filtrados dinamicamente
- **Contribuição:** torna a comparação mais objetiva e reduz ruído visual

#### 2. Validação do formulário de contato

- **Página:** `contato.html`
- **Elementos envolvidos:** formulário `.main-form`, inputs, `textarea`, botão
- **Ação do usuário:** clicar em "Enviar Solicitação"
- **Comportamento esperado:** validação em tempo real com mensagens de erro visíveis
- **Contribuição:** garante integridade dos dados e feedback imediato ao usuário

#### 3. Estimativa de pegada de CO₂

- **Página:** `index.html`
- **Elementos envolvidos:** inputs de origem/destino e área de resultado
- **Ação do usuário:** preencher busca e clicar em "Pesquisar Rotas"
- **Comportamento esperado:** cálculo aproximado da emissão por modal escolhido
- **Contribuição:** reforça o pilar de sustentabilidade do projeto

---

## Responsividade

O portal foi adaptado para três faixas de tela:

- **Desktop (acima de 768 px):** cards em três colunas, menu horizontal, hero centralizado.
- **Tablet (até 768 px):** cards empilhados, formulário de busca em coluna, menu empilhado.
- **Celular (até 480 px):** layout em coluna única, tipografia ajustada, botão em largura
  total, imagens fluidas.

As adaptações são controladas pelas media queries `@media (max-width: 768px)` e
`@media (max-width: 480px)` em `global.css`, que alteram:

- `.header-container` → `flex-direction: column`
- `.search-box` → `flex-direction: column`
- `.cards-grid` e `.benefits-grid` → `flex-direction: column`
- `.card` → `flex: 1 1 100%`
- `.btn-primary` → `width: 100%` (em 480 px)
- `.hero-content h1` → tamanho reduzido (em 480 px)

Testado com o modo responsivo do DevTools do Chrome/Firefox.

---

## Acessibilidade

- Uso de HTML semântico (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`,
  `<aside>`, `<footer>`).
- Todas as imagens possuem `alt` descritivo.
- Formulários com `<label>` associado via `for`/`id`; labels invisíveis nos campos
  de busca para leitores de tela.
- Estados `:hover` e `:focus` visíveis em links, botões e inputs (contorno verde
  esmeralda de 3 px).
- Contraste de texto revisado nas áreas principais.

---

## Como Executar Localmente

1. Clone o repositório:

   ```bash
   git clone https://github.com/kastencorrea/PagoGo.git
   ```

2. Acesse a pasta do projeto:

   ```bash
   cd PagoGo
   ```

3. Abra o arquivo `index.html` diretamente no navegador, ou utilize a extensão
   **Live Server** do VS Code para servir localmente.

---

## Publicação (GitHub Pages)

O projeto está publicado via GitHub Pages no endereço:

**<https://kastencorrea.github.io/PagoGo/>**

Para publicar/atualizar:

1. Faça o push da branch `main`.
2. Vá em **Settings → Pages** no repositório.
3. Selecione a branch `main` e a pasta `/ (root)`.
4. Aguarde a publicação e acesse o link acima.

---

## Principais Dificuldades Encontradas

- **Flexbox em grids de cards:** ajustar `flex: 1 1 calc(33.333% - 1rem)` para que
  três cards caibam por linha sem quebrar em telas intermediárias exigiu testes.
- **Responsividade do menu:** fazer o menu horizontal virar vertical no mobile sem
  perder a indicação de página ativa.
- **Consistência visual entre páginas:** manter a identidade (cores, tipografia,
  espaçamentos) usando variáveis CSS em `:root`.
- **Publicação no GitHub Pages:** entender que o `index.html` precisa estar na raiz
  do repositório e que os caminhos de CSS e imagens devem ser relativos.
- **Semântica HTML:** decidir quando usar `<section>` vs `<article>` vs `<aside>`.

## Pontos a Corrigir / Aprimorar na Versão 2

- Implementar as três funcionalidades JavaScript planejadas.
- Adicionar mensagens de feedback visual na validação do formulário.
- Otimizar imagens (converter `.avif` para `.webp` com fallback `.jpg`) para navegadores
  mais antigos.
- Criar uma página adicional com detalhes de uma rota específica.
- Melhorar contraste de textos secundários (`.card-info`) para nível AAA de acessibilidade.

---

## Antes da Apresentação (Checklist)

- [x] Repositório público
- [x] GitHub Pages funcionando
- [x] Portal com pelo menos três páginas
- [x] Todas as páginas acessíveis pelo menu
- [x] Arquivos CSS carregando corretamente
- [x] Imagens aparecem corretamente
- [x] Portal funcional em telas menores (768 px e 480 px)
- [x] Formulário presente
- [x] README atualizado
- [x] Funcionalidades futuras planejadas
- [x] Links enviados abrem corretamente
- [x] Versão publicada corresponde ao código mais recente

---

&copy; 2026 PagoGo — Projeto Acadêmico IFC.