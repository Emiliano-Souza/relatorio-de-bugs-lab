# Atividade: Primeiro Teste de Software

**Estudante:** Emiliano Ferreira de Souza Junior

**Curso e período:** Bacharelado em Sistemas  Informação, 8º período  

**Disciplina:** Teste de Software

## Sistema testado

SauceDemo — https://www.saucedemo.com/

O SauceDemo é uma loja virtual utilizada para praticar testes de software. Nesta atividade, foram realizados quatro casos de teste para verificar o funcionamento do login, do carrinho de compras e da exibição das imagens dos produtos.

## Classificação do teste realizado

- **Nível — Sistema:** os testes verificaram funcionalidades da loja por meio do navegador, considerando seu funcionamento como um todo.
- **Objetivo — Funcional:** foi verificado se as funcionalidades apresentavam os resultados esperados.
- **Visão do código — Caixa-preta:** os testes foram realizados sem acesso ao código-fonte, observando apenas as entradas e as respostas do sistema.
- **Execução — Dinâmico:** o sistema foi executado durante os testes para observar seu comportamento.
- **Modo — Manual:** as ações foram realizadas e os resultados conferidos manualmente.
- **Motivo — Teste novo:** foi a primeira execução planejada desses casos de teste, sem objetivo de verificar uma correção anterior.

## Casos de teste

Foram cadastrados quatro casos de teste no Qase, dentro do projeto E-Commerce-QA e da suíte Autenticação e Compras.

### CT-01 — Login com credenciais válidas

**Resultado: Passed**

O sistema permitiu o acesso utilizando credenciais válidas e apresentou a página de produtos.

<img width="2500" height="1408" alt="Screenshot 2026-11-18 095124" src="https://github.com/user-attachments/assets/082d754c-b4a9-4c6a-b5d6-c4f5ae91fef5" />

### CT-02 — Login com senha incorreta

**Resultado: Passed**

O sistema impediu o acesso com a senha incorreta e apresentou uma mensagem de erro.

<img width="2550" height="1428" alt="Screenshot 2026-11-18 095219" src="https://github.com/user-attachments/assets/4c96514a-3e86-4ebf-91f0-82cd86222e75" />

### CT-03 — Adicionar produto ao carrinho

**Resultado: Passed**

O produto Sauce Labs Backpack foi adicionado corretamente. O botão passou a mostrar Remove e o carrinho apresentou a quantidade 1.

<img width="2512" height="1418" alt="Screenshot 2026-11-18 095306" src="https://github.com/user-attachments/assets/c7d0f475-f880-44eb-b896-cc980342cdac" />

### CT-04 — Imagens dos produtos com o usuário problem_user

**Resultado: Failed**

Ao acessar a loja com o usuário `problem_user`, foi identificado que diferentes produtos apresentavam a mesma imagem de um cachorro, em vez das imagens correspondentes a cada item.

<img width="2546" height="1418" alt="Screenshot 2026-11-18 095428" src="https://github.com/user-attachments/assets/a12b2235-8acb-42a8-b929-27fb417a2204" />

## Execução

Os quatro casos foram executados no Qase, na execução **Execução de Testes - Ciclo 1**, em 18 de novembro de 2026.

**Resumo dos resultados:**

- Total de testes: 4
- Aprovados (Passed): 3
- Reprovados (Failed): 1
- Taxa de execução: 100%

<img width="2496" height="1378" alt="Screenshot 2026-11-18 093056" src="https://github.com/user-attachments/assets/e3c0eb78-0154-4aae-88bf-25d30d526795" />

## Defeito encontrado

Foi identificado um defeito na exibição das imagens dos produtos ao utilizar o usuário `problem_user`.

**Severidade:** Média  
**Prioridade:** Alta  
**Caso relacionado:** CT-04 (ECQ-4 no Qase)

O problema foi documentado em uma Issue no GitHub, contendo descrição, ambiente, passos para reprodução, resultados esperado e obtido e evidência visual.

**Issue #1:** https://github.com/Emiliano-Souza/relatorio-de-bugs-lab/issues/1

## Respostas às perguntas para refletir

### 1. Por que o resultado esperado é escrito antes de executar o teste?

Porque precisamos definir como o sistema deveria funcionar antes de observar seu comportamento. Isso evita que um resultado incorreto seja considerado normal e permite comparar o que era esperado com o que realmente aconteceu.

### 2. Qual a diferença entre o caso de teste (CT-04) e o relatório de defeito (a issue)? Por que precisamos dos dois?

O caso de teste descreve o que será verificado, quais passos devem ser seguidos e qual resultado é esperado. Já o relatório de defeito registra o problema encontrado durante a execução, explicando como reproduzi-lo e apresentando evidências.

Precisamos dos dois porque o caso orienta a verificação e o relatório ajuda a entender e corrigir o problema identificado.

### 3. Podemos afirmar que a loja não tem mais nenhum defeito além do que foi encontrado? Justifique.

Não. Os quatro casos verificaram apenas algumas funcionalidades da loja. Mesmo que três tenham passado, outras partes do sistema podem apresentar problemas que não foram identificados. Os testes mostram a existência de defeitos, mas não garantem que o software esteja livre de erros.

### 4. Se essa loja fosse da sua empresa, o que você testaria a seguir?

Eu testaria o processo de finalização da compra, verificando os campos obrigatórios, o preenchimento dos dados do cliente e o funcionamento do checkout. Também verificaria a ordenação dos produtos e o comportamento do carrinho ao adicionar e remover vários itens.

### 5. Classifique o teste deste guia nos seis critérios e justifique cada resposta.

A classificação está apresentada na seção **Classificação do teste realizado**, considerando os seis critérios: nível de sistema, objetivo funcional, visão de caixa-preta, execução dinâmica, modo manual e motivo de teste novo.

### 6. Por que ele não é um teste unitário nem um teste de carga?

Não é um teste unitário porque não foram verificadas funções ou partes isoladas do código. Os testes foram realizados utilizando a loja pelo navegador.

Também não é um teste de carga porque não houve simulação de vários usuários acessando o sistema ao mesmo tempo nem avaliação do comportamento da aplicação sob grande volume de acessos.

## Conclusão

A atividade permitiu executar um ciclo de testes de software, desde a elaboração dos casos até o registro de um defeito. Dos quatro testes realizados, três apresentaram o comportamento esperado e um identificou um problema nas imagens dos produtos.

O uso do Qase e do GitHub permitiu organizar os resultados, registrar evidências e relacionar o defeito ao caso de teste responsável por identificá-lo.
