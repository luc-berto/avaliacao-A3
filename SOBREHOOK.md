 o que é useState
	useState é um Hook do React que permite adicionar uma variável de estado
 ao seu componente. Atualizando o estado com base no estado anterior.
 Atualizando objetos e arrays no estado. Evitar recriar o estado inicial.
 
 import React, { useState } from 'react';

function Contador() {
  // Declara uma variável de estado "count" e a função para atualizá-la "setCount"
  const [count, setCount] = useState(0); // 0 é o valor inicial

  return (
    <div>
      <p>Você clicou {count} vezes</p>
      {/* Exemplo de uso: atualizando o estado ao clicar */}
      <button onClick={() => setCount(count + 1)}>
        Aumentar
      </button>
    </div>
  );
}

  o que  usefect
	O useEffect é um Hook do React que permite executar efeitos colaterais em componentes funcionais,
  como buscar dados (APIs), manipular o DOM diretamente ou configurar timers.
  
  
  import React, { useState, useEffect } from 'react';

function ExemploComponente() {
  const [data, setData] = useState(null);
  const [contador, setContador] = useState(0);

  // Exemplo 1: Executa APENAS na montagem (array de dependências vazio)
  useEffect(() => {
    console.log("Componente montado - Busca dados da API");
    // Ex: fetch('api/dados').then(...)
  }, []);

  // Exemplo 2: Executa sempre que 'contador' mudar
  useEffect(() => {
    document.title = `Contador: ${contador}`;
    console.log("Contador atualizado");
  }, [contador]);

  return (
    <div>
      <p>Contador: {contador}</p>
      <button onClick={() => setContador(contador + 1)}>Aumentar</button>
    </div>
  );
}
