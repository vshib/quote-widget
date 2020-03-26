<script>
  import { onMount } from 'svelte'

  let currentQuote = ''
  let toolBlockEnabled = false

  let quotes = [
    'Написал код на бумажке. Отладил в голове.',
    'Почистил дорожку от снега. Повысил пропускную способность.',
    'Попросили исправить чужой код. сtrl+A; delete; пишу программу.',
    'Девушка сказала 100000 раз написать "Прости". for i:=1 to 100000 do writeln("Прости").',
    'Удобный интерфейс? Главное, что работает.',
    'Завел кошку, еще не придумал, как назвать. Пока обращаюсь к ней по айпишнику.',
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
  .quote-container {
    width: 320px;
    min-height: 150px;
    background: white;
    color: black;
    font-size: 17px;
    border-radius: 4px;
    cursor: pointer;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    display: flex;
    font-family: Roboto, Helvetica, Arial, sans-serif;
    font-weight: 400;
    line-height: 1.75;
  }

  .quote-container .quote-data .quote-text {
    padding: 0 45px;
    width: 100%;
    display: flex;
    justify-content: flex-start;
  }

  .quote-container .quote-data .icon-quote-left {
    justify-content: flex-start;
    padding: 15px 15px 0px 15px;
  }

  .quote-container .quote-data .icon-quote-right {
    justify-content: flex-end;
    padding: 0px 15px 15px 15px;
  }

  .quote-container .quote-tool .icon-arrows-ccw {
    color: #04a49c;
    justify-content: flex-start;
  }

  .quote-container .quote-tool {
    position: absolute;
    font-size: 60px;
  }

  .quote-data.opacity {
    opacity: 0.4;
  }
</style>

<div
  on:mouseleave={() => {
    toolBlockEnabled = false
  }}
  on:mouseenter={() => {
    toolBlockEnabled = true
  }}
  class="quote-container">

  <div class:opacity={toolBlockEnabled} class="quote-data full-flex">
    <div class="icon-quote-left full-flex" />
    <div class="quote-text">{currentQuote}</div>
    <div class="icon-quote-right full-flex" />
  </div>
  {#if toolBlockEnabled}
    <div class="quote-tool">
      <div on:click={nextQuote} class="icon-arrows-ccw full-flex" />
    </div>
  {/if}
</div>
