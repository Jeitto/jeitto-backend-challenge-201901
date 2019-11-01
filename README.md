# Desafio Backend do Jeitto

Este desafio tem como intuito testar as habilidades de desenvolvimento e arquitetura de software do candidato a uma vaga no time de engenharia do Jeitto.
Não foque apenas em entregar este projeto, ele será sim avaliado porém foque mais em aprender durante o processo e tirar o máximo de proveito possível desta experiência.
Antes de começar a codificar, leia todo o texto. Entenda bem o problema, o que foi proposto e em caso de dúvida/sugestão entre em contato.
No final do texto existe uma seção com leituras recomendadas. São textos variados que possuem como intuito auxiliar no processo de decisão e aprendizagem para chegar com sucesso ao final deste desafio.

Divirta-se! :)


## Problema: Recarga telefônica
Implementar uma API para permitir a compra de créditos telefônicos onde o usuário, após informar o número a ser recarregado, efetua a compra.


### Pesquisa por produtos
O primeiro recurso que deve ser implementado é o que irá permitir a manutenção (CRUD) e busca por produtos compatíveis para serem utilizado na recarga. O mesmo deverá, também, receber um parâmetro "company_id" em seu método GET e retornar um JSON com os produtos daquela companhia informada como no exemplo abaixo:

Exemplo 1.1: GET /CompanyProducts?company_id=claro_11

```json
{
"company_id": "claro_11",
 "products":[
   {"id": "claro_10", "value": 10.0},
   {"id": "claro_20", "value": 20.0}
 ]
}
```

Exemplo 1.2: GET /CompanyProducts
```json
[
   {
       "company_id": "claro_11",
       "products":[
           {"id": "claro_10", "value": 10.0},
           {"id": "claro_20", "value": 20.0}
       ]
   },
   {
       "company_id": "tim_11",
       "products":[
           {"id": "tim_10", "value": 10.0},
           {"id": "tim_20", "value": 20.0}
       ]
   }
]
```

Obs.: Os demais métodos deverão seguir a mesma estrutura do payload indicado no exemplo 1.1.


### Efetivação da recarga
O segundo recurso deverá efetivar a recarga telefônica propriamente dita. Permitirá um POST com os dados necessários para a recarga, bem como GETs para busca de dados como nos exemplos abaixo:

Exemplo 2.1: POST /PhoneRecharges
```json
{
   "company_id": "claro_11",
   "product_id": "claro_10",
   "phone_number": "5511999999999",
   "value": 10.00
}
```

Exemplo 2.2: GET /PhoneRecharges?id=id_da_recarga
```json
{
   "id": "id_da_recarga",
   "created_at": "2019-02-01T13:00:00.000Z",
   "company_id": "claro_11",
   "product_id": "claro_10",
   "phone_number": "5511999999999",
   "value": 10.00
}
```

Exemplo 2.3: GET /PhoneRecharges?phone_number=5511999999999
```json
[
   {
       "id": "id_da_recarga",
       "created_at": "2019-02-01T13:00:00.000Z",
       "company_id": "claro_11",
       "product_id": "claro_10",
       "phone_number": "5511999999999",
       "value": 10.00
   },
   {
       "id": "id_da_recarga",
       "created_at": "2019-03-14T13:00:00.000Z",
       "company_id": "claro_11",
       "product_id": "claro_10",
       "phone_number": "5511999999999",
       "value": 10.00
   }
]
```

Obs.: Os demais métodos não deverão ser permitidos para este recurso.


## Como enviar sua solução
Para participar você deverá fazer um fork deste repositório e submeter as alterações apenas para a sua cópia. Não faça um PR para este repositório, apenas envie um link para o avaliador que está em contato com você.

O que **queremos** ver:
- Python 3;
- Testes bem escritos e com uma boa cobertura;
- Legibilidade e manutenibilidade de código;
- Código em inglês;
- Segurança de dados e acesso;
- Tratamento de erros;
- Organização e instruções de como executar o projeto.

O que **gostariamos** de ver:
- Documentação fácil e bem escrita;
- Utilização de docker;
- Processamento assíncrono;
- Tornado, Sanic, Flask;
- Cache de dados;
- Deploy automatizado;
- Amigável com Google Cloud;
- Segurança de dados.

Perguntas que devem ser respondidas
- Quais foram os principais desafios durante o desenvolvimento?
- O que você escolheu como arquitetura/framework/banco e por quê?
- O que falta desenvolver / como poderíamos melhorar o que você entregou?
- Python é a melhor escolha para esta atividade? Por quê?


## Trilha sonora recomendada
- [AC/DC Radio](https://open.spotify.com/user/spotify/playlist/37i9dQZF1E4sEEhVjuqbvL?si=uw6fr-VcTVSopgvRL0koWw)


## Leituras recomendadas
- [Small acts manifesto](http://smallactsmanifesto.org/) sobre comportamento humano e social.
- [The Twelve-Factor App](https://12factor.net/pt_br/) é um manifesto sobre o desenvolvimento e boas práticas para facilitar a manutenção de softwares.
- [Design Patterns for Humans](https://github.com/kamranahmedse/design-patterns-for-humans) texto excelente explicando e mostrando exemplos de uso de padrões de projetos.
- [Python Patterns](https://github.com/faif/python-patterns) é um repositório com exemplos de padrões de projetos implementados em Python.
- [Continuous integration vs. continuous delivery vs. continuous deployment](https://www.atlassian.com/continuous-delivery/principles/continuous-integration-vs-delivery-vs-deployment)
- [OpenAPI Specification](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/2.0.md#operation-object)
