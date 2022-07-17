<script>
  import { createEventDispatcher } from "svelte";
  import Progress from "./Progress.svelte";
  const dispatch = createEventDispatcher();
  let totalSeconds = 20;

  let secondsLeft = totalSeconds;
  $: isIncreasing = ((totalSeconds - secondsLeft) / totalSeconds) * 100;
  let isRunning = false; //if not applied button starts a lot of timer
  function setTimer() {
    isRunning = true;
    let timer = setInterval(() => {
      secondsLeft -= 1;
      if (secondsLeft == 0) {
        clearInterval(timer);
        isRunning = false;
        secondsLeft = totalSeconds;
        dispatch("end");
      }
    }, 1000);
  }
</script>

<main>
  <h3 class="seconds-text">Seconds left:{secondsLeft}</h3>
  <Progress {isIncreasing} />
  <button
    type="button"
    class="btn start"
    on:click={setTimer}
    disabled={isRunning}>Start</button
  >
</main>

<style>
  button {
    font-size: 1rem;
    width: 100%;
    background-color: black;
    margin: 1rem 0;
    padding: 1rem 3rem;
    border-radius: 5px;
    color: white;
  }
  .start[disabled] {
    background-color: darkgrey;
    cursor: not-allowed;
  }
  .seconds-text{
    font-weight: 500 !important;
  }
  
</style>
