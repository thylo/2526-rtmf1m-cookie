<script lang="ts">
    import Item from "./Item.svelte";

    const inventory = [
        {id: 'cursor', count: 10},
        {id: 'moules', count: 2},
        {id: 'grand_mere', count: 3},
    ];

</script>

<div class="c-inventory">
    <h1>Inventory</h1>

    <ul>
        {#each inventory as product}
            <li>
                <Item {product} />
            </li>
        {/each}
    </ul>
</div>

<style>
.c-inventory{
    height: 100%;
    overflow: auto;
}
</style>