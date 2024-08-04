# Appsec-Practitioner-CA
Certified Appsec Practitioner (CAP)

* Os conteúdos do curso para o Certified Appsec Practitioner são todos como:
* Input Validation Mechanisms


* A validação de entrada é algo que é usado para limitar a entrada do usuário para alcançar apenas a funcionalidade necessária através de testes de entrada. Como algumas das vulnerabilidades como XSS, SQL Injection, SSTI etc. são possíveis devido à falta de implementação dentro da validação de entrada, é necessário entender o que somos capazes de implementar para evitar essas vulnerabilidades e evitar qualquer um dos problemas de Confidencialidade, Integridade e Disponibilidade. Como diferentes linguagens de programação oferecem métodos diferentes para validar a entrada, o mecanismo de lista branca ou lista negra permanece o mesmo para todas as linguagens. 


* A validação deve ser feita dentro dos níveis sintáticos e semânticos. 
Nível Sintático: A partir do nome, somos capazes de adivinhar que o syntático está relacionado com a sintaxe de qualquer entrada. Portanto, a sintaxe dos campos estruturados precisa ser validada. 

* Por exemplo:

* Número de telefone: +9779812345678, que mostra que temos um símbolo + no início da sintaxe seguido por um código de país que poderia estar entre 1 a 3 de comprimento, juntamente com o número de telefone, 10 em comprimento permitindo apenas dígitos de 0 a 9. 
