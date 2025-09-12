Projeto Padaria Doce Sabor
Atividade Prática 9 – Programação Web

O projeto simula o site de uma padaria com catálogo de produtos, carrinho de compras, painel administrativo e sistema de pontos de fidelidade.

---
## Variáveis Principais (script.js)

### Produtos
- `produtos` → Array de objetos que armazena todos os produtos disponíveis.  
  Cada objeto contém:
  - `id` → Identificador único do produto (ex: "PAO001").
  - `nome` → Nome do produto.
  - `preco` → Valor unitário em R$.
  - `estoque` → Quantidade disponível em estoque.
  - `vendidos` → Quantidade vendida até o momento.
  - `promocao` → Percentual de desconto aplicado (%).
  - `imagem` → Caminho para imagem ilustrativa.

### Carrinho e Cliente
- `carrinho` → Array que guarda os itens adicionados pelo cliente (id, nome, preço e quantidade).
- `pontos` → Pontos acumulados pelo cliente (1 ponto = R$1 de desconto).
- `historico` → Lista de compras já finalizadas (guarda itens, total e data).

### Funções e Cálculos
- `filtrarProdutos()` → Filtra produtos pelo campo de busca.
- `criarCardProduto(produto)` → Gera o card HTML de cada produto.
- `adicionarCarrinho(id)` → Adiciona produto ao carrinho e atualiza estoque.
- `renderCarrinho()` → Recalcula subtotal, descontos, impostos, entrega e total.
  - **Subtotal** = soma dos itens.
  - **Desconto por quantidade** = 10% se comprar ≥ 10 itens.
  - **Cupom** (`descontoCupom`) → desconto manual em R$.
  - **Entrega** (`entrega`) → valor fixo da taxa.
  - **Imposto** (`imposto`) → percentual aplicado sobre subtotal.
  - **Pontos usados** (`usarPontos`) → desconto em R$.
- `calcularTroco()` → Calcula troco com base em `valorPago`.
- `converterMoeda()` → Converte o total em BRL, USD ou EUR.
- `finalizarCompra()` → Conclui a compra, atualiza pontos, histórico e estatísticas.
- `renderPainel()` → Atualiza painel administrativo com preços, promoções e estoque.
- `renderEstatisticas()` → Mostra número de pedidos, faturamento e produto mais vendido.
- `limparDados()` → Zera pontos, histórico e vendas.

### Estilização (styles.css)
- `:root` → Define variáveis globais de estilo:
  - `--brand-color` → Cor principal (bege).
  - `--accent-color` → Cor de destaque (marrom).
  - `--text-color` → Cor padrão do texto.
  - `--bg` → Fundo da página.
  - `--shadow` → Sombras em botões e caixas.
- Classes como `.produto`, `.carrinho-container`, `.painel-valores`, `.btn-floating` controlam layout e responsividade.

---
## Estrutura do Projeto

📄 index.html → Página principal da Padaria Doce Sabor.  
📄 script.js → Regras de negócio (carrinho, pontos, painel).  
📄 styles.css → Estilização e responsividade.  
📄 README.txt → Explicação das variáveis (este arquivo).  
📄 testes.html → Página para demonstrações de código/testes.  
📁 exemplos/ → Exemplos de uso dos conceitos aplicados.

---
## Observações
- O sistema utiliza `localStorage` para salvar carrinho temporariamente.  
- Pontos de fidelidade são acumulados a cada compra (1 ponto a cada R$10).  
- As promoções podem ser ajustadas pelo painel administrativo.

Desenvolvido por Elisangela Felix