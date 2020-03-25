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

  function getQuote() {
    const randomNumber = getRandomIntInclusive(0, quotes.length)
    const randomQuote = quotes[randomNumber]
    return randomQuote
  }

  function getRandomIntInclusive(min, max) {
    min = Math.ceil(min)
    max = Math.floor(max)
    return Math.floor(Math.random() * (max - min + 1)) + min
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
