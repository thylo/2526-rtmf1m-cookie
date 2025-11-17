<script lang="ts">
    import {groupBy} from 'lodash';

    const {inventory} = $props();

    let groupedInventory = $derived(groupBy(inventory, 'id'));

    $inspect(groupedInventory);
</script>

<div class="c-inventory">
    <h1>Inventory</h1>

    <ul>
        {#each inventory as product}
            <li>
                {product.id}
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