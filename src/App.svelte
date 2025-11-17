<script lang="js">
  import Shop from "./components/shop/Shop.svelte";
  import Inventory from "./components/inventory/Inventory.svelte";


  let count = $state(0);
  let inventory = $state([]);

  function onCookieClick(){
    console.log('click');
    count ++;
  }

    const buyItem = (product)=>{
      count-=product.price;
      inventory= [...inventory, product];
    }

  $inspect(inventory); // will console.log when `inventory` change

</script>

<main class="application">
  <div class="frite-bar">

    <p>Frites: {count}</p>
    <button class="frite-button" onclick={onCookieClick}>
      <img src="/frite.png" alt="frite">
    </button>
  </div>
  <div class="inventory">
      <Inventory />
  </div>
  <div class="shop">
    <Shop count={count} {buyItem}/>
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
      height: 100%;
    overflow: hidden;
  }
  .shop{
    background: red;
  }
</style>
