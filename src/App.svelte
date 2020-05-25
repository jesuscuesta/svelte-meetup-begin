<script>
  import Dc from "./dc.svelte";

  export let name;
  let src =
    "https://media1.tenor.com/images/4a96d6c6ce310c9cc1b10b21ea327651/tenor.gif?itemid=14666652";

  const superheroes = {
    miembros : 2,
    nombres : "Wonderworman, SuperGirl",
    poderes : "Volar, Superfuerza",
    planeta : "Algún lugar"
  };
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

</main>

<main>
  <Dc
    miembros={3}
    nombres="Superman, Batman, Linterna Verde"
    poderes={'Volar, Superfuerza, ser de color verde'}
    planeta={'La tierra'} />

  <Dc {...superheroes} />
</main>
