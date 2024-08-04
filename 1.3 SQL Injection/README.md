# SQL Injection

* A injeção de SQL é um tipo de ataque que aproveita a estrutura do SQL para injetar código malicioso em um aplicativo da Web. É uma das vulnerabilidades de segurança mais comuns em aplicações web e pode causar perda de dados, comprometimento do sistema e outras atividades maliciosas. 

* Os ataques de injeção SQL podem ser divididos em três categorias:

1. Injeção de SQL clássico: A injeção SQL clássica envolve manipular a sintaxe de uma consulta SQL para obter acesso a dados confidenciais. Isso geralmente envolve a inserção de código malicioso em um campo de entrada ou URL.

2. Injeção de SQL cego: Injeção de SQL cego é um tipo de ataque que é usado quando o invasor não tem acesso direto ao banco de dados. Neste caso, o invasor usará técnicas como injeção de SQL baseada em booleano e baseada em tempo para obter acesso ao banco de dados.

3. Injeção SQL de segunda ordem: Injeção SQL de segunda ordem é um tipo de ataque que ocorre quando um invasor é capaz de injetar código malicioso em um aplicativo web e é executado quando o aplicativo é usado por outro usuário.

4. Além desses três tipos de ataques, também existem outros métodos de injeção de SQL. Isso inclui explorar procedimentos armazenados, explorar funções definidas pelo usuário, explorar a execução remota de comandos e explorar firewalls de aplicativos da Web. 

* Exemplos de injeção de SQL incluem:

* Inserir código malicioso em um campo de entrada: Isso envolve a inserção de código malicioso em um campo de entrada para obter acesso a dados confidenciais. Por exemplo, um invasor pode inserir o seguinte código em um formulário de login:

````
SELECT ? DOS usuários OBRINDE-Util de nome de usuário?'$username' E palavra-passe'$password' OU '1''''1''
````

* Explorar procedimentos armazenados: envolve a exploração dos procedimentos armazenados de uma aplicação web para obter acesso a dados sensíveis. Por exemplo, um invasor pode usar o seguinte código para executar um procedimento armazenado:

````
EXEC sp_executesql 'SELECT ? FROM usuário WHERE username?'$username' E password'$password' OR '1''''
````

* Explorar funções definidas pelo usuário: isso envolve a exploração de funções definidas pelo usuário para obter acesso a dados confidenciais. Por exemplo, um intruso pode utilizar o código a seguir para executar uma função definida pelo utilizador:

````
SELECT dbo.fn_getuserdata('$username','$password')
````

* Explorar a execução remota do comando: envolve a exploração do recurso de execução de comando remoto de um aplicativo da Web para obter acesso a dados confidenciais. Por exemplo, um atacante pode usar o seguinte código para executar um comando remoto:

````
EXEC xp_cmdshell 'SELECT ? FROM users WHERE username?'$username' AND password''$password' OR '1'''
````

* Explorar firewalls de aplicativos da Web: isso envolve a exploração dos firewalls de aplicativos da Web de um aplicativo da Web para obter acesso a dados confidenciais. Por exemplo, um invasor pode usar o seguinte código para ignorar um firewall de aplicativo da Web:

````
SELECIONE - FROM users WHERE username LIKE '%$username%' E senha LIKE '%$password%'
````

* Exemplos de injeção de SQL incluem:

* Inserir código malicioso em um campo de entrada: Isso envolve a inserção de código malicioso em um campo de entrada para obter acesso a dados confidenciais. Por exemplo, um invasor pode inserir o seguinte código em um formulário de login:

````
SELECT ? DOS usuários OBRINDE-Util de nome de usuário?'$username' E palavra-passe'$password' OU '1''''1''
````

* Explorar procedimentos armazenados: envolve a exploração dos procedimentos armazenados de uma aplicação web para obter acesso a dados sensíveis. Por exemplo, um invasor pode usar o seguinte código para executar um procedimento armazenado:
````
EXEC sp_executesql 'SELECT ? FROM usuário WHERE username?'$username' E password'$password' OR '1''''
````
* Explorar funções definidas pelo usuário: isso envolve a exploração de funções definidas pelo usuário para obter acesso a dados confidenciais. Por exemplo, um intruso pode utilizar o código a seguir para executar uma função definida pelo utilizador:
````
SELECT dbo.fn_getuserdata('$username','$password')
````
* Explorar a execução remota do comando: envolve a exploração do recurso de execução de comando remoto de um aplicativo da Web para obter acesso a dados confidenciais. Por exemplo, um atacante pode usar o seguinte código para executar um comando remoto:
````
EXEC xp_cmdshell 'SELECT ? FROM users WHERE username?'$username' AND password''$password' OR '1'''
````
* Explorar firewalls de aplicativos da Web: isso envolve a exploração dos firewalls de aplicativos da Web de um aplicativo da Web para obter acesso a dados confidenciais. Por exemplo, um invasor pode usar o seguinte código para ignorar um firewall de aplicativo da Web:
````
SELECIONE - FROM users WHERE username LIKE '%$username%' E senha LIKE '%$password%' 
````

* A injeção de SQL é um sério risco de segurança e pode ter sérias consequências tanto para o atacante quanto para a vítima. É importante estar ciente dos diferentes tipos de injeção de SQL e tomar medidas para evitá-los. Alguns deles são os seguintes: 

1. Usar consultas parametrizadas - As consultas parametrizadas são um tipo de consulta que usa espaços reservados para representar valores e impedir que o código malicioso seja injetado na consulta.

2. Use instruções preparadas - As instruções preparadas são um tipo de consulta que é pré-compilado e pode ser usado várias vezes com parâmetros diferentes.

3. Validação de entrada - A validação de entrada é uma técnica que verifica a entrada do usuário para código malicioso e impede que ela seja executada.

4. Implementar whitelisting - Whitelisting é uma técnica que permite que apenas certos tipos e valores de dados sejam aceitos pela aplicação.

5. Use procedimentos armazenados - Os procedimentos armazenados são um tipo de consulta que é armazenado no banco de dados e pode ser usado para executar várias consultas em uma única instrução.

6. Criptografar dados confidenciais - Criptografia é uma técnica que é usada para proteger dados confidenciais contra acesso por usuários não autorizados.

7. Use o acesso de privilégio mínimo - O acesso mínimo de privilégios é um princípio de segurança que concede aos usuários o acesso mínimo necessário para executar tarefas.

8. Monitore logs do sistema - Os logs do sistema são um tipo de log que pode ser usado para monitorar a atividade do sistema e detectar atividades suspeitas.

9. Use firewalls de aplicativos da Web - Os firewalls de aplicativos da Web são um tipo de firewall que é usado para proteger aplicativos da Web contra tráfego malicioso. 

# OWASPTOP10 

https://owasp.org/Top10/A03_2021-Injection/
https://owasp.org/www-project-top-ten/2017/A1_2017-Injection