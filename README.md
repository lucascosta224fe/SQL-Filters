# SQL-Filters
Uso de filtros em SQL 

<h2>📜 Contexto:</h2>

A database da **organização** possui duas tabelas: 

 - ***log_in_attempts***
   `event_id`: id atribuído ao evento (PK);
   
   `username`: nome do funcionário;
   
   `login_date`: data do login;
   
   `login_time`: horário do login;
   
   `country`: país de acesso;
   
   `ip_address`: ip da máquina;
   
   `success`: identifica se o login foi bem ou mal sucedido.

 - ***employees***
   
   `employee_id`: id do funcionário (PK);
   
   `device_id`: id da máquina do funcionário;
   
   `username`: nome do funcionário;
   
   `department`: departamento do funcionário;
   
   `office`: onde o escritório fica localizado.

<h2>📖 Descrição do Projeto: </h2>

Neste projeto devo ser capaz de filtrar corretamente o que se pede nos itens abaixo, utilizando
de operadores como NOT, AND ou OR e de filtros como LIKE ou FILTER FOR

 - ***Retrieve after hours failed login attempts***
    - O dessa objetivo seção é identificar as tentativas de acesso feitas depois do horário de trabalho
18:00 e falharam.
  ![image](https://github.com/user-attachments/assets/0a394be9-15c4-4b55-bfae-85ea27b48d67)

Utilizei o comando `SELECT` para selecionar todas as colunas com * , depois usei `FROM` para
pegar as tentativas de login `log_in_attempts` e logo após `WHERE` (Verifica uma condição), no
caso a condição é o tempo de login `login-time` foi depois `>` das 18:00 e não foram
concluídas (success = 0).

 - ***Retrieve login attempts on specific dates***
   - Nesta parte, o objetivo é identificar os logins ocorridos nas datas 08/05/2022 e 09/05/2022 
   ![image](https://github.com/user-attachments/assets/ffc8ea99-3c8d-4105-836e-7c1578051d3d)

Seguindo a mesma lógica aqui só muda quando utilizamos o operador `OR` para ver uma data
ou outra.

 - ***Retrieve login attempts outside of Mexico***
   - Aqui, preciso pegar logins fora do México, mas percebe-se que o banco de dados não está tratado.
     ![image](https://github.com/user-attachments/assets/b17a4d99-14b7-41c7-a8a5-590b73364acb)

    Neste utilizar outro operador `NOT` para pegar tudo o que não é do México no caso utilizando
    o `LIKE` que filtra dados num banco de dados já que esse banco de dados em específico tinha
    MEX e MEXICO ( o que não é recomendado, o ideal é filtrar e tratar o banco de dados para não
    ter arquivos com o mesmo sentido duplicado ) usei `MEX%`, o que significa que ele exclui
    palavras com MEX no início delas e qualquer coisa que essa palavra completa é descartada.

 - ***Retrieve employees in Marketing***
   -O objetivo aqui era filtrar por empregados no departamento de marketing e localizados nos
escritórios do leste.
   ![image](https://github.com/user-attachments/assets/3f0eb2d5-b280-4970-a4bc-7736cd63a04a)
   
   Usei o `LIKE` novamente só que com o operador `AND` para filtrar realmente só os empregados
exigidos.

 - ***Retrieve employees in Finance or Sales***
   ![image](https://github.com/user-attachments/assets/dd8d8d70-61ae-451a-8d6f-ff118249a1e1)
   
 Aqui a ideia era filtrar certos funcionários do departamento de finanças e de vendas.
Juntei o operador `OR` com o `LIKE` e observe que para fazer aparecer os dois é necessário
escrever novamente o department após `OR` se não ele apenas pega do primeiro parâmetro.

 - ***Retrieve all employees not in IT***
   ![image](https://github.com/user-attachments/assets/ddbd7fb3-d526-4c08-bc93-cde0e157fba8)

   Aqui só utilizei o operador `NOT` para tirar tudo o que se referia a ‘Information Technology’ para
mostrar todos que não são desse departamento;

<h2>📕 Summary:</h2>
Em resumo, fui capaz de filtrar corretamente os dados solicitados e demonstrar conhecimento básico
na ferramenta SQL do mariaDB.

 

