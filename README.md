<h1 align="center">
    <br>
    <p align="center">Resolução do Exercício - Semana 12<p>
</h1>

###  <h3>Apresentação </h3>

Eu me chamo Larissa Maria, sou aluna do Reprograma na turma On12 de 2021.1 e é um prazer compartilhar um pouco do conhecimento adquirido. Ao longo dessa trajetória venho aprendendo que desenvolver a lógica de programação exige prática e é algo que suma importância para saber os caminhos a seguir e interpretar os dados necessários para resolução daquele determinado problema. Com isso, venho praticando e aliando com o cronograma do curso, sendo assim, a cada dia venho ganhando mais confiança em relação a programação.

<h3>Loja Pet Shop </h3>

Foi criado um banco de dados novo e gerado a Collection Produtos que recebeu a seguinte a inserção de documentos, segue abaixo o passo a passo:

### Criação de novo database

```
use loja_pet_shop
```

### Criação de nova collection

```
db.createCollection('Produtos')
```

### Inserindo documentos na collection

```
db.Produtos.insertMany([
    {
         "id":1,
          "name":"Pote para Ração",
         "description":"Pote que suporta 3 litros, inclui a pá para servir, otima vedação e tampa com relevo nas extremidades",
          "price":39.99
       },
       {
          "id":2,
          "name":"Tapete Higiênico",
          "description":"Tapete higiênico com cheirinho cítrico para os clientes economizarem tempo e dinheiro",
          "price":49.99
       },
       {
          "id":3,
          "name":"Cama Flex Pet Azul Marinho",
          "description":"Fácil de higienizar, leve para transportar, possui maior resistência e conforto para seu pet",
          "price":59.99
       },
       {
          "id":4,
          "name":"Shampoo Antipulgas",
          "description":"Antiséptico, elimina pulgas, carrapatos e piolhos com fórmula suave para ser aplicado até em filhotes",
          "price":19.99
       },
       {
          "id":5,
          "name":"Brinquedo Sonoro Frango Gritador",
          "description":"Leve, macio, formato engraçado e totalmente atóxico",
          "price":12.99
       },
       {
          "id":6,
          "name":"Ração Seca Natural",
          "description":"Com atioxidantes naturais, ideal para saúde dos pelos e pele, proteção imunólogica e contribui com a saúde intestinal do seu pet",
          "price":42.99
       },
       {
          "id":7,
          "name":"Coleira",
          "description":"Confortável, design moderno e toque simples para deixar seu pet elegante",
          "price":19.99
       },
       {
          "id":8,
          "name":"Guia retrátil",
          "description":"Guia retrátil Preto de 3 metros que suporta até 5 kg",
          "price":19.99
       },
       {
          "id":9,
          "name":"Osso Chomp",
          "description":"Previne no controle do tártaro, proporciona gengivas mais saudáveis e combate o mau hálito",
          "price":9.99
       },
       {
          "id":10,
          "name":"Petisco Gold",
          "description":"Pedacinhos crocantes por fora e macio por dentro no sabor frango",
          "price":5.99
       }
]);
```

### Atualização do preço do Produto

```
db.getCollection('Produtos').update(
    {
        "name" : "Petisco Gold",
    },
    {
        $set:{"price":4.99}
    }
);
```

### Exclusão de documento por id

```
db.getCollection('Produtos').remove({
     "id" : 10,
});
```

### Consulta com projeção  - Ordenar do mais barato para o mais caro

```
db.getCollection('Produtos').find({}).sort({price: +1})
```

### Consulta utilizando combinação entre os seletores - Buscar produto que comece com 'C' e o preço seja menor ou igual  59.99

```
db.getCollection('Produtos').find({name:/^C/, price:{$lte:59.99}})
```

### Consulta que retorna no máximo 4 consultas na busca utilizando o limit

```
db.getCollection('Produtos').find({}).limit(4)
```

### Consulta que remove alguns registros da lista (exemplo:  "pulou " 2 registros)

```
db.getCollection('Produtos').find().skip(2)
```

### Consulta paginada e ordenada (utilizar skip, limit e sort) - Busca o terceiro produto mais caro

```
db.getCollection('Produtos').find({}).sort({price: -1}).skip(2).limit(1)
```

<h3>Fonte:</h3>

https://docs.mongodb.com/manual/tutorial/query-documents/

### <h3>Contato :</h3>

* [Linkedin](https://www.linkedin.com/in/lmrs99/)

* [Github](https://github.com/Larissamrs)

