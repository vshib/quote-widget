<script>
  function hover() {
    console.log('hover')
  }
  function nextQuote() {
    console.log('next')
  }
  let quotes = [
    'Вы пробовали выключить и снова включить?',
    'Романтический ужин при свичах в компании соблазнительных цисок.',
  ]
  function getQuote(){
    
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
