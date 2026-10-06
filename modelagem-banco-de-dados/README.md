# Entrega-1-Modelo-Conceitual-DER
Modelagem de um sistema de gestão de informações para uma organização de pequeno porte    
## Metadados
**João Vitor Silva Alves Araujo RGM: 46905570**

**Raimundo Walter RGM: 46852042**

**Kaique Vieira Santos RGM: 47022493**

**Vítor Bezerra Marques RGM: 47538775**
****
# 1. Caracterização da Organização

- **Nome e natureza da organização:** Peg Vest Jeans — empresa especializada na comercialização de jeans feminino no segmento de atacado.
- **Contexto e porte:** Com fins lucrativos; pequena empresa; 20 pessoas envolvidas, volume de atividades média 
- **Problemas e necessidades identificados:** Dificuldade de controle de estoque, padronizações e processos, necessidade do uso de outros sistemas para diferentes canais de vendas, não totalmente compatíveis 
- **Justificativa da escolha:** A Peg Vest Jeans foi escolhida porque um membro de nossa equipe trabalha no local e possui proximidade com a área e facil acesso ao local e, também, por se encaixar nos parâmetros estabelecidos para a escolha da organização.
- **Evidências da organização:**
  
    Endereço : R. Rodrigues dos Santos, 718
  
    Link Google Maps: https://share.google/DAEpR3k6h6TCqBPD0

    Link site da loja: https://pegvest.com.br/
  
    Contato: (11) 96173-2019
  
    Imagens Do local:

  <img width="382" height="510" alt="image" src="https://github.com/user-attachments/assets/eb38a776-4753-43cc-a795-d5f32b7f5d3a" />

    Foto Da Entrevista:
  
  <img width="382" height="510" alt="image" src="https://github.com/user-attachments/assets/49514ebb-dc71-494b-8eb8-c0ae2eaa4e55" />
  <img width="382," height="510" alt="image" src="https://github.com/user-attachments/assets/46031314-3464-46a9-a30a-425d2cd8fb3d" />



  
# 2. Processos de Negócio

- **Principais processos mapeados:** cadastro de clientes, controle de estoque, vendas, emissão de pedidos e solicitações, entregas e transferências
---
## 3. Requisitos do Sistema


### 3.1 Requisitos Funcionais
- **Cadastrar clientes → O sistema deve permitir cadastrar nome, CPF, telefone e endereço do cliente.**
- **Cadastrar produtos → O sistema deve permitir cadastrar produtos com nome, preço e quantidade em estoque.**
- **Realizar vendas → O sistema deve permitir que o funcionário registre uma venda para um cliente.**
- **Consultar estoque → O sistema deve permitir consultar a quantidade disponível de cada produto.**
- **Atualizar estoque → Após uma venda, o sistema deve diminuir automaticamente a quantidade do produto no estoque**
- **Gerar nota fiscal → O sistema deve permitir gerar a nota fiscal referente à venda.**
- **Realizar login → O sistema deve permitir que funcionários façam login utilizando usuário e senha.**
- **Gerar relatórios → O sistema deve permitir gerar relatórios de vendas por período.**
- **Cancelar uma venda → O sistema deve permitir que um funcionário autorizado cancele uma venda.**
- **Enviar notificações → O sistema deve enviar uma notificação quando determinado produto estiver com estoque baixo**
---
### 3.2 Requisitos Não Funcionais
- **Desempenho → O sistema deve apresentar tempo de resposta adequado durante a verificação e consulta de produtos.**
- **Segurança → Cada usuário deve ter acesso restrito à sua área de atuação; apenas o gerente possui acesso a senhas e preços, sendo que qualquer desconto ou alteração de valor só pode ocorrer mediante confirmação da gerência.**
- **Disponibilidade → Os pontos de venda físicos só podem ser acessados localmente, dentro da empresa e em horário de funcionamento; já os relatórios de vendas podem ser acessados remotamente via web.**
- **Usabilidade → O sistema deve permitir consulta automática ao cadastro de clientes, preenchendo automaticamente os demais dados a partir do CNPJ informado.**
- **Backup → O sistema deve sincronizar o banco de dados local com a nuvem, permanecendo disponível localmente mesmo em caso de falha de conexão com a internet; após o retorno da conexão, os dados devem ser sincronizados automaticamente.**
- **Compatibilidade → O sistema deve ser compatível com os principais navegadores e dispositivos.** 
- **Escalabilidade → O sistema deve suportar até 1.000 usuários simultâneos.**
- **Manutenibilidade → O sistema deve possuir partes customizáveis e permitir controle total das permissões de configuração de acesso, organizadas por módulos.** 
- **Confiabilidade → O sistema deve realizar backup automático e local dos dados diariamente.**

