# challenge-amigo-secreto
Desafio completo para o curso da Challenges ONE(ORACLE)

# Amigo Secreto

Este projeto é uma aplicação simples que permite aos usuários inserir nomes de amigos em uma lista e, em seguida, realizar um sorteio aleatório para determinar quem será o "amigo secreto".

## Funcionalidades
- Adicionar nomes à lista.
- Validar entrada para garantir que o nome não seja vazio.
- Exibir a lista de amigos na página.
- Sortear um amigo aleatoriamente.
- Exibir o nome sorteado na tela.

## Tecnologias Utilizadas
- HTML
- CSS
- JavaScript

## Como Usar
1. Insira um nome no campo de texto.
2. Clique no botão "Adicionar" para incluir o nome na lista.
3. Após adicionar todos os amigos desejados, clique em "Sortear Amigo".
4. O nome sorteado será exibido na tela.

## Estrutura do Código

### 1. Criar um Array para Armazenar os Nomes
O projeto usa um array chamado `amigos` para armazenar os nomes inseridos pelo usuário:
```javascript
let amigos = [];
```

### 2. Função para Adicionar Amigos
A função `adicionarAmigo()` captura o valor do campo de entrada, valida se o nome não está vazio e o adiciona ao array:
```javascript
function adicionarAmigo() {
    let input = document.getElementById("nome");
    let nome = input.value.trim();

    if (nome === "") {
        alert("Por favor, insira um nome.");
        return;
    }

    amigos.push(nome);
    input.value = "";
    atualizarLista();
}
```

### 3. Função para Atualizar a Lista de Amigos
A função `atualizarLista()` exibe os nomes na tela:
```javascript
function atualizarLista() {
    let lista = document.getElementById("lista-amigos");
    lista.innerHTML = "";
    
    amigos.forEach(nome => {
        let item = document.createElement("li");
        item.textContent = nome;
        lista.appendChild(item);
    });
}
```

### 4. Função para Sortear um Amigo
A função `sortearAmigo()` seleciona aleatoriamente um nome da lista:
```javascript
function sortearAmigo() {
    if (amigos.length === 0) {
        alert("A lista está vazia. Adicione amigos antes de sortear.");
        return;
    }

    let indiceSorteado = Math.floor(Math.random() * amigos.length);
    let amigoSorteado = amigos[indiceSorteado];

    document.getElementById("resultado").textContent = `Amigo sorteado: ${amigoSorteado}`;
}
```

## Como Executar o Projeto
1. Baixe ou clone este repositório.
2. Abra o arquivo `index.html` em um navegador.
3. Utilize os botões para adicionar nomes e realizar o sorteio.

## Melhorias Futuras
- Permitir a remoção de nomes da lista.
- Impedir nomes duplicados.
- Melhorar o design com animações CSS.

## Autor
Desenvolvido por Lara Camile.

