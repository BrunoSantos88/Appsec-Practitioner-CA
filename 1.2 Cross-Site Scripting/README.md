
# Cross-site scripting

* Cross-site scripting (XSS) é um tipo de vulnerabilidade de segurança normalmente encontrada em aplicações web. Ocorre quando um invasor usa código malicioso para injetar um script do lado do cliente em uma página da Web visualizada por outros usuários. Esse tipo de ataque permite que um invasor seja exibido como a página da Web é exibida para o visualizador e pode ser usada para obter acesso a dados do usuário ou até mesmo injetar código malicioso na própria página da web.  Os ataques XSS são normalmente realizados injetando código malicioso na página da web usando HTML ou JavaScript. Este código pode ser usado para obter acesso aos dados do usuário, alterar a aparência da página ou até mesmo enviar comandos maliciosos para o servidor. O código malicioso é muitas vezes escondido em um URL, campo de formulário oculto ou na origem HTML da página da web.

* Os ataques XSS são frequentemente usados em conjunto com outros ataques, como phishing ou malware, para obter acesso a dados do usuário ou para executar comandos maliciosos. Eles também podem ser usados para espalhar links maliciosos ou código para outros usuários.  

* Existem dois tipos principais de XSS: 

# Stored XSS 

* Em um ataque XSS armazenado, o invasor injeta código malicioso no banco de dados de um site, onde é armazenado e executado sempre que é executado sempre que alguém acessa uma página que recupera dados do banco de dados.

# XSS refletido

* Em um ataque XSS refletido, o invasor cria um URL que envolve que maliciosa o código e engana a vítima para clicar nele. Quando o navegador da vítima solicita o URL, o servidor retorna uma página contendo o código injetado, que é então executado pelo navegador da vítima.
  

# Prevenção 

* Existem várias maneiras de prevenir ataques XSS:

1. Validação e higienização de entrada: envolve a verificação da entrada do usuário para conteúdo malicioso e removê-lo ou codificá-lo. Isso pode ser feito no lado do cliente usando JavaScript ou no lado do servidor.

2. Política de segurança de conteúdo (CSP): CSP é um recurso de segurança que permite que um site especifique quais fontes de conteúdo podem ser carregadas pelo navegador. Ao usar o CSP, um site pode impedir a execução de um código malicioso que foi injetado no site.

3. Escapando a entrada do usuário: Isso envolve a conversão de caracteres especiais na entrada do usuário para que eles não sejam interpretados como código. Isso pode ser feito no lado do servidor antes que a entrada seja exibida no site.

4. Codificação de entrada do usuário: Isso envolve a conversão da entrada do usuário em um formato que pode ser exibido com segurança no site sem ser executado como código.

5. Desativar HTML na entrada do usuário: Isso envolve a desativação da capacidade de os usuários inserirem tags e atributos HTML para evitar a injeção de código malicioso.

6. É importante notar que nenhuma solução única pode impedir completamente os ataques XSS, e uma combinação dessas medidas deve ser usada para mitigar efetivamente o risco. 


https://owasp.org/www-community/attacks/xss/ </p>
https://owasp.org/www-project-top-ten/2017/A7_2017-Cross-Site_Scripting_(XSS) </p>