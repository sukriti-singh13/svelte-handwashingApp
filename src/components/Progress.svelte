<script>
  export let isIncreasing;
</script>

<div class="progress-container">
  <div class="progress-bar" style="width:{isIncreasing}%">
    <span class="scren-only" />
  </div>
</div>

<style>
  .progress-container {
    margin: 20px 0;
    border: solid rgba(194, 194, 194) 1px;
  }

  .progress-bar {
    height: 30px;
    background-color: rgb(77, 199, 55);
  }
</style>
