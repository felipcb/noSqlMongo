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
03/10/2022 às 20:17
    A: Precisei abrir o docker e dar o play no mongo. 
    Não funcionou. Reiniciei o pc e acessei o docker novamente e dei run no mongo. Funcionou \o/