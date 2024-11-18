# desafio
Esquema do BD
Projeto de E-commerce
Entidades e Relacionamentos
1. Tabela: Produtos
Armazena as informações dos produtos vendidos na plataforma.

ID_Produto (Chave Primária)
Nome_Produto
Descrição
Preço
Quantidade_Estoque
ID_Vendedor (Chave Estrangeira para a tabela Vendedores)
ID_Fornecedor (Chave Estrangeira para a tabela Fornecedores)
Relacionamentos:

Cada produto é associado a um único Fornecedor.
Cada produto pode ser vendido por um Vendedor Terceiro.
2. Tabela: Vendedores
Armazena informações dos vendedores que comercializam produtos na plataforma.

ID_Vendedor (Chave Primária)
Nome_Vendedor
CPF_CNPJ
Endereço
Contato
Relacionamentos:

Um vendedor pode listar vários Produtos.
3. Tabela: Fornecedores
Armazena informações dos fornecedores dos produtos.

ID_Fornecedor (Chave Primária)
Nome_Fornecedor
CPF_CNPJ
Endereço
Contato
Relacionamentos:

Um fornecedor pode fornecer vários Produtos.
4. Tabela: Clientes
Armazena informações dos clientes cadastrados na plataforma.

ID_Cliente (Chave Primária)
Nome_Cliente
CPF_CNPJ (Identifica se é PF ou PJ)
Endereço (Com base no CEP para cálculo de frete)
Telefone
Email
Relacionamentos:

Um cliente pode realizar vários Pedidos.
5. Tabela: Pedidos
Armazena os pedidos realizados pelos clientes.

ID_Pedido (Chave Primária)
ID_Cliente (Chave Estrangeira para a tabela Clientes)
Data_Pedido
Status_Pedido (Enum: 'Pendente', 'Em Processamento', 'Enviado', 'Entregue', 'Cancelado')
Endereço_Entrega
Valor_Total
Frete
Prazo_Devolucao (Calculado com base no período de carência)
Relacionamentos:

Cada pedido é associado a um único Cliente.
Um pedido pode conter vários Produtos.
6. Tabela: Itens_Pedido
Relaciona os produtos incluídos em cada pedido.

ID_Item_Pedido (Chave Primária)
ID_Pedido (Chave Estrangeira para a tabela Pedidos)
ID_Produto (Chave Estrangeira para a tabela Produtos)
Quantidade
Preço_Unitario
Subtotal (Calculado como Quantidade * Preço_Unitario)
Relacionamentos:

Um pedido pode conter vários produtos.
Um produto pode estar em vários pedidos.
7. Tabela: Entregas
Armazena informações sobre as entregas dos pedidos.

ID_Entrega (Chave Primária)
ID_Pedido (Chave Estrangeira para a tabela Pedidos)
Codigo_Rastreio
Status_Entrega (Enum: 'Pendente', 'Em Trânsito', 'Entregue')
Data_Envio
Data_Entrega
Relacionamentos:

Cada pedido pode ter uma única entrega.
Fluxo dos Relacionamentos
Produtos e Vendedores: Os produtos são cadastrados por vendedores distintos, que podem ser terceiros. Um vendedor pode ter vários produtos à venda.
Produtos e Fornecedores: Cada produto é associado a um único fornecedor, responsável pelo abastecimento do estoque.
Clientes e Pedidos: Cada cliente pode realizar vários pedidos. Cada pedido é associado a um único cliente e pode conter um ou mais produtos.
Pedidos e Entregas: Cada pedido gera uma entrega, com status e código de rastreio para acompanhamento.
Itens_Pedido: Essa tabela intermediária permite que um pedido inclua vários produtos, detalhando quantidade, preços e subtotais.
Considerações Especiais
Cálculo do Frete: O valor do frete é calculado com base no endereço do cliente (CEP) e armazenado no pedido.
Devolução: A tabela Pedidos inclui o campo Prazo_Devolucao para controlar o período de carência para devolução.
Cancelamento de Pedidos: O cancelamento é registrado ao atualizar o campo Status_Pedido para "Cancelado".
Controle de Estoque: Ao confirmar um pedido, a quantidade em estoque de cada produto será atualizada automaticamente.

