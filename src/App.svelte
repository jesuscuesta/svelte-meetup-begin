<script>
  import Dc from "./dc.svelte";

  export let name;

  let marca = true;

  let promise = toggle();

  const superheroes = {
    miembros: 2,
    nombres: "Wonderworman, SuperGirl",
    poderes: "Volar, Superfuerza",
    planeta: "Algún lugar",
    src:
      "https://media1.tenor.com/images/4a96d6c6ce310c9cc1b10b21ea327651/tenor.gif?itemid=14666652"
  };

  const marvelListado = {
    miembros: 2,
    nombres: "Ciclope, Lobezno",
    poderes: "Rayos, Garras",
    planeta: "La Tierra",
    src:
      "https://www.laguiadelvaron.com/wp-content/uploads/2017/03/media1.popsugar-assets.com-Here-He-Getting-Down-Business.gif"
  };

  async function toggle() {
	const resultado = await setTimeout(() => marca = !marca, 3000);
	return marca;
  }

  function handleClick() {
		promise = toggle();
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
</main>

<main>
  <button on:click={handleClick}>Cambio</button>
  {#await toggle}
    <p>...buscando héroes</p>
  {:then number}
    <p>Hemos conseguido encontrarlos</p>
  {:catch error}
    <p style="color: red">{error.message}</p>
  {/await}

  {#if marca}
    <Dc {...superheroes} />
  {:else}
    <Dc {...marvelListado} />
  {/if}
</main>
