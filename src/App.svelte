<script>
  import { onMount } from 'svelte'

  let currentQuote = ''

  let quotes = [
    'Quote 1',
    'Some quote 1',
    'Quote 2',
    'Some quote 2',
    'Some quote 3',
    'Some quote 4',
    'Some quote 5',
    'Some quote 6',
  ]

  function hover() {
    console.log('hover')
  }

  function nextQuote() {
    currentQuote = getQuote()
  }

  function getQuote() {
    const randomNumber = getRandomIntInclusive(0, quotes.length - 1)
    const randomQuote = quotes[randomNumber]
    return randomQuote
  }

  function getRandomIntInclusive(min, max) {
    min = Math.ceil(min)
    max = Math.floor(max)
    return Math.floor(Math.random() * (max - min + 1)) + min
  }

  onMount(nextQuote)
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

<div class="window" on:mouseover={hover} on:click={nextQuote}>{currentQuote}</div>
