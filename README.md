# Atividade: Primeiro Teste de Software

**Estudante:** Emiliano Ferreira de Souza Junior
**Curso e período:** Bacharelado em Sistemas de Informação — 8º período  
**Disciplina:** Teste de Software  
**Data da execução:** 18/11/2026

---

## 1. Sistema testado

**Sistema:** [SauceDemo](https://www.saucedemo.com/)

O SauceDemo é uma loja virtual fictícia utilizada para treinamento em testes de software.

Nesta atividade, foram realizados testes funcionais para verificar o comportamento do login, da adição de produtos ao carrinho e da exibição das imagens dos produtos.

Os casos foram organizados e executados no **Qase**, enquanto o **GitHub** foi utilizado para documentar o defeito identificado e armazenar as evidências.

## 2. Classificação do teste realizado

Os testes realizados possuem as seguintes classificações:

| Critério | Classificação | Justificativa |
|---|---|---|
| Nível | Sistema | As funcionalidades foram verificadas por meio da interface da loja, considerando seu funcionamento como um todo. |
| Objetivo | Funcional | Foi avaliado se o sistema apresentava o comportamento esperado em cada funcionalidade testada. |
| Visão do código | Caixa-preta | Os testes foram realizados sem acesso ao código-fonte, utilizando apenas as entradas e os resultados apresentados pela aplicação. |
| Execução | Dinâmico | O sistema foi executado durante os testes para observar seu comportamento. |
| Modo | Manual | Os procedimentos foram executados e conferidos manualmente, sem scripts de automação. |
| Motivo | Teste novo | Foi realizada a primeira execução planejada dos casos, sem o objetivo de confirmar uma correção anterior. |

Portanto, a atividade corresponde a testes **manuais, funcionais, dinâmicos e de caixa-preta, no nível de sistema**.

## 3. Planejamento e casos de teste

Os casos foram cadastrados no Qase com a seguinte organização:

- **Projeto:** E-Commerce-QA
- **Código:** ECQ
- **Suíte:** Autenticação e Compras
- **Execução:** Execução de Testes - Ciclo 1
- **Total de casos:** 4

Foram utilizados testes positivos e negativos, incluindo credenciais válidas e inválidas. Essa escolha permite verificar tanto o funcionamento normal da aplicação quanto sua resposta a entradas incorretas.

### CT-01 — Login com credenciais válidas

**Identificação no Qase:** ECQ-1  
**Tipo:** Positivo  
**Status:** Passed

**Objetivo:** verificar se o sistema permite a autenticação com credenciais válidas.

**Resultado esperado:** o usuário deve ser autenticado e direcionado à página de produtos, identificada pelo título *Products*.

**Resultado obtido:** o login foi realizado corretamente e a página de produtos foi apresentada.

**Evidência do caso de teste:**

<img width="2500" height="1408" alt="Screenshot 2026-11-18 095124" src="https://github.com/user-attachments/assets/082d754c-b4a9-4c6a-b5d6-c4f5ae91fef5" />

### CT-02 — Login com senha incorreta

**Identificação no Qase:** ECQ-2  
**Tipo:** Negativo  
**Status:** Passed

**Objetivo:** verificar se o sistema impede a autenticação quando a senha informada está incorreta.

**Resultado esperado:** o usuário deve permanecer na tela de login e receber uma mensagem informando que as credenciais não correspondem a uma conta válida.

**Resultado obtido:** o acesso foi recusado e a mensagem de erro foi apresentada, conforme esperado.

**Evidência do caso de teste:**

<img width="2550" height="1428" alt="Screenshot 2026-11-18 095219" src="https://github.com/user-attachments/assets/4c96514a-3e86-4ebf-91f0-82cd86222e75" />

### CT-03 — Adicionar produto ao carrinho

**Identificação no Qase:** ECQ-3  
**Tipo:** Positivo  
**Status:** Passed

**Objetivo:** verificar se o produto Sauce Labs Backpack pode ser adicionado corretamente ao carrinho.

**Resultado esperado:** após adicionar o produto, o botão deve mudar de *Add to cart* para *Remove*, e o ícone do carrinho deve mostrar a quantidade 1.

**Resultado obtido:** o botão passou a apresentar *Remove*, o carrinho indicou um item e o produto foi exibido corretamente na página do carrinho.

**Evidência do caso de teste:**

<img width="2512" height="1418" alt="Screenshot 2026-11-18 095306" src="https://github.com/user-attachments/assets/c7d0f475-f880-44eb-b896-cc980342cdac" />

### CT-04 — Imagens dos produtos com o usuário problem_user

**Identificação no Qase:** ECQ-4  
**Tipo:** Positivo  
**Status:** Failed

**Objetivo:** verificar se as imagens apresentadas na listagem correspondem aos respectivos produtos.

**Resultado esperado:** cada produto deve apresentar uma imagem correspondente ao seu nome e às suas características.

**Resultado obtido:** ao entrar com o usuário `problem_user`, diferentes produtos apresentaram a mesma imagem de um cachorro, independentemente do item anunciado.

**Evidência do caso de teste:**

<img width="2546" height="1418" alt="Screenshot 2026-11-18 095428" src="https://github.com/user-attachments/assets/a12b2235-8acb-42a8-b929-27fb417a2204" />

O resultado diferente do esperado foi registrado como defeito no GitHub.

## 4. Execução dos testes

A execução foi realizada no Qase em **18 de novembro de 2026**, utilizando o ciclo denominado *Execução de Testes - Ciclo 1*.

### Resumo da execução

| Caso de teste | Resultado |
|---|---|
| CT-01 — Login com credenciais válidas | Passed |
| CT-02 — Login com senha incorreta | Passed |
| CT-03 — Adicionar produto ao carrinho | Passed |
| CT-04 — Imagens dos produtos | Failed |

**Indicadores da execução:**

| Indicador | Resultado |
|---|---|
| Casos executados | 4 |
| Casos aprovados | 3 |
| Casos reprovados | 1 |
| Taxa de execução | 100% |
| Taxa de aprovação | 75% |
| Taxa de reprovação | 25% |

Os quatro casos foram executados. Três apresentaram os resultados esperados, enquanto o CT-04 identificou uma falha na exibição das imagens dos produtos.

O status geral da execução foi **Failed**, devido à reprovação do CT-04.

### Evidência da execução

A captura abaixo apresenta o resumo do Qase, com os quatro casos executados e seus respectivos resultados.

<img width="2560" height="1422" alt="image" src="https://github.com/user-attachments/assets/8ca376ad-34e2-463c-9268-63cbfd9d0e0e" />

## 5. Defeito encontrado

**Título:** [BUG] Produtos: todas as imagens iguais ao logar com problem_user

**Caso relacionado:** CT-04 / ECQ-4  
**Severidade:** Média  
**Prioridade:** Alta

### Descrição

Durante a execução do CT-04, foi identificado que a página de produtos apresentava a mesma imagem de um cachorro em diferentes itens quando acessada com o usuário `problem_user`.

O problema foi observado, entre outros, nos produtos Sauce Labs Backpack, Sauce Labs Bike Light, Sauce Labs Bolt T-Shirt e Sauce Labs Fleece Jacket.

### Resultado esperado

Cada produto deve apresentar sua imagem correspondente, permitindo que o usuário identifique visualmente o item anunciado.

### Resultado obtido

Produtos diferentes apresentaram a mesma imagem, sem correspondência com seus nomes e descrições.

### Impacto

O defeito prejudica a identificação visual dos produtos e pode comprometer a decisão de compra do usuário.

A severidade foi classificada como **média**, pois a loja continua acessível, mas uma funcionalidade importante apresenta comportamento incorreto.

A prioridade foi definida como **alta**, considerando a importância das imagens na apresentação dos produtos.

### Registro do defeito

O problema foi documentado na Issue #1 do GitHub, com os passos para reprodução, os resultados esperado e obtido e a evidência visual.

**[Acessar o relatório do defeito — Issue #1](https://github.com/Emiliano-Souza/relatorio-de-bugs-lab/issues/1)**

## 6. Rastreabilidade

A rastreabilidade permite relacionar o caso de teste que identificou a falha ao relatório utilizado para documentá-la.

| Elemento | Referência |
|---|---|
| Caso de teste | CT-04 |
| Identificação no Qase | ECQ-4 |
| Execução | Execução de Testes - Ciclo 1 |
| Resultado | Failed |
| Relatório de defeito | [GitHub Issue #1](https://github.com/Emiliano-Souza/relatorio-de-bugs-lab/issues/1) |

O resultado do ECQ-4 contém a referência à Issue no GitHub, permitindo consultar o defeito a partir da execução. A Issue também identifica o caso de teste relacionado.

## 7. Respostas às perguntas para refletir

### 1. Por que o resultado esperado é escrito antes de executar o teste?

Porque é necessário definir previamente qual deve ser o comportamento correto do sistema. Se o resultado esperado fosse escrito depois da execução, poderíamos acabar considerando normal um comportamento que, na verdade, é um defeito. Defini-lo antes permite fazer uma comparação mais confiável.

### 2. Qual a diferença entre o caso de teste (CT-04) e o relatório de defeito (a issue)? Por que precisamos dos dois?

O caso de teste apresenta as condições, os passos e o resultado esperado de uma verificação. Já o relatório de defeito documenta o problema encontrado, mostrando o que aconteceu, como reproduzir o erro e quais evidências foram coletadas.

Os dois são necessários porque cumprem funções diferentes: o caso de teste orienta a execução, enquanto a issue fornece informações para analisar e corrigir a falha.

### 3. Podemos afirmar que a loja não tem mais nenhum defeito além do que foi encontrado? Justifique.

Não. Foram executados apenas quatro casos de teste, que abrangem uma parte das funcionalidades da loja. Mesmo com três resultados positivos, ainda podem existir problemas em outras situações que não foram verificadas.

Os testes ajudam a encontrar defeitos, mas não comprovam que um sistema esteja completamente livre deles.

### 4. Se essa loja fosse da sua empresa, o que você testaria a seguir?

Eu priorizaria o processo de checkout, verificando os campos obrigatórios, o preenchimento dos dados do cliente e a conclusão do pedido. Também testaria a ordenação dos produtos e a adição e remoção de vários itens do carrinho.

Essas funcionalidades fazem parte do processo de compra e podem afetar diretamente a experiência do cliente.

### 5. Classifique o teste deste guia nos seis critérios e justifique cada resposta.

A classificação completa está apresentada na **seção 2 — Classificação do teste realizado**.

O teste foi classificado como:

- **Sistema:** verifica o comportamento da loja por meio do navegador.
- **Funcional:** avalia se as funcionalidades apresentam os resultados esperados.
- **Caixa-preta:** não exige conhecimento ou acesso ao código-fonte.
- **Dinâmico:** depende da execução da aplicação.
- **Manual:** as ações e verificações são realizadas por uma pessoa.
- **Teste novo:** corresponde à primeira execução planejada dos casos.

### 6. Por que ele não é um teste unitário nem um teste de carga?

Não é um teste unitário porque não foram verificadas funções isoladas ou componentes internos do código. Os testes avaliaram o comportamento da aplicação por meio de sua interface.

Também não é um teste de carga porque não houve simulação de muitos usuários acessando o sistema simultaneamente nem avaliação de seu comportamento sob grande volume de requisições.

## 8. Conclusão

A atividade permitiu realizar as principais etapas de um ciclo de testes de software: planejamento, elaboração dos casos, execução, comparação dos resultados e documentação de um defeito.

Os quatro casos foram executados, sendo três aprovados e um reprovado. A falha identificada na exibição das imagens foi documentada no GitHub e relacionada ao respectivo caso de teste no Qase.

O processo demonstrou a importância de definir resultados esperados antes da execução, registrar evidências e manter a rastreabilidade entre testes e defeitos.