---
# 4. Regras de Negócio

- ## 4.1 Regras operacionais:
- #### Cadastro 
  O cadastro de clientes deve possuir os dados obrigatórios definidos pela empresa, incluindo CPF para clientes pessoa física e CNPJ para clientes pessoa jurídica.*
- #### Pagamento
  Uma compra somente pode ser considerada efetuada após a confirmação do pagamento.*
  
  O pedido não deve ser liberado para as etapas seguintes enquanto o pagamento não estiver confirmado.
- #### Desconto
  Compras realizadas por meio de Pix possuem desconto de 5% sobre o valor da compra.
  
  O desconto deve ser aplicado somente quando a forma de pagamento selecionada for Pix.
  
  Funcionários não possuem permissão para conceder descontos diferentes dos definidos pela empresa.
  

- #### Estoque 
  Um produto não pode ser vendido quando não houver quantidade disponível em estoque.
  
  Após a confirmação de uma venda, a quantidade correspondente deve ser atualizada no estoque.
  
  A quantidade disponível de um produto não pode assumir valores negativos.
- #### Cancelamento
  Um pedido pode ser cancelado somente enquanto não tiver sido enviado.
  
  Após o envio do pedido, o cancelamento não poderá ser realizado pelo fluxo normal do sistema.
- #### Vendas no atacado e varejo
  Nas vendas realizadas no atacado, os pedidos devem respeitar uma quantidade mínima de 15 peças.
  
  As vendas no varejo não possuem quantidade mínima de peças.
  
  Os preços praticados no varejo são superiores aos preços utilizados nas vendas no atacado, conforme a política comercial da empresa.
- #### Funcionarios
  Funcionários não podem alterar os preços dos produtos.
  
  Funcionários não podem conceder descontos que não estejam previamente definidos pela empresa.
  
  Vendedores somente podem liberar uma entrega mediante autorização da gerência.
  
  Alterações que afetem configurações ou regras comerciais do sistema devem ser realizadas somente por usuários autorizados*
  
- ## Restrições organizacionais:
- ### Permissões de acesso
  Cada usuário deve possuir acesso somente aos módulos do sistema correspondentes à sua função, como vendas, estoque, financeiro ou administração.
  
  O acesso às funcionalidades do sistema deve ser controlado de acordo com o nível de permissão de cada usuário.
  
  Funcionários do setor de vendas, por exemplo, não devem possuir acesso às configurações administrativas ou informações restritas do setor financeiro.
  
- ### Administração do sistema
  Somente o administrador possui permissão para alterar determinadas configurações do sistema.
  
  Usuários comuns não podem modificar configurações administrativas sem autorização.
  
  Alterações relacionadas às configurações do sistema, permissões de usuários e regras internas devem ser realizadas somente por funcionários autorizados
  
- ### Backup
  Os dados do sistema devem possuir backup realizado diariamente, conforme a política interna da empresa.
  
  Os backups devem preservar informações como clientes, produtos, estoque, pedidos, vendas e pagamentos.
  
  Os backups têm como objetivo possibilitar a recuperação dos dados em caso de falhas, perda de informações ou problemas no sistema.
  
