# Atividade: Making History (Product Owner)

---

## 1. Acompanhamento do Pedido pelo Cliente

### História de Utilizador (User Story)
> **Como** cliente da aplicação de entregas,  
> **Quero** visualizar o estado atualizado do meu pedido em tempo real após a confirmação do pagamento,  
> **Para que** eu possa saber exatamente em que etapa se encontra a preparação/entrega e programar-me para o receber.

### Critérios de Aceitação

#### Critério 1: Mudança de estado em tempo real
- **Dado** que o cliente concluiu o pagamento com sucesso,
- **Quando** o restaurante confirmar o início do preparo da refeição,
- **Então** o ecrã de acompanhamento deve atualizar o estado para "A preparar o pedido" sem necessidade de reiniciar a aplicação.

#### Critério 2: Notificação de saída para entrega
- **Dado** que o pedido foi recolhido pelo estafeta no restaurante,
- **Quando** o estafeta iniciar a rota no seu perfil,
- **Então** o cliente deve receber uma notificação push informando que o pedido saiu para entrega e exibir a previsão estimada de chegada.

#### Critério 3: Histórico e confirmação de entrega
- **Dado** que o estafeta marcou o pedido como finalizado no destino,
- **Quando** o cliente aceder ao ecrã de detalhes da encomenda,
- **Então** o estado final deve constar como "Pedido entregue" e deve ser apresentado o botão para avaliar o serviço.

---

## 2. Gestão de Itens Indisponíveis pelo Restaurante

### História de Utilizador (User Story)
> **Como** gestor do restaurante parceiro,  
> **Quero** alterar a disponibilidade de qualquer prato ou ingrediente do meu menu através do painel de controlo,  
> **Para que** os clientes não façam encomendas de itens esgotados, evitando cancelamentos e insatisfação.

### Critérios de Aceitação

#### Critério 1: Desativação imediata de um item
- **Dado** que o gestor do restaurante está autenticado no painel de administração,
- **Quando** desmarcar a opção "Disponível" de um determinado item,
- **Então** o item deve passar imediatamente ao estado "Esgotado" na ementa visível aos clientes.

#### Critério 2: Tentativa de compra de item esgotado
- **Dado** que um cliente tinha colocado um item no carrinho antes de o mesmo ser desativado,
- **Quando** tentar avançar para o ecrã de checkout,
- **Então** o sistema deve exibir um aviso informando que o item esgotou e bloquear a finalização do pedido até que este seja removido.

#### Critério 3: Reativação simplificada
- **Dado** que o restaurante voltou a ter stock de um produto previamente esgotado,
- **Quando** o gestor ativar novamente a opção "Disponível",
- **Então** o item deve voltar a estar elegível para compra imediatamente na aplicação pública.

---

## 3. Notificação de Incidências pelo Estafeta

### História de Utilizador (User Story)
> **Como** estafeta parceiro,  
> **Quero** reportar rapidamente incidentes ou imprevistos durante o percurso da entrega,  
> **Para que** o suporte e o cliente sejam informados do atraso e as medidas corretivas adequadas possam ser acionadas.

### Critérios de Aceitação

#### Critério 1: Seleção de motivo pré-definido
- **Dado** que o estafeta está com uma entrega em curso,
- **Quando** selecionar a opção "Reportar Problema" e escolher uma categoria válida (ex.: avaria de veículo, acidente, morada incorreta),
- **Então** o incidente deve ser registado com hora e localização geográfica do envio.

#### Critério 2: Atualização do cliente sobre o atraso
- **Dado** que um problema foi reportado pelo estafeta durante a rota,
- **Quando** o registo for validado pelo sistema,
- **Então** o cliente deve ser alertado com uma notificação no ecrã de rastreio sobre o atraso imprevisto e o novo tempo estimado.

#### Critério 3: Notificação imediata à equipa de suporte
- **Dado** que o incidente é do tipo crítico (ex.: acidente de trânsito ou furto),
- **Quando** o envio do relatório for concluído,
- **Então** um chamado de prioridade alta deve ser criado automaticamente no painel da equipa de apoio ao cliente.

---

## Priorização MoSCoW

| Prioridade | História / Funcionalidade | Justificativa |
| :--- | :--- | :--- |
| **Must Have** (Indispensável) | **História 2: Gestão de Itens Indisponíveis pelo Restaurante** | Essencial para a integridade da operação. Se o cliente comprar produtos inexistentes, ocorrem quebras de stock, devoluções financeiras e frustração grave imediata. |
| **Must Have** (Indispensável) | **História 1: Acompanhamento do Pedido pelo Cliente** | Funcionalidade nuclear da experiência de delivery. O cliente necessita de saber se o pedido foi recebido, preparado e quando irá chegar. |
| **Should Have** (Importante) | **História 3: Notificação de Incidências pelo Estafeta** | Muito relevante para gerir exceções operacionais e assegurar transparência, embora num MVP básico o estafeta possa inicialmente contactar o suporte por via telefónica/chat direto. |
| **Could Have** (Desejável) | *Rastreamento detalhado por GPS em tempo real no mapa* | Adiciona valor à História 1, mas os estados discretos (Recebido, A Preparar, Em Rota, Entregue) já resolvem a necessidade primária. |
| **Won't Have (nesta fase)** | *Reatribuição automática de estafetas via inteligência artificial em caso de avaria* | Complexidade técnica elevada para esta versão; o suporte humano lidará manualmente com as exceções reportadas pela História 3. |
