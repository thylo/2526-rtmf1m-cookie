<script lang="js">
    const {product} = $props();

    let items = $derived(new Array(product.count).fill(''));
</script>

<div>
<h3>{product.id}</h3>
{#each  items as item}
    <img class="product-image" src={`/products/${product.id}.png`} alt="" />
{/each}
</div>

<style>
    .product-image{
        width: 200px;
        aspect-ratio: 1;
        object-fit: cover;
    }
</style>