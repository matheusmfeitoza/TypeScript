# TypeScript

Superset para o JavaScript

Tipagem para o JavaScript

## Tipagens

 - Tipagem explicita:
    
Eu defino explicitamente, de maneira obvia, o que a variável deve ser retornada.

Exemplo:

```TypeScript
    const name: string;
    const numero: number;
```
- Any:

Tipo que espera qualquer tipo. Seu uso é com extremo cuidado, pois perde o real sentido de usar o TypeScript.

exemplo: 

```TypeScript
    const sum: any;

```
- Inferência de tipos (Tipagem implícita):

No Typescript, podemos criar variáveis sem necessitar explicitar o seu tipo, pois o TypeScript sabe reconhecer o seu tipo, isto é quando o mesmo é de maneira obvia ou a variável criada é inicializada.

exemplo:

```TypeScript
    const name = 'João'
    const idade = 18;
    const estaDoente = false;
    const grupoDeNomes = ['Selma','Vilma','Rodolfo'];
    const grupoDeContatos = [
        {
            nome: 'Matheus',
            telefone: 9999999999
        },
        {
            nome: 'Danilo',
            telefone: 88888888
        }

    ]
```

- Tipos primitivos:

Tipos primitivos reconhecidos e aceitos pelo TypeScript.

 1. number
 2. string
 3. boolean


- Arrays:

Podemos tipar arrays também, veja o exemplo abaixo:

```TypeScript
    const numbers: number[]; // Declarei a variável number e explicitei que será um array de números, logo será somente aceito números.

    const users: string[]; // Declarei a variável users e explicitei que será aceito somente string's

    // Também podemos declarar um array desta maneira:

    const sequecialNumbers = Array<number>;
```
- Funções:

Funções também pode ter seu retorno tipado, mas primeiro vamos entender um pouco da nomenclatura esperada de uma função:

```TypeScript

    function functionName(param1:string): void {

        //Escopo
        
    }
```

Acima temos um escopo básico, onde temos a palavra reservada function, o nome da função, os parâmetros com o seu tipo explicitado logo após o retorno da função.

O TypeScript, faz o retorno da função de maneira automática, caso o mesmo não seja informado, por meio da inferência.

- Union:

Usado para descrever mais de um tipo aceito.

```TypeScript
    function getIdNumber(id: number | string) { // Será aceito, number ou string
        //Scope
    }
```

- Generics:

Ainda irei melhorar esta sessão, pois ainda preciso compreender melhor generics e seu uso.

[Documentação oficial](https://www.typescriptlang.org/docs/handbook/2/generics.html)

- Types:

Poder de criar nossa própria tipagem, ou seja, posso criar contextos com meus tipos definidos.

```typescript

    let UserType = string | number

    const userID: UserType;
    const otherUserId: UserType;

```
- Type assertions

Quando sabemos o retorno de um tipo, podemos especificar, mais claramente afirmar o seu retorno para um contexto. Geralmente usado em consumo de API'sabe

```typescript
    type UserResponse = {
        id: number;
        name: string;
        avatar: string;
    }

    const userResponse = {} as UserResponse;
``` 

- Intersecção de tipos:

É quando queremos juntar 2 tipos em 1, confira no exemplo:

```typescript
    type User = {
        id: number;
        nome: string;
    }

    type Player = {
        nickname: string
        level: number
    }

    type PlayerProps = User & Player;

    const info: PlayerProps = {
        id: 1,
        nome: "Naruto Son",
        nickname: "Naruto",
        level: 999
    }
```

- Interface:

Usado também para criar tipagem

```typescript
    interface User {
        id: number;
        nome: string
    }

    const usuario: User = {
        id: 0,
        nome: "Dolphin"
    }
```  

## Extras

?? pode ser usado para um valor default...

Exemplo: 

 ```TypeScript
    function getNameAndTicket(user:string | null, ticket: number) {
        console.log(`Usuário: ${user ?? 'Usuário padrão'}, Ticket: ${ticket}`)
    }
    getNameAndTicket(null, 200);

 ```   

 ? Define que uma propriedade é opcional

```typescript
    type UserProps = {
        name: string
        age: number
        email?: string
    }

```