- ### Dados dos clientes
  Somente funcionários autorizados podem acessar os dados cadastrais dos clientes.
  
  O acesso às informações dos clientes deve respeitar as permissões definidas pela empresa.
  
  Funcionários que não necessitam dessas informações para realizar suas atividades não devem possuir acesso aos dados cadastrais dos clientes.
  
  As informações dos clientes devem ser utilizadas somente para as atividades relacionadas ao funcionamento da loja.

---
# 5. Dicionário de Dados Conceitual (Preliminar) 

---

### Relação entre o Dicionário de Dados e as Regras de Negócio

Os atributos apresentados foram definidos considerando as regras de funcionamento da loja. Dessa forma, o dicionário serve como uma base para a construção do modelo conceitual e das próximas etapas da modelagem do banco de dados.

As principais relações são:

* **Funcionário → Pedido:** identifica o funcionário responsável pelo pedido e permite aplicar as regras de permissão.
* **Cliente → Pedido:** identifica o cliente que realizou o pedido.
* **Pedido → Pagamento:** permite controlar a confirmação do pagamento.
* **Produto → Estoque:** permite controlar a quantidade disponível de cada produto.
* **Fornecedor → Produto:** identifica o fornecedor responsável pelo fornecimento dos produtos.
* **Pedido → Produto:** permite identificar os produtos pertencentes a cada pedido.
* **Empresa → Funcionário:** relaciona os funcionários à empresa.

Os exemplos de valores eventualmente utilizados para representar os atributos devem ser fictícios e servir apenas para ilustrar o funcionamento do sistema, não devendo ser utilizados dados reais de clientes, funcionários ou fornecedores.


---
# 6. Modelagem Conceitual (Entidades, Atributos, Relacionamentos)
### 6.1 Entidades reconhecidas
 Entidade | Justificativa |
|---|---|
| **Funcionário** | Representa os colaboradores da empresa que realizam atendimentos e processam pedidos. Necessário para controle de responsabilidade e rastreabilidade das operações. |
| **Cliente** | Representa as pessoas físicas ou jurídicas que efetuam compras. Essencial para o relacionamento comercial e emissão de pedidos. |
| **Empresa** | Representa a organização proprietária do sistema (dados institucionais/fiscais), usada como referência corporativa (ex: emissão de documentos fiscais). |
| **Estoque** | Controla a quantidade física disponível de cada produto, permitindo gestão de reposição e disponibilidade para venda. |
| **Pedido** | Registra as transações de venda realizadas entre cliente e empresa, intermediadas por um funcionário. |
| **Fornecedor** | Representa as entidades externas responsáveis pelo fornecimento de produtos, necessário para reposição de estoque. |
| **Pagamento** | Registra as transações financeiras associadas a um pedido, permitindo controle de recebimentos. |
| **Produto** | Representa os itens comercializáveis pela empresa, base para pedidos, estoque e fornecimento. | 

### 6.2 Relacionamentos Pertinentes

| Relacionamento | Cardinalidade | Descrição |
|---|---|---|
| **Empresa — Funcionário** | 1:N | Uma empresa possui vários funcionários vinculados a ela; cada funcionário pertence a uma única empresa. |
| **Empresa — Cliente** | 1:N | Uma empresa atende vários clientes; cada cliente é atendido por uma empresa. |
| **Empresa — Pedido** | 1:N | A empresa registra inúmeros pedidos no sistema. |
| **Empresa — Estoque** | 1:1 | A empresa controla/possui um estoque; cada registro de estoque pertence a uma única empresa. |
| **Empresa — Fornecedor** | 0:N | Uma empresa pode se relacionar com vários fornecedores. |
| **Funcionário — Pedido** | 1:N | Um funcionário pode registrar/atender vários pedidos; cada pedido é atendido por apenas um funcionário. |
| **Cliente — Pedido** | 1:N | Um cliente pode realizar vários pedidos; cada pedido pertence a um único cliente. |
| **Pedido — Pagamento** | 1:N | Um pedido pode ter um ou mais pagamentos (ex: parcelamento); cada pagamento está vinculado a um único pedido. |
| **Produto — Estoque** | 1:1 | Cada produto possui um registro de controle de estoque associado. |
| **Fornecedor — Produto** | 1:N | Um fornecedor pode fornecer um ou vários produtos, e um produto pode ser fornecido por um ou vários fornecedor  |



