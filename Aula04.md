# Atividade: Elicitação de Requisitos e Fontes de Informação

---

## Processo 1: Registro de Pedidos (Vendedores)

### Requisito 1.1: Registro do canal de venda e dados do cliente
- **Requisito:** O sistema deve permitir registrar o canal de atendimento (venda por telefone ou presencial), vinculando os dados cadastrais do cliente e o endereço de entrega ao pedido.
- **Fonte 1:** Entrevista com vendedor externo e operador de televendas. *Fonte humana, nível operacional, classe de usuário: vendedor.*
- **Fonte 2:** Formulários físicos em papel e planilhas eletrônicas utilizadas atualmente no atendimento. *Fonte não humana, categoria: documentação.*

### Requisito 1.2: Consulta de estoque em tempo real na montagem do pedido
- **Requisito:** O sistema deve exibir a quantidade de produtos disponíveis em estoque no instante da inclusão de cada item no carrinho, impedindo a inserção de itens sem saldo físico suficiente.
- **Fonte 1:** Reunião com o Supervisor de Vendas. *Fonte humana, nível tático.*
- **Fonte 2:** Base de dados do software de controle comercial utilizado pela empresa. *Fonte não humana, categoria: sistema legado.*

### Requisito 1.3: Seleção e validação das condições de pagamento
- **Requisito:** O sistema deve permitir selecionar a condição de pagamento acordada (ex.: dinheiro, cartão, boleto ou faturamento a prazo) e calcular descontos conforme a política comercial autorizada.
- **Fonte 1:** Política comercial e tabela de alçadas da empresa. *Fonte não humana, categoria: documentação.*
- **Fonte 2:** Entrevista com o Diretor Comercial. *Fonte humana, nível estratégico.*

---

## Processo 2: Gestão de Produtos (Administrador)

### Requisito 2.1: Cadastro detalhado de novos produtos
- **Requisito:** O sistema deve permitir ao administrador cadastrar novos produtos informando nome, descrição completa, SKU/código de barras, categoria, unidade de medida e preço de venda.
- **Fonte 1:** Entrevista com o Administrador do Sistema. *Fonte humana, nível operacional, classe de usuário: administrador.*
- **Fonte 2:** Padrão técnico de codificação de mercadorias (GS1 Brasil / Padrão EAN). *Fonte não humana, categoria: norma.*

### Requisito 2.2: Desativação e exclusão lógica de produtos
- **Requisito:** O sistema deve permitir inativar ou excluir logicamente produtos fora de linha, preservando todo o histórico de vendas passadas para relatórios e fins contábeis.
- **Fonte 1:** Legislação tributária e normas contábeis de guarda de dados fiscais. *Fonte não humana, categoria: norma.*
- **Fonte 2:** Entrevista com o Gerente de Operações / TI. *Fonte humana, nível tático.*

### Requisito 2.3: Atualização de preços em massa
- **Requisito:** O sistema deve oferecer recurso de importação de arquivo (CSV ou planilha Excel) para atualização de preços em lote por categoria.
- **Fonte 1:** Análise de plataformas de e-commerce e sistemas ERP concorrentes do segmento. *Fonte não humana, categoria: concorrência.*
- **Fonte 2:** Entrevista com o Coordenador de Precificação e Produtos. *Fonte humana, nível tático.*

---

## Processo 3: Controle de Estoque (Equipe de Estoque)

### Requisito 3.1: Registro de entrada via importação de XML da Nota Fiscal
- **Requisito:** O sistema deve registrar a entrada de produtos no estoque através do carregamento e processamento automático do arquivo XML da Nota Fiscal Eletrônica (NF-e) emitida pelo fornecedor.
- **Fonte 1:** Entrevista com os conferentes e estoquistas de recebimento. *Fonte humana, nível operacional, classe de usuário: estoquista.*
- **Fonte 2:** Manual de Orientação do Contribuinte da Nota Fiscal Eletrônica (NF-e/SEFAZ). *Fonte não humana, categoria: documentação.*

### Requisito 3.2: Baixa automática do estoque após separação e expedição
- **Requisito:** O sistema deve atualizar e dar baixa definitiva na quantidade física em estoque assim que o operador bipar e confirmar a separação dos itens para envio.
- **Fonte 1:** Procedimento Operacional Padrão (POP) de expedição e logística da empresa. *Fonte não humana, categoria: documentação.*
- **Fonte 2:** Reunião de alinhamento com o Supervisor de Logística. *Fonte humana, nível tático.*

### Requisito 3.3: Registro de avarias, perdas e ajustes de inventário
- **Requisito:** O sistema deve fornecer um fluxo para lançamento de perdas, produtos danificados e ajustes de balanço de inventário físico, exigindo motivo justificado e autorização.
- **Fonte 1:** Entrevista com o Auditor de Estoque e Inventário. *Fonte humana, nível operacional, classe de usuário: auditor de estoque.*
- **Fonte 2:** Relatórios de perdas e histórico de divergências do sistema antigo. *Fonte não humana, categoria: sistema legado.*
