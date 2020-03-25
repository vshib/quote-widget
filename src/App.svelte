<script>
  import { onMount } from 'svelte'

  let currentQuote = ''

  let quotes = [
    'Imagination is the one weapon in the war against reality.',
    'Some quote 1',
    'Quote 2',
    'Some quote 2',
    'Some quote 3',
    'Some quote 4',
    'Some quote 5',
    'Some quote 6',
  ]

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
  :global(body) {
    background: #2b2a29;
  }
  .window {
    width: 320px;
    height: 150px;
    background: white;
    color: black;
    border: 1px solid black;
    font-size: 17px;
    border-radius: 4px;
    cursor: pointer;

    justify-content: center;
    align-items: center;

    flex-wrap: wrap;
    display: flex;
  }

  .quote-text {
    padding: 0 35px;
    width: 100%;
    display: flex;
    justify-content: flex-start;
  }
  .icon-quote-left {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-start;
    align-items: center;
    padding-top: 15px;
    padding-left: 15px;
    padding-right: 15px;
  }
  .icon-quote-right {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-end;
    align-items: center;
    padding-bottom: 15px;
    padding-left: 15px;
    padding-right: 15px;
  }

  .icon-arrows-ccw {
    color: #04a49c;
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    padding-bottom: 15px;
    align-items: center;
  }
</style>

<div class="window">

  <div class="icon-quote-left" />
  <div class="quote-text">{currentQuote}</div>
  <div class="icon-quote-right" />

  <div on:click={nextQuote} class="icon-arrows-ccw" />

</div>
