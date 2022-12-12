# Contains

é uma função de manipulação de string que manipula todos os tipos de dados de string (BIT, BLOB e CHARACTER) e retorna um valor booleano para indicar se uma string está presente dentro de outra. 


![image](https://user-images.githubusercontent.com/80789711/207022783-7fc1fd01-41b0-4fcc-a911-462831cb67f5.png)


```
CONTAINS('Hello World!', 'ello');
```
Retornara *TRUE*


```
CONTAINS('Hello World!', 'daisy');
```

Retornara *False*



# ENDSWITH

ENDSWITH é uma função de manipulação de string que manipula todos os tipos de dados de string (BIT, BLOB e CHARACTER) e retorna um valor booleano para indicar se uma string termina com outra. 


![image](https://user-images.githubusercontent.com/80789711/207027573-a3f6c54a-84a5-416f-a9a0-51bbc328e5fc.png)


ENDSWITH retorna TRUE se SourceExpression termina com SearchExpression , caso contrário, retorna FALSE.

As strings de parâmetro para SearchExpression e SourceExpression podem ser do tipo de dados CHARACTER, BLOB ou BIT, mas devem ser do mesmo tipo de dados.

Se algum parâmetro for NULL, o resultado será NULL.

```
ENDSWITH('Hello World!', 'World!');
```
Retornara *TRUE*


```
ENDSWITH('Hello World!', 'World');
```

Retornara *False*


