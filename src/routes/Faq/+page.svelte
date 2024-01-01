<script>
    /**
   * @type {{ name: any; } | null}
   */
    let data = null;
  
    async function fetchPokemonData() {
      try {
        const response = await fetch('https://pokeapi.co/api/v2/pokemon');
        data = await response.json();
      } catch (err) {
        console.error('Erro:', err);
      }
    }
  
    fetchPokemonData();
  </script>

  {#if data}
    <p>Nome do Pokémon: {data.name}</p>
  {:else}
    <p>Carregando...</p>
  {/if}
  