## 6.3 Restrições e Políticas Organizacionais

- **Integridade referencial:** todo `id_cliente`, `id_funcionario`, `id_produto` e `id_pedido` referenciado em outra entidade deve existir previamente na entidade de origem (não é permitido pedido órfão sem cliente ou funcionário válido).
- **Unicidade:** os campos `cpf` (Funcionário), `cpf_cnpj` (Cliente), `cnpj` (Empresa e Fornecedor) devem ser únicos no sistema, evitando duplicidade de cadastro.
- **Status obrigatório:** entidades como Funcionário, Cliente e Fornecedor possuem o atributo `status`, permitindo inativação lógica em vez de exclusão física dos registros (soft delete), preservando o histórico de pedidos e pagamentos.
- **Controle de estoque mínimo:** o atributo `quantidade_minima` deve ser utilizado como gatilho de alerta para reposição junto a fornecedores, impedindo venda quando `quantidade_disponivel` for insuficiente.
- **Consistência financeira:** o `valor_total` do Pedido deve ser validado em relação à soma dos valores pagos em Pagamento, considerando o `desconto_aplicado`.
- **Rastreabilidade:** todo pedido deve manter o vínculo com o funcionário responsável pelo atendimento, para fins de auditoria e avaliação de desempenho.
- **Confidencialidade de dados:** informações pessoais (CPF, telefone, email) devem seguir políticas de proteção de dados (ex: LGPD), com acesso restrito conforme perfil do usuário do sistema.

### Permissões de acesso
- Cada usuário/funcionário deve ter acesso apenas aos módulos correspondentes à sua função (vendas, estoque, financeiro ou administração).
- O acesso às funcionalidades do sistema é controlado conforme o nível de permissão associado ao cargo/perfil do funcionário.
- Funcionários do setor de vendas não possuem acesso a configurações administrativas nem a informações restritas do setor financeiro.

### Administração do sistema
- Somente o administrador possui permissão para alterar configurações do sistema.
- Usuários comuns não podem modificar configurações administrativas sem autorização prévia.
- Alterações em configurações do sistema, permissões de usuários e regras internas devem ser realizadas exclusivamente por funcionários autorizados.

### Backup
- Os dados do sistema devem possuir backup diário, conforme política interna da empresa.
- Os backups devem preservar informações de Clientes, Produtos, Estoque, Pedidos, Vendas e Pagamentos.
- O backup tem como finalidade permitir a recuperação de dados em caso de falhas, perda de informações ou problemas no sistema.

### Dados dos clientes
- Somente funcionários autorizados podem acessar os dados cadastrais dos clientes.
- O acesso às informações dos clientes deve respeitar as permissões definidas pela empresa, restritas conforme a necessidade da função exercida.
- Funcionários que não necessitam dessas informações para desempenhar suas atividades não devem ter acesso aos dados cadastrais dos clientes.
- As informações dos clientes devem ser utilizadas exclusivamente para atividades relacionadas ao funcionamento da loja, não podendo ser compartilhadas com terceiros ou usadas para finalidades diversas.
---

# 7. Diagrama Entidade-Relacionamento (DER)
Anexado ao reposiório

---

## 8. Justificativa Técnica

A estrutura do modelo foi definida com base nos principais processos que identificamos na Peg Vest Jeans, focando em representar no banco de dados apenas os dados que realmente fazem parte da rotina da empresa. Por isso, modelamos entidades para clientes, funcionários, produtos, estoque e para as operações de venda e pedido, afinal, são esses pontos que sustentam o cadastro, a venda, o controle de estoque, o envio de pedidos, as entregas e as transferências.

