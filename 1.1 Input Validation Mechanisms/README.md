# Appsec-Practitioner-CA
Certified Appsec Practitioner (CAP)

* Os conteúdos do curso para o Certified Appsec Practitioner são todos como:

# Input Validation Mechanisms


* A validação de entrada é algo que é usado para limitar a entrada do usuário para alcançar apenas a funcionalidade necessária através de testes de entrada. Como algumas das vulnerabilidades como XSS, SQL Injection, SSTI etc. são possíveis devido à falta de implementação dentro da validação de entrada, é necessário entender o que somos capazes de implementar para evitar essas vulnerabilidades e evitar qualquer um dos problemas de Confidencialidade, Integridade e Disponibilidade. Como diferentes linguagens de programação oferecem métodos diferentes para validar a entrada, o mecanismo de lista branca ou lista negra permanece o mesmo para todas as linguagens. 


* A validação deve ser feita dentro dos níveis sintáticos e semânticos. 
Nível Sintático: A partir do nome, somos capazes de adivinhar que o syntático está relacionado com a sintaxe de qualquer entrada. Portanto, a sintaxe dos campos estruturados precisa ser validada.  </p>

Por exemplo:

* Número de telefone: +9779812345678, que mostra que temos um símbolo + no início da sintaxe seguido por um código de país que poderia estar entre 1 a 3 de comprimento, juntamente com o número de telefone, 10 em comprimento permitindo apenas dígitos de 0 a 9. 

*Nível semântico: A semântica vem para jogar quando a correção dos valores está dentro do contexto necessário. Por exemplo: Datas: Permitir datas com limites quando necessário. Se uma data para a inscrição de um usuário dentro de uma universidade for dada, a validação semântica não deve permitir que o usuário insira nenhuma data antes da data de inscrição para a graduação. 

* Alguns dos novos desenvolvedores que trabalham sem frameworks geralmente só lidam com a validação na parte frontal, tornando o aplicativo vulnerável quando as solicitações são modificadas por meio de diferentes ferramentas, como o Burp Suite ou até mesmo a capacidade do navegador de modificar e reenviar solicitações. 

* Portanto, a validação deve ser feita tanto para a extremidade dianteira quanto para o back-end. Mas a maior parte da validação de entrada já está disponível em frameworks como o Django, o que facilita a implementação dessas validações. Mas parte da validação precisa ser feita de acordo com os casos que vemos. 


# A seguir estão as formas de definir validações: 

1. Verifica esquemas específicos, como JSON, XML, etc., e incluindo verificações rigorosas para validação.

2. Usando o tratamento de exceções para lidar com casos especiais e usando tipos de dados para especificar o tipo de dados que estão sendo inseridos em vez de usar strings para cada tipo de dados.

3. O intervalo dos caracteres deve ser verificado e limitado para que não mais do que o intervalo especificado possa ser inserido.

4. O uso de expressões regulares deve ser feito para cobrir toda a string, em vez de apenas seções da string, ou seja, usar o - para digitalizar a partir do início da cadeia de caracteres e $ até o final para garantir que a cadeia de caracteres inteiras seja selecionada em vez de uma substring envolvida.

5. Permitir apenas um conjunto de caracteres obrigatórios para ser aceito

6. Usando a codificação para codificar caracteres especiais que precisam ser emitidos para a página ou aplicativo

7. Valide o mesmo conjunto de regras para o nome dos uploads para os arquivos e renomeá-los aleatoriamente usando UUIDs ou qualquer convenção de nomenclatura que seja muito aleatória.

8. Valide o tamanho do arquivo carregado e a extensão do arquivo. A extensão do arquivo deve ser validada e limitada.

9. Para arquivos compactados e descompactados posteriormente pelo servidor, a validação do zip precisa ser feita com antecedência, o que inclui o caminho de destino, o nível de compactação e o tamanho estimado do arquivo descomprimido. 
Os arquivos enviados precisam ser verificados para qualquer conteúdo malicioso e precisam ser verificados.

