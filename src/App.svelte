<script lang="ts">
  import Shop from "./components/shop/Shop.svelte";


  let count = $state(0);

  function onCookieClick(){
    console.log('click');
    count ++;
  };
</script>

<main class="application">
  <div class="frite-bar">
    <p>Frites: {count}</p>
    <button class="frite-button" onclick={onCookieClick}>
      <img src="/frite.png" alt="frite">
    </button>
  </div>
  <div class="inventory">
  </div>
  <div class="shop">
    <Shop count={count} />
  </div>
</main>

<style>
  .application {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    height: 100%;
    background: pink;
    position: fixed;
    width: 100%;
  }
  
  .frite-bar{
    background: black;
    color: white;
    font-size: 6.25em;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .frite-button{
    background-color: transparent;
    border-radius: 0%;
    border: 0cap;
  }

  .inventory{
    background: yellow;
  }
  .shop{
    background: red;
  }
</style>
