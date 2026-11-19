# Caso de Uso: Solicitar Empréstimo

- **Ator principal:** Aluno
- **Atores de apoio:** Bibliotecário, Sistema de Pagamento
- **Descrição:** Permite que um aluno com matrícula ativa solicite o empréstimo de um livro disponível no acervo da biblioteca, registando o prazo de devolução e verificando pendências financeiras.
- **Gatilho:** O aluno seleciona um livro disponível no catálogo e aciona a opção de solicitar empréstimo no sistema.

## Pré-condições
- O aluno está autenticado e possui matrícula ativa no sistema.
- O livro selecionado consta como disponível no acervo.

## Pós-condições
- O empréstimo é registado no sistema com a data de retirada e a data prevista de devolução.
- O estado do exemplar do livro passa a emprestado.

## Fluxo principal
1. O aluno seleciona o livro desejado no catálogo e solicita o empréstimo.
2. O sistema verifica se o aluno possui multas pendentes consultando o **Sistema de Pagamento** e valida o limite de empréstimos ativos.
3. O sistema confirma a disponibilidade do exemplar selecionado.
4. O sistema regista o empréstimo, define o prazo de devolução e atualiza o estado do livro para emprestado.
5. O sistema apresenta o comprovativo do empréstimo ao aluno e notifica o **Bibliotecário** para entrega ou registo no balcão.

## Fluxo alternativo
- **Quando:** O aluno já atingiu o limite máximo de livros emprestados simultaneamente, mas não possui multas pendentes.
- **Passos:**
  1. O sistema identifica que o limite de empréstimos ativos do aluno foi atingido.
  2. O sistema informa ao aluno o limite máximo permitido e exibe a lista dos empréstimos ativos com as respetivas datas de devolução.
- **Retorno:** O caso de uso encerra sem registar um novo empréstimo, mantendo o aluno na tela de consulta do acervo.

## Exceção
- **Quando:** O aluno possui multa pendente ou o **Sistema de Pagamento** está indisponível durante a verificação.
- **Passos:**
  1. O sistema bloqueia a conclusão do pedido de empréstimo.
  2. O sistema exibe uma mensagem de alerta informando a existência de pendência financeira ou a indisponibilidade temporária da validação.
- **Retorno:** O empréstimo não é registado, o estado do livro permanece disponível e o fluxo retorna à tela inicial de consulta.
