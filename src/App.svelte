<script>
  import HowTo from "./components/Howto.svelte";
  import Time from "./components/Time.svelte";
  let audio;
  function timerEnds() {
    audio.play();
  }
</script>

<main class="container mx-auto px-40">
  <h1 class="text-center">Hand Washing App</h1>

  <Time on:end={timerEnds} />
  <HowTo />
  <h3 class="text-center">
    <a class="mx-1" href="https://www.who.int/gpsc/clean_hands_protection/en/">
      Picture Source
    </a>

    <a href="https://freesound.org/people/metrostock99/sounds/345086/ ">
      Sound Source
    </a>
  </h3>

  <audio bind:this={audio}><source src="sound.wav" /></audio>
</main>

<style>
  h1 {
    font-weight: 800;
    font-size: 1.5rem;
  }
  h3 {
    font-weight: 500;
    text-decoration: underline;
    color: blue;
  }
</style>
