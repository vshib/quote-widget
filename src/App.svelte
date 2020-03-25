<script>
  function hover() {
    console.log('focus')
  }
  function nextQuote() {
    console.log('next')
  }
</script>

<style>
  .window {
    width: 320px;
    height: 150px;
    background: white;
    color: black;
  }
  .window:hover {
    background: yellow;
  }
</style>

<div class="window" on:mouseover={hover} on:click={nextQuote} />
