noSql com Mongo

03/10/2022 às 18:57
    Q: Problemas para enviar o segundo commit ao git. Ao digitar "git status", foi gerado a seguinte informação

        *fatal: detected dubious ownership in repository at 'C:/Users/Felipe/Documents/repositorio/noSql'
        To add an exception for this directory, call:

                git config --global --add safe.directory C:/Users/Felipe/Documents/repositorio/noSql

        Set the environment variable GIT_TEST_DEBUG_UNSAFE_DIRECTORIES=true and run
        again for more information.*
03/10/2022 às 19:57
    A: digitei todo o comando no gitBash, conforme abaixo
    git config --global --add safe.directory C:/Users/Felipe/Documents/repositorio/noSql
    ps: observei que o próprio program adicionou (master) após o caminho. Antes não estava.

03/10/2022 às 20:14
    Q: Desliguei o pc, mas agora não conecta o mongo
03/10/2022 às 21:52
    A: Precisei abrir o docker e dar o play no mongo. 
    Não funcionou. Reiniciei o pc e acessei o docker novamente e dei run no mongo. Funcionou \o/

__________________________________
Comandos no MongoDB Compass

*use escola* //vai criar uma nova pasta chamada "escola". Mas, é necessário inserir algo para gravar. 
ps: após o comando *use* você coloca o nome da pasta que quiser.

*cls* //limpa a tela

*db.alunos.find()* //como boa prática é bom colocar um limite dentro de find para filtrar o que se procura.
    eg. *db.alunos.find({nome: "Alice"})*

*db.alunos.find().limit(3)* //vai listar os três primeiros do array.

*db.alunos.find().count()* //vai informar a quantidade de elementos que há no array.
    eg. *db.alunos.find({curso: "QA"}).count()*


usando funções
*db.alunos.find({nota: {$gt: 5}})* //vai mostrar todas as notas maiores que 5
//$lt (less than - menor que), 
//$lte (less than or equals - menor que ou igual), 
//$gt (greater than - maior que) e 
//$gte (greater than or equal - menor que ou igual) 

tabela verdade 
// find({$and: [{nota: 7}, {curso: "QA"}] usando a condicional E
// find({$or: [{nota: 7}, {curso: "QA"}] usando a condicional OU
*db.alunos.find({
    $and: [
        {nota: 7},
        {curso: "QA"}
    ]
})

Caracter coringa
// tiramos as aspas e usamos barra antes e depois do nome eg. */José/*
    *db.alunos.find({nome: /José/})*

Selecionando os dados que a gente quer que apareça
    *db.alunos.find({}, {nome:1})* //O número 1 refere-se ao valor booleano - quer dizer true.
ps: para ocultar basta incluir o "0" em vez de "1".
    eg.*db.alunos.find({}, {nome:1, _id: 0})*

Ordenar elementos em ordem alfabética
    *db.alunos.find({}).sort({nome: 1})* 
    //Nesse caso, o número "1" organizará a lista de forma ascendente.
    //Para decrescente, colocar "-1"

Concatenando as duas últimas funções
    db.alunos.find({}, {nome:1}).sort({nome: 1})
    //basta usar o ".sort" após a primeir função

Alterando o valor de um elemento
    *db.alunos.updateOne({nome: "Paulo"}, {$set: {nota: 7}})*
    // a primeira chave é a forma como vai capturar o array. A segunda chave é o valor que vai alterar

Deletando um array
    db.alunos.deleteOne({nome: "Paulo"})

Deletando em massa
    db.alunos.deleteMany({curso: "QA"})