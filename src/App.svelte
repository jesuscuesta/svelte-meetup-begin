<script>
  import Dc from "./dc.svelte";

  export let name;
  let src =
    "https://media1.tenor.com/images/4a96d6c6ce310c9cc1b10b21ea327651/tenor.gif?itemid=14666652";

  let count = 0;

  function votar() {
    count += 1;
  }
</script>

<style>
  main {
    text-align: center;
  }

  h1 {
    color: #ff3e00;
  }
</style>

<main>
  <h1>Hola {name.toUpperCase()}!</h1>
  <div>
    <img {src} alt={name} />
  </div>

  <div>
    <button on:click={votar}>
      Votos {count} {count === 1 ? 'vez' : 'veces'}
    </button>
  </div>

</main>

<main>
  <Dc />
</main>
