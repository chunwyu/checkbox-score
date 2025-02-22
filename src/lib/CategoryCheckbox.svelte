<script>
    let { categories } = $props();
</script>

<div>
    {#each Object.entries(categories) as [category, games]}
    <h1>{category}</h1>
        {#each games as game}
        <div>
            <input type="checkbox" id="cbox_{game}" />
            <label for="cbox_{game}">{game}</label>
        </div>
        {/each}
    {/each}
</div>
