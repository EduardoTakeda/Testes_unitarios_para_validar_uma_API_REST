<h2> Testes_unitarios_para_validar_uma_API_REST </h2>

Com os testes unitários é possível montar um projeto bem documentado<br/>
Frameworks: JUnit, Mockito e Hamcrest <br/>
JPARepository classe que tem a responsabilidade de conversar com o
banco de dados, criar, ler, atualizar, excluir e implementar
outras operações no bd, retorna os dados como um tipo Optional onde
são feitas operações seguras e posteriormente realizar validações
com o Optional
O JPA faz todo o gerenciamento com o banco de dados (Spring data jpa)
A classe sevice recebendo anotação @Service, para indicar que essa
classe será gerenciada pelo Spring, todo o ciclo de vida dela será
gerenciada pelo Spring
É só injetar a classe service na classe controller para que o String
faça o gerenciamento

Classe controller, onde acontece todas as operações iniciais do padrão REST
@RestController :indicando que é uma classe controladora e voltada a
uma API_REST e somente com a parte de dados

JUnit utlizar o assertEquals para fazer a validação da operação em teste

Mockito, pode verificar interações a partir de uma lista mockada e com o
método mock é possível criar um objeto dublê e adicionando dados na lista
mockada é possível verificar as interações, se pode também simular chamadas

Hamcrest, uma biblioteca para ajudar escrever testes com maior qualidade
criando bons testes, com maior cobertura e de fácil nomenclatura para
ajudar na documentação do projeto

Ao adicionar a biblioteca "Spring Boot Starter Test", será adicionado os
frameworks JUnit, Mockito, Hamcrest, Spring core e Spring test

O "Spring Boot Starter Test", no pom.xml deve ser adicionado nas dependências
com o "scope teste" (num escopo de teste)



Na classe BeerServiceTest a anotação @ExtendWith(MockitoExtension.class)
Essa anotação diz que vai rodar o teste com extensão Mockito e realizar
testes com objetos dublês

@Builder, uma anotação, classe, do Lombok para facilitar a criação de
objetos para os testes
Definido no BeerDTOBuilder, já com os atributos e valores do objeto,
pode-se chamar o @Builder em vários testes dentro da estrutura do projeto
O padrão Builder é muito utilizado nos testes para facilitar a criação de
objetos pois nos traz o objeto com todos os valores preenchidos