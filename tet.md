# Criar Process Extension Scenario

Este documento tem como objetivo demonstrar o passo a passo da criação de Process Extension Scenario no SDK.

# Passo a Passo

## Criar Process Extension Scenario

1. Abrir o SDK, no *Solution Explorer*, botão direito no projeto e selecione *Add -> New Item*

![image](https://user-images.githubusercontent.com/42722229/154365901-2aad43ec-987e-4c31-abf4-9e2f21a5aa2f.png)

2. Abaixo de *Installed Templates*, clique em SAP > Extension. Selecione o *Process Extension Scenario*, dê um nome a ele e clique em adicionar.

![image](https://user-images.githubusercontent.com/42722229/154366132-8799d6db-3801-4fb9-97e0-159b604f9cd2.png)

3. Selecione o Namespace, Business Object e o Node que deseja utilizar no Process Extension Scenario.

OBS: *Geralmente* o namespace que iremos utilizar será o *http://sap.com/xi/AP/CRM/Global*

No exemplo abaixo, utilizei o Customer Quote como exemplo.

![image](https://user-images.githubusercontent.com/42722229/154366356-ae3a5f39-2206-4083-b2da-f53897fa23f4.png)

4. Feito isso, na parte de baixo temos a opção de selecionar quais serviços standard iremos adicionar naquele Process Extension Scenario.

![image](https://user-images.githubusercontent.com/42722229/154366709-4e70fd74-2195-4145-a88e-351f54d0edd2.png)

Basta selecionar qual deseja utilizar e clicar em *Ok*

## Adicionar campos estendidos (Extension Fields) a um Process Scenario

Para esta etapa, precisaremos utilizar um XBO (Extended Business Object). 

Caso o XBO já esteja criado, seguir para o [passo 4](#passo4)

Caso ainda não esteja criado, devemos seguir os seguintes passos:

1. Abrir o SDK, no *Solution Explorer*, botão direito no projeto e selecione *Add -> New Item*

![image](https://user-images.githubusercontent.com/42722229/154365901-2aad43ec-987e-4c31-abf4-9e2f21a5aa2f.png)

2. Abaixo de *Installed Templates*, clique em SAP > Extension. Selecione o *Business Object Extension*, dê um nome a ele e clique em adicionar.

![image](https://user-images.githubusercontent.com/42722229/154367258-6163c7c2-2b40-4b77-94ce-179377363d16.png)

OBS: Geralmente, alguns XBO's já são utilizados em alguns clientes, verificar antes de tentar criar.

3. Selecione o Namespace e o Business Object que deseja extender e clique em "Ok"

![image](https://user-images.githubusercontent.com/42722229/154367580-43dd0696-d4ef-4843-9388-4157f22fee28.png)

OBS: *Geralmente* o namespace que iremos utilizar será o *http://sap.com/xi/AP/CRM/Global*

<a id="passo4" /> 4. No Solution Explorer, dê um duplo clique e abra o XBO.

![image](https://user-images.githubusercontent.com/42722229/154368398-c2b1da46-c69f-4e70-974d-b2a1dcdfdd55.png)

5. Para adicionar Extension Fields no Process Extension Scenario, será necessário colocar uma notação na frente da criação de cada campo.

A notação deve seguir o seguinte padrão:

Scenario + (Nome do Process Extension Scenario)

Isso deve estar na frente da criação do campo conforme exemplo abaixo:

```[Scenario (Lead_to_Opportunity)] element ext_field_Opportunity_root:Text;```

OBS: Lembrando que o Process Extension Scenario é específico para o Node que ele foi criado. 

Caso ele tenha sido criado para o Node do *Root*, então ele só pode ser utilizado no Node do *Root* do XBO. 

A mesma coisa ocorre para um Process Extension Scenario que foi criado para o Node de *Item*, por exemplo.