10. O caminho do arquivo deve ser definido a partir do lado do servidor (backend) e não do lado do cliente (fronteireiro)

11. O tipo de conteúdo do arquivo carregado deve ser predefinido e ser servido de acordo com scripts executáveis, arquivos de configuração e outros arquivos de configuração de domínio cruzado devem ser bloqueados do upload.

12. O uso de bibliotecas de reescrita de imagens para verificar a validade da imagem e a remoção de conteúdo em excesso deve ser feito. A imagem deve ser definida como apenas de certos formatos. Alguns acham que parar a extensão do arquivo seria uma boa solução, mas o conteúdo da imagem precisa ser verificado de antemão, pois há scripts executáveis que podem ser renomeados e carregados.

13. A validação rigorosa do endereço de e-mail precisa ser feita do lado do cliente, bem como do lado do servidor. https://tools.ietf.org/html/rfc5321-section-4.1.2 define o formato dos endereços de e-mail. Usar o regex para ter validação sintática e usar técnicas para verificar por meio da validação semântica de que o e-mail realmente existe é uma maneira de validar e-mails.

14. Listar endereços de e-mail que são descartáveis pode ser uma solução, mas como os domínios podem ser criados e criar um servidor de e-mail é muito fácil, o processo para a lista negra pode ser infinito. Assim, a lista de permissões de endereços de e-mail pode ser feita sempre que possível.

15. Portanto, seguindo os métodos acima para listar e listar no blacklist um conjunto de regras sintáticas e seguindo alguns procedimentos semânticos, somos capazes de validar os dados que foram inseridos. 


# O que fazer quando a entrada falha na validação? 

1. Então, o que você faz quando a entrada falha na validação? Existem duas abordagens principais: recuperar e continuar, ou falhar a ação e relatar um erro. Cada um tem suas vantagens e desvantagens:

2. Recuperação: Recuperar-se de uma falha de validação de entrada implica que a entrada pode ser higienizada ou corrigida - ou seja, que o problema que causou a falha pode ser resolvido de forma programática. Isso geralmente é mais provável de ser possível se você estiver adotando uma abordagem de lista negra para validação de entrada, e geralmente adota a abordagem de remover caracteres ruins da entrada. A principal desvantagem dessa abordagem é garantir que a filtragem ou remoção de valores realmente higienize a entrada e não apenas mascabre a entrada maliciosa, o que ainda pode levar a problemas de injeção de SQL.

3. Falha: falhar a ação implica gerar um erro de segurança e, possivelmente, redirecionar para uma página de erro genérico indicando ao usuário que o aplicativo tinha um problema e não pode continuar. Esta é geralmente a opção mais segura, mas você ainda deve ter cuidado para se certificar de que nenhuma informação sobre o erro específico é apresentada ao usuário, pois isso pode ser útil para um invasor para determinar o que está sendo validado na entrada. A principal desvantagem dessa abordagem é que a experiência do usuário é interrompida e qualquer transação em andamento pode ser perdida. Você pode mitigar isso, além de realizar a validação de entrada no navegador do cliente, para garantir que os usuários genuínos não devem enviar dados inválidos, mas você não pode confiar nisso como um controle porque um usuário mal-intencionado pode alterar o que é enviado para o site.

4. Qualquer que seja a abordagem escolhida, certifique-se de registrar que ocorreu um erro de validação de entrada nos logs do aplicativo. Este pode ser um recurso valioso para você usar para investigar uma invasão real ou tentada em seu aplicativo. 

# References

https://wiki.owasp.org/index.php/Testing_for_Input_Validation </p>
https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html </p>
https://owasp.org/www-project-proactive-controls/v3/en/c5-validate-inputs</p>


# Owasptop10

https://owasp.org/www-project-mobile-top-10/2023-risks/m4-insufficient-input-output-validation </p>
https://owasp.org/www-project-mobile-top-10/2023-risks/m4-insufficient-input-output-validation </p>
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/07-Input_Validation_Testing/README
https://owasp.org/www-project-proactive-controls/v3/en/c5-validate-inputs