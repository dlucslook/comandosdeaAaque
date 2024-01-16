# Jogo de Heróis

## Escolha seu Herói

1. **Nome do Herói:** [Digite o nome]
2. **Idade do Herói:** [Digite a idade]
3. **Tipo do Herói:**
   - [x] Mago
   - [ ] Guerreiro
   - [ ] Monge
   - [ ] Ninja

## Realizar Ataque

Clique no botão para realizar o ataque:

```html
<button onclick="realizarAtaque()">Atacar</button>
<div id="resultado"></div>

function realizarAtaque() {
  const nome = document.getElementById('nome').value;
  const idade = document.getElementById('idade').value;
  const tipo = document.getElementById('tipo').value;

  const heroi = new Heroi(nome, idade, tipo);
  heroi.atacar();
}

class Heroi {
  constructor(nome, idade, tipo) {
    this.nome = nome;
    this.idade = idade;
    this.tipo = tipo;
  }

  atacar() {
    let ataque;

    switch (this.tipo) {
      case 'mago':
        ataque = 'usou magia';
        break;
      case 'guerreiro':
        ataque = 'usou espada';
        break;
      case 'monge':
        ataque = 'usou artes marciais';
        break;
      case 'ninja':
        ataque = 'usou shuriken';
        break;
      default:
        ataque = 'usou um ataque indefinido';
    }

    const resultadoElement = document.getElementById('resultado');
    resultadoElement.textContent = `O ${this.tipo} ${this.nome} atacou usando ${ataque}`;
  }
}
