# Atividade: Sua Vez de Criar um Caso

---

## 1. Empatia
**Pergunta de empatia:** Por que eu acabo sempre atrasando ou esquecendo as revisões e manutenções preventivas do carro (como a troca de óleo por quilometragem ou tempo), mesmo sabendo o quanto isso é importante para não danificar o motor?

---

## 2. Definição
**Definição do problema:** Eu não atraso as revisões por falta de cuidado ou desorganização financeira; o problema é que a informação fica presa em uma etiqueta colada no para-brisa ou em um manual dentro do porta-luvas, suportes que não olho no dia a dia, sem que exista nenhum aviso preditivo antes do vencimento do prazo.

---

## 3. Ideação
1. **Ideia 1:** Notificação push no celular com cálculo preditivo da quilometragem média semanal, avisando 500 km ou 15 dias antes do vencimento do óleo/filtro.
2. **Ideia 2:** Widget na tela inicial do celular mostrando uma barra com a porcentagem de vida útil de cada componente essencial do carro (óleo, pneus, pastilhas de freio).
3. **Ideia 3:** Scanner leitor OBD-II conectado via Bluetooth que sincroniza a quilometragem real com o aplicativo e agenda a oficina de forma automática ao identificar um prazo atingido.

---

## 4. Escolha
**Ideia escolhida:** Notificação push no celular com cálculo preditivo da quilometragem média semanal, avisando 500 km ou 15 dias antes do vencimento do óleo/filtro (Ideia 1).

---

## 5. Histórias de Usuário (User Stories)

### História 1
> **Como** motorista e dono do veículo,  
> **Quero** cadastrar a data e a quilometragem da última troca de óleo junto com a minha média de uso semanal,  
> **Para que** o sistema calcule uma previsão de quando será a próxima revisão sem que eu precise preencher dados todos os dias.

### História 2
> **Como** motorista com rotina corrida,  
> **Quero** receber alertas e notificações no celular 15 dias ou 500 km antes do prazo estimado da manutenção preventiva,  
> **Para que** eu consiga programar meus gastos e agendar o serviço com antecedência.

### História 3
> **Como** usuário do aplicativo,  
> **Quero** marcar a manutenção como "Realizada" e atualizar a quilometragem do hodômetro,  
> **Para que** a contagem seja reiniciada e o histórico de manutenções anteriores fique registrado para consultas futuras.

---

## 6. Critérios de Aceitação

### Critério 1 (Referente à História 1)
- **Dado** que o usuário acessou a tela de cadastro do carro,
- **Quando** preencher os dados de "quilometragem atual", "quilometragem da última troca" e o intervalo do lubrificante (ex.: 10.000 km ou 12 meses),
- **Então** o sistema deve salvar as informações com sucesso e mostrar na tela inicial a previsão estimada para a próxima manutenção.

### Critério 2 (Referente à História 2)
- **Dado** que a quilometragem calculada atingir a margem de segurança (faltando 500 km) ou restarem 15 dias para o prazo final,
- **Quando** a rotina diária de verificação em segundo plano rodar,
- **Então** uma notificação push deve ser enviada para o celular alertando qual item precisa de atenção e o tempo restante.

### Critério 3 (Referente à História 3)
- **Dado** que o motorista realizou o serviço e abriu o alerta de manutenção pendente,
- **Quando** clicar no botão "Confirmar Troca Feita" e digitar a quilometragem atual do painel,
- **Então** o alerta atual deve ser movido para o histórico de revisões e a contagem do novo ciclo deve ser reiniciada do zero.
