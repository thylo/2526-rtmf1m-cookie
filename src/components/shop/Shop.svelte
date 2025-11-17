<script lang="ts">

let {count} = $props();

const products = [
    {name: 'Pointeur', price: 10, id: 'cursor'},
    {name: 'Moules', price: 20, id: 'moules'},
    {name: 'Grand-mere', price: 30, id: 'grand_mere'},
];

</script>


<h1>Shop :D</h1>

<ul>
    {#each products as product}
        <li>
            <button disabled={count < product.price}> {product.name} {product.price} frites
                <img class="product-image" src={`/products/${product.id}.png`} alt="">
            </button>
        </li>
    {/each}
</ul>

<style>
    .product-image{
        width: 100px;
        aspect-ratio: 1;
      object-fit: cover;
    }
</style>