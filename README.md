<h2> Testes_unitarios_para_validar_uma_API_REST </h2>

Com os testes unitários é possível montar um projeto bem documentado<br/>
* Frameworks: JUnit, Mockito e Hamcrest <br/>


* JPARepository classe que tem a responsabilidade de conversar com o
banco de dados, criar, ler, atualizar, excluir e implementar
outras operações no bd, retorna os dados como um tipo Optional onde
são feitas operações seguras e posteriormente realizar validações
com o Optional<br/>
 O JPA faz todo o gerenciamento com o banco de dados (Spring data jpa)<br/>
A classe sevice recebe anotação @Service, para indicar que essa
classe será gerenciada pelo Spring, todo o ciclo de vida dela será
gerenciada pelo Spring<br/>
É só injetar a classe service na classe controller para que o String
faça o gerenciamento
  

* Classe controller, onde acontece todas as operações iniciais do padrão REST<br/>
@RestController : indicando que é uma classe controladora e voltada a
uma API_REST e somente com a parte de dados
  

* JUnit utlizar o assertEquals para fazer a validação da operação em teste
  

* Mockito, pode verificar interações a partir de uma lista mockada e com o
método mock é possível criar um objeto dublê e adicionando dados na lista
mockada é possível verificar as interações, se pode também simular chamadas<br/>
OBS: na construção do "when", se faz uso do Mockito.when no início


* Hamcrest, uma biblioteca para ajudar escrever testes com maior qualidade
criando bons testes, com maior cobertura e de fácil nomenclatura para
ajudar na documentação do projeto


* Ao adicionar a biblioteca "Spring Boot Starter Test", será adicionado os
frameworks JUnit, Mockito, Hamcrest, Spring core e Spring test


* O "Spring Boot Starter Test", no pom.xml deve ser adicionado nas dependências
com o "scope test" (num escopo de teste)


* Na classe BeerServiceTest a anotação @ExtendWith(MockitoExtension.class)<br/>
Essa anotação diz que vai rodar o teste com extensão Mockito e realizar
testes com objetos dublês


* @Builder, uma anotação, classe, do Lombok para facilitar a criação de
objetos para os testes<br/>
Definido no BeerDTOBuilder, já com os atributos e valores do objeto,
pode-se chamar o @Builder em vários testes dentro da estrutura do projeto<br/>
O padrão Builder é muito utilizado nos testes para facilitar a criação de
objetos pois nos traz o objeto com todos os valores preenchidos


* A classe controller faz a a interação com o postman, nessa classe
existe três métodos para ser testado


* A classe Sevice já testada, quando for testar o controller a service
servirá como um mock, objeto dublê nos testes<br/>
É preciso gerar um método de setup<br/>
Antes de realizar cada teste, é preciso configurar o objeto mockMvc


* Foi criado uma classa JsonConvertionUtils para realizar os testes
no BeerControllerTest<br/>
O JsonConvertionUtils converte todos os objetos para uma json para
a simulação de uma chamada do teste unitario numa API


* Quando o teste não tem um retorno (um void), o assert não tem como
ser aplicado, nesses casos se usa o verify do Mockito<br/>
exemplo, no BeerServiceTest testando a exclusão


* Sobre TDD: criar primeiro testes que falham , para depois criar
códigos que atendam os testes de forma bem legível e de fácil manutenção<br/>
exemplo: nos 3 testes sobre o incremento da classe BeerService, o increment
sofreu alteração para cada teste aplicado para fins de aprimoramento do código<br/>
Desenvolver o código orientado por testes focando a qualidade<br/>
Os testes que cobrem o maior cenário possível de situações vem atender
a necessidade de desenvolver um código mais completo, seguro e que
atenda todas as necessidades do usuário prevendo e previnindo todas
as possibilidades possíveis.
  

* Finalizando o projeto:<br/>
 *** realizar fix a partir do teste quando incrementa valor acima do máximo...<br/>
 *** Corrigir o "mockMvc..." para que o ".content(asJsonString(..." possa reconhecer a referência<br/>
 *** Criar o método "decrement" na classe BeerService<br/>
 *** Criar o "@PatchMapping("/{id}/decrement")" no BeerController, e fazer
a relação do "decrement"

## Dessa forma, todos os testes unitários passarão!!!