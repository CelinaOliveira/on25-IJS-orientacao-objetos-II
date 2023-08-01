# Exercício de Sala 🏫  

- Conteúdo teórico: 
[Abstração](../../../README.md#abstração) e [Encapsulamento](../../../README.md#encapsulamento)

## Exercício 2

Dada a classe `Account` abaixo:
```javascript
class Account {
  id;
  name;
  balance;

  constructor(id, name, balance) {
    this.id = id;
    this.name = name;
    this.balance = balance;
  }

  credit(amount) {
    this.balance += amount;
    console.log(`O saldo após o crédito é de R$ ${this.balance}`);
  }

  debit(amount) {
    this.balance -= amount;
    console.log(`O saldo após o débito é de R$ ${this.balance}`);
  }

  transferTo(anotherAccount, amount) {
    if (!(anotherAccount instanceof Account)) {
      throw 'ERRO: Informe uma conta válida.';
    }

    if (this.balance <= amount) {
      throw 'ERRO: Você não possui saldo suficiente para realizar essa operação.';
    }
    this.debit(amount);
    anotherAccount.credit(amount);

    console.log(`O saldo atual da conta de origem é de R$ ${this.balance}`);
    console.log(
      `O saldo atual da conta de destino é de R$ ${anotherAccount.balance}`
    );
  }
}
```

Modifique a classe `Account` acima conforme o diagrama de classe abaixo:

<div style="text-align:center;">
  <img src="https://github.com/reprograma/on25-IJS-orientacao-objetos-I/assets/26902816/72ffbe7a-8af6-42d5-90f7-f62284808858" />
</div>

Teste tudo o que foi criado.