Para a definição dos atributos, o foco foi guardar só o que é necessário para cada entidade. No caso de clientes, por exemplo, colocamos dados essenciais como nome, CPF, telefone e endereço; já para produtos, mantivemos as informações de cadastro, preço e quantidade em estoque. Essa divisão é importante para manter o banco organizado e evitar colocar dados de contextos diferentes dentro de uma mesma tabela.

Os relacionamentos e as cardinalidades foram mapeados seguindo o fluxo de trabalho da loja. Um cliente pode fazer várias compras ao longo do tempo, e os funcionários entram registrando e finalizando o atendimento. Os produtos se conectam tanto ao estoque quanto às vendas, o que permite checar a disponibilidade e dar baixa nos itens assim que uma venda é concluída. Com isso, as ligações refletem a lógica do negócio sem criar vínculos desnecessários no esquema.

No fim, a ideia dessa modelagem foi evitar uma complexidade desnecessária, mantendo os dados bem separados pela sua finalidade. O resultado é uma estrutura bem organizada, que reflete os processos atuais da Peg Vest Jeans e serve como uma base sólida para as próximas fases do projeto.

---

## 9. Uso de Inteligência Artificial


| Item | O que registrar |
|------|------------------|
| **Ferramenta e etapa** | ChatGPT e Claude - utilizado na etapa de Modelagem Conceitual (Entidades, Atributos, Relacionamentos e Cardinalidades), para apoiar a definição do modelo de dados a partir dos requisitos e regras de negócio já levantados pelo grupo. |
| **Motivação** | Nosso grupo já havia levantado os processos de negócio, requisitos funcionais e regras de negócio da Peg Vest Jeans, mas tinha dúvidas sobre quais entidades, atributos e relacionamentos seriam mais adequados para representar esse cenário em um modelo conceitual, e queria um direcionamento inicial sobre cardinalidades e sobre o que deveria ou não entrar no DER. |
| **Prompt(s) utilizados** | Estamos desenvolvendo um sistema para a empresa Peg Vest Jeans (...) Com base exclusivamente nessas informações, identifique as entidades necessárias para um modelo conceitual de banco de dados, seus principais atributos, os relacionamentos entre elas e as respectivas cardinalidades. Explique também quais entidades devem ser consideradas no DER e quais conceitos devem permanecer apenas como contexto do sistema. |
| **Resposta recebida** | A IA sugeriu 8 entidades (Funcionário, Cliente, Empresa, Estoque, Pedido, Fornecedor, Pagamento e Produto), com seus respectivos atributos e justificativas de uso, além dos relacionamentos entre elas com cardinalidades (ex: Funcionário–Pedido 1:N, Cliente–Pedido 1:N, Pedido–Pagamento 1:N, Produto–Estoque 1:1, Fornecedor–Produto N:M, Empresa–Pedido 1:N), e recomendou considerar "Empresa" apenas como referência institucional, sem tratá-la como parte operacional do fluxo de vendas. |
| **Fontes consultadas e verificadas** | A resposta da IA foi confrontada com os processos de negócio, requisitos funcionais e regras de negócio já levantados diretamente com a Peg Vest Jeans pelo grupo, garantindo que as entidades e relacionamentos sugeridos realmente refletissem a rotina da empresa. |
| **Trechos rejeitados ou corrigidos** | Algumas sugestões apresentadas pela IA não foram utilizadas ou precisaram ser adaptadas, principalmente quando não correspondiam ao que havia sido identificado pelo grupo durante o desenvolvimento do trabalho. |
| **Justificativa da escolha final** | Nós utilizamos a sugestão da IA como ponto de partida, mas validou cada entidade, atributo e relacionamento com base no conhecimento prático sobre a rotina da Peg Vest Jeans, ajustando o que fosse necessário para refletir com mais precisão os processos reais da empresa antes de incluir no modelo final. |
| **Reflexão crítica** | Utilizamos a IA para nos ajudar a organizar rapidamente um primeiro esboço da modelagem conceitual e a pensar em pontos como escalabilidade e integração futura, mas o grupo percebeu a necessidade de revisar as sugestões à luz da realidade específica da organização, já que a IA não teve acesso direto ao contexto real da loja. |
