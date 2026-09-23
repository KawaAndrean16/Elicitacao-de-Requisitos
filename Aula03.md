# Atividade: Requisitos Não-Funcionais (RNF) e ISO/IEC 25010

---

## História 1: Avaliação do Pedido pelo Cliente

> **Como** cliente, **quero** avaliar o pedido depois da entrega, **para** ajudar outros clientes a escolherem melhor.

### Critérios de Aceitação da História:
- *Dado que o pedido foi entregue, quando o cliente abre o app, então aparece a opção de avaliar o pedido.*
- *Dado que o cliente avalia com nota e comentário, quando confirma o envio, então a avaliação aparece no perfil do restaurante.*

### Requisitos Não-Funcionais (RNF):

1. **RNF 1.1 - Latência de Atualização Pública**
   - **Descrição:** Após o cliente submeter a avaliação e comentário, a informação agregada (média de notas e novo comentário) deve ser refletida publicamente no perfil do restaurante em menos de **3 segundos**.
   - **Característica ISO/IEC 25010:** Eficiência de Desempenho (*Performance Efficiency*) — *Comportamento Temporal / Resposta no Tempo*.

2. **RNF 1.2 - Disponibilidade do Formulário Offline / Falha de Rede**
   - **Descrição:** Caso o cliente preencha a avaliação e ocorra uma perda temporária de conectividade móvel, o aplicativo deve reter localmente os dados preenchidos e reenviá-los de forma automática assim que a ligação à rede for restabelecida, evitando perda de dados.
   - **Característica ISO/IEC 25010:** Fiabilidade (*Reliability*) — *Tolerância a Falhas / Recuperabilidade*.

3. **RNF 1.3 - Acessibilidade do Mecanismo de Avaliação**
   - **Descrição:** O ecrã de avaliação (estrelas/notas e campo de texto) deve estar em conformidade com as diretrizes WCAG 2.1 nível AA, permitindo navegação completa por leitores de ecrã (TalkBack/VoiceOver) e contraste de cores adequado.
   - **Característica ISO/IEC 25010:** Usabilidade (*Usability*) — *Acessibilidade*.

---

## História 2: Armazenamento de Cartão de Pagamento

> **Como** cliente, **quero** salvar um cartão de pagamento, **para** não digitar os dados a cada compra.

### Critérios de Aceitação da História:
- *Dado que o cliente cadastra um cartão válido, quando confirma o cadastro, então o cartão fica disponível para escolha no checkout.*
- *Dado que o cliente tem um cartão salvo, quando faz um novo pedido, então pode selecionar esse cartão sem redigitar os dados.*

### Requisitos Não-Funcionais (RNF):

1. **RNF 2.1 - Encriptação e Conformidade com Padrões de Segurança**
   - **Descrição:** Nenhum dado sensível de pagamento (como o CVV completo ou o PAN em texto simples) pode ser armazenado em base de dados local; o sistema deve utilizar tokenização via *gateway* em conformidade com a norma **PCI-DSS** e cifragem AES-256 em trânsito e em repouso.
   - **Característica ISO/IEC 25010:** Segurança (*Security*) — *Confidencialidade*.

2. **RNF 2.2 - Prevenção de Erros de Registo e Validação Rápida**
   - **Descrição:** O formulário de registo do cartão deve efetuar validação sintática em tempo real (algoritmo de Luhn para números de cartão e máscara de formato mm/aa) antes de submeter a requisição, reduzindo transações inválidas e erros operacionais do utilizador.
   - **Característica ISO/IEC 25010:** Usabilidade (*Usability*) — *Proteção contra Erros do Utilizador*.

3. **RNF 2.3 - Integridade e Autenticidade Transacional**
   - **Descrição:** Ao selecionar um cartão previamente salvo no checkout, o sistema deve garantir que o token utilizado pertence estritamente ao utilizador autenticado e registar registos de auditoria imutáveis com carimbo de data/hora para cada tentativa de cobrança.
   - **Característica ISO/IEC 25010:** Segurança (*Security*) — *Integridade e Não Repúdio*.

---

## História 3: Resumo Diário de Vendas para Restaurante

> **Como** dono de restaurante, **quero** ver um resumo diário de vendas, **para** acompanhar o desempenho do dia.

### Critérios de Aceitação da História:
- *Dado que o dia comercial termina, quando o restaurante abre o painel de vendas, então vê o total de pedidos e o faturamento do dia.*
- *Dado que o restaurante seleciona um período diferente, quando aplica o filtro, então o resumo é recalculado para aquele período.*

### Requisitos Não-Funcionais (RNF):

1. **RNF 3.1 - Tempo de Processamento em Lotes e Filtragem**
   - **Descrição:** Ao aplicar um filtro de período personalizado (mesmo com volumes superiores a 10.000 transações acumuladas), o recálculo dos indicadores de faturação e pedidos deve ser concluído e apresentado no ecrã em no máximo **1,5 segundos**.
   - **Característica ISO/IEC 25010:** Eficiência de Desempenho (*Performance Efficiency*) — *Comportamento Temporal e Capacidade*.

2. **RNF 3.2 - Compatibilidade e Responsividade Multiplataforma**
   - **Descrição:** O painel de vendas e gráficos de faturação diária deve ser totalmente responsivo, adaptando-se sem perda de legibilidade ou corte de dados a ecrãs de tablets, telemóveis e computadores de secretária (resoluções de 360px até 1920px de largura).
   - **Característica ISO/IEC 25010:** Compatibilidade (*Compatibility*) — *Interoperabilidade / Coexistência* (ou Portabilidade — *Adaptabilidade*).

3. **RNF 3.3 - Precisão no Cálculo dos Dados Financeiros**
   - **Descrição:** Os valores totais de faturação, taxas e deduções exibidos no resumo devem ter exatidão decimal estrita (arredondamento bancário) sem discrepâncias numéricas face aos registos contábeis brutos da base de dados.
   - **Característica ISO/IEC 25010:** Adequação Funcional (*Functional Suitability*) / Fiabilidade (*Reliability*) — *Correção Funcional / Precisão dos Dados*.
