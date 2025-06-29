# Projeto: Gerenciador de Tarefas v2.0

## 1. Visão Geral

Este é um projeto de um Gerenciador de Tarefas via terminal, desenvolvido em Python. A base do projeto oferece funcionalidades para adicionar, listar, concluir e remover tarefas. O objetivo deste trabalho é estender a funcionalidade do sistema e demonstrar um fluxo de trabalho de desenvolvimento profissional utilizando Git e GitHub.

## 2. Configuração Inicial

1.  **Fork:** Realize um fork deste repositório para a sua conta pessoal no GitHub.
2.  **Clone:** Clone o repositório que você criou (o seu fork) para o seu ambiente de desenvolvimento local.
    ```bash
    git clone [https://github.com/SEU-USUARIO/NOME-DO-REPOSITORIO.git](https://github.com/SEU-USUARIO/NOME-DO-REPOSITORIO.git)
    ```

## 3. Especificações da Tarefa

Você deve implementar as **duas** novas funcionalidades descritas abaixo.

### Funcionalidade 1: Prioridade de Tarefas

* **Estrutura de Dados:** A estrutura de dados de cada tarefa deve ser alterada para incluir um campo `prioridade`.
* **Adicionar Tarefa:** A função de adição deve ser modificada para solicitar ao usuário um nível de prioridade (`Alta`, `Média`, `Baixa`). Uma entrada inválida deve resultar na prioridade padrão `Baixa`.
* **Listar Tarefas:** A função de listagem deve ser atualizada para exibir a prioridade de cada tarefa.

### Funcionalidade 2: Edição de Descrição da Tarefa

* **Menu:** Uma nova opção para "Editar Tarefa" deve ser adicionada ao menu principal.
* **Implementação:** Deve ser criada uma função que permita ao usuário:
    1.  Selecionar uma tarefa existente pelo seu índice.
    2.  Visualizar a descrição atual.
    3.  Inserir uma nova descrição para substituí-la.
* **Feedback:** O sistema deve informar ao usuário se a operação foi bem-sucedida.

## 4. Requisitos de Entrega e Fluxo de Trabalho

A avaliação levará em conta a organização do seu repositório e o uso correto das ferramentas.

* **README.md:** Este arquivo deve ser atualizado com a seção "Minhas Contribuições" devidamente preenchida.
* **`.gitignore`:** O repositório precisa conter um arquivo `.gitignore` configurado adequadamente para projetos Python, ignorando arquivos e pastas como `__pycache__` e `venv/`.
* **Fluxo com Branches:** Cada uma das duas funcionalidades deve ser desenvolvida em uma *feature branch* separada (ex: `feature/task-priority` e `feature/edit-task-description`). Após a finalização, cada branch deve ser mesclada (`merge`) de volta à branch `main`.
* **Histórico de Commits:** É exigido um histórico com um mínimo de **8 a 10 commits atômicos**. As mensagens de commit devem ser claras e refletir o trabalho realizado em cada etapa.

## 5. Critérios de Avaliação

* **README:** Clareza e detalhamento da seção "Minhas Contribuições".
* **Git:** Qualidade das mensagens de commit e demonstração do fluxo de trabalho com branches e merges.
* **Funcionalidade:** Implementação correta e funcional das modificações solicitadas.
* **Código:** Legibilidade, organização e qualidade geral do código implementado.

---


**Nome:** Mateus Silveira Vicente  
**GitHub:** [https://github.com/DevMateusVicente06](https://github.com/DevMateusVicente06)

**Modificação 1 – Prioridade**
Para implementar a funcionalidade de prioridade, comecei alterando a função adicionar_tarefa para que ela também recebesse um terceiro parâmetro chamado prioridade. Isso foi necessário para que, no momento em que o usuário cria uma nova tarefa, ele possa informar se ela é de prioridade alta, média ou baixa.

Dentro da função, criei uma estrutura condicional que verifica qual foi a prioridade digitada pelo usuário. Se ele digitar corretamente "alta", "media" ou "baixa", o programa associa (alta, média, baixa) e define a prioridade correspondente. Caso o usuário digite algo fora do esperado, a prioridade padrão atribuída será baixa, como forma de segurança.

Também adicionei o campo "prioridade" ao dicionário de cada tarefa. Assim, agora cada tarefa tem três informações principais: "descricao", "concluida" e "prioridade". Isso faz com que o sistema fique mais organizado e completo.

Além disso, atualizei a função listar_tarefas para que, ao mostrar as tarefas ao usuário, a prioridade de cada uma apareça ao lado da descrição.

**Como Testar:**
1. Execute o programa ("python nome_do_arquivo.py").
2. Escolha a opção "1. Adicionar Tarefa".
3. Insira uma descrição qualquer.
4. Quando solicitado, digite uma prioridade (ex: "alta", "media", "baixa").
5. Escolha a opção "2. Listar Tarefas" para verificar se a tarefa foi adicionada com a prioridade correta.
6. Teste digitar uma prioridade inválida (ex: "urgente") e veja se a prioridade foi definida como "Baixa".

**Lógica usada para a prioridade**
A ideia da prioridade surgiu como uma condição dentro do meu código. Por isso, utilizei estruturas do tipo if, elif e else para verificar o que o usuário digitou e aplicar a prioridade correta. Essa parte exigiu atenção, já que precisava lidar com possíveis erros de digitação.

Depois de definir bem essa lógica, o resto foi aplicar a variável prioridade nos pontos certos do código: dentro da função que adiciona a tarefa, e também na função que exibe as tarefas. Assim, garanti que o usuário veja essa informação tanto na criação quanto na listagem das tarefas.


**Modificação 2 – Editar Descrição da Tarefa**
Para implementar a função de edição de descrição, primeiramente criei uma nova função chamada editar_descricao, que recebe dois parâmetros: a lista de tarefas e o índice da tarefa a ser modificada.

Essa função começa identificando o índice correto na lista (ajustando para começar do 0). Em seguida, verifica se esse índice é válido dentro da lista. Caso seja, o programa solicita ao usuário uma nova descrição e uma nova prioridade para a tarefa.

Com isso, atualizei os dois campos no dicionário daquela tarefa: "descricao" e "prioridade". Além disso, criei uma nova opção no menu principal (opção 5) chamada “Editar Descrição da Tarefa”, permitindo ao usuário acessar essa funcionalidade facilmente.

**Lógica usada para a edição**
Assim como na modificação anterior, aqui também utilizei condicionais if para garantir que o índice informado seja válido e que a nova descrição não seja vazia. Para garantir que a prioridade seja tratada corretamente, reaproveitei a lógica já usada anteriormente com as prioridades (alta, media, baixa), mantendo o código coerente e reaproveitável.

Essa abordagem tornou o código mais funcional e permitiu ao usuário alterar tarefas de forma prática, sem precisar removê-las e criá-las novamente.

**Como Testar:**
1. Execute o programa.
2. Use a opção "1" para adicionar ao menos duas tarefas.
3. Use a opção "2" para listar as tarefas e ver os números delas.
4. Escolha a opção "5. Editar Descrição de Tarefa".
5. Digite o número da tarefa que deseja alterar.
6. Digite a nova descrição e uma nova prioridade.
7. Use novamente a opção "2" para listar e confirmar se a edição foi aplicada corretame


