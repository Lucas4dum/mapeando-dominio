# mapeando-dominio
Desafio para aplicar aprendizado sobre Fundamentos do DDD.
[link do contexto da atividade](https://efficient-sloth-d85.notion.site/Gloss-rio-DDD-3a81b4df36d348a299ccbc53f38a1665)
✅ Casos de Uso
Agora os principais casos de uso levantados da conversa:

**Organizando o projeto**
estoque-inteligente/
<br>├── docs/
<br>│   └── requisitos.md       # Documento com as entidades e casos de uso
<br>├── backend/
<br>│   ├── src/
<br>│   ├── tests/
<br>│   └── composer.json
<br>├── frontend/
<br>│   ├── src/
<br>│   ├── public/
<br>│   └── package.json
<br>├── docker/
<br>│   ├── docker-compose.yaml
<br>│   └── ...
<br>├── .env.example
<br>├── README.md

# Requisitos do Sistema de Gerenciamento de Estoque

## 1. Entidades de Domínio

### 1.1 Produto
- **id**: Identificador único do produto
- **nome**: Nome do produto
- **descrição**: Descrição do produto
- **tamanho**: Tamanho do produto
- **cor**: Cor do produto
- **quantidade_atual**: Quantidade disponível no estoque
- **quantidade_minima**: Quantidade mínima que deve ser mantida em estoque
- **preco_venda**: Preço de venda do produto
- **custo**: Custo do produto

### 1.2 Estoque
- **produto_id**: Referência ao produto
- **data_movimentacao**: Data da movimentação (entrada ou saída)
- **tipo**: Tipo da movimentação (entrada ou saída)
- **quantidade**: Quantidade movimentada
- **observacoes**: Observações relacionadas à movimentação

### 1.3 Venda
- **id**: Identificador único da venda
- **produto_id**: Produto vendido
- **quantidade_vendida**: Quantidade de produto vendida
- **data_venda**: Data da venda
- **valor_unitario**: Preço unitário do produto na venda
- **valor_total**: Valor total da venda (quantidade * valor_unitario)
- **lucro**: Lucro gerado pela venda

### 1.4 Ordem de Compra
- **id**: Identificador único da ordem de compra
- **produto_id**: Produto relacionado à ordem de compra
- **quantidade**: Quantidade solicitada na ordem
- **status**: Status da ordem (pendente, enviada, recebida)
- **data_criacao**: Data de criação da ordem de compra
- **data_estimativa_entrega**: Data estimada para a entrega do produto

### 1.5 Fornecedor
- **id**: Identificador único do fornecedor
- **nome**: Nome do fornecedor
- **contato**: Informações de contato do fornecedor
- **produtos_fornecidos**: Lista de produtos fornecidos por este fornecedor
- **prazo_medio_entrega**: Prazo médio de entrega dos produtos

### 1.6 Alerta
- **id**: Identificador único do alerta
- **produto_id**: Produto associado ao alerta
- **tipo**: Tipo de alerta (estoque baixo)
- **data**: Data em que o alerta foi gerado
- **metodo_notificacao**: Método de notificação (e-mail, sistema)

---

## 2. Casos de Uso

### 2.1 Casos de Uso Principais

1. **Cadastrar Produto**
   - O sistema deve permitir o cadastro de novos produtos, incluindo informações como nome, tamanho, cor, quantidade em estoque, preço de venda, custo, etc.

2. **Editar Produto**
   - O sistema deve permitir editar as informações de um produto já cadastrado.

3. **Acompanhar Movimentações de Estoque**
   - O sistema deve registrar as movimentações de estoque, associando uma data, tipo (entrada ou saída), quantidade e observações.

4. **Definir Quantidade Mínima de Estoque**
   - O sistema deve permitir definir uma quantidade mínima para cada produto em estoque.

5. **Emitir Alerta de Estoque Baixo**
   - O sistema deve gerar um alerta quando o estoque de um produto atingir a quantidade mínima definida.

6. **Enviar Alertas de Estoque Baixo**
   - O sistema deve permitir o envio de alertas via e-mail e exibição de notificações no sistema.

7. **Visualizar Histórico de Vendas**
   - O sistema deve permitir visualizar o histórico de vendas por produto e por período.

8. **Analisar Tendências de Estoque**
   - O sistema deve permitir visualizar a variação do estoque ao longo do tempo.

9. **Visualizar Produtos com Melhor Desempenho de Vendas**
   - O sistema deve permitir visualizar os produtos mais vendidos em determinado período.

10. **Gerar Ordens de Compra Automaticamente**
    - O sistema deve gerar ordens de compra automaticamente com base nas quantidades mínimas de estoque e tendências de vendas.

11. **Gerenciar Ordens de Compra**
    - O sistema deve permitir a criação, atualização e monitoramento do status das ordens de compra.

12. **Integrar com Fornecedores**
    - O sistema deve permitir integrar com fornecedores, atualizando automaticamente os prazos de entrega e outros dados relevantes.


