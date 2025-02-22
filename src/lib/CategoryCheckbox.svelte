<script>
    let { categories } = $props();
    /**
	 * @type {string | any[]}
	 */
    let playedGames = $state([]);

    let totalGames = Object.entries(categories).reduce((total, currCategory) => total + currCategory[1].length, 0);
</script>

<style>
    .checkbox-set-container
    {
        display: flex;
        flex-flow: row wrap;
    }

    .category
    {
        display: flex;
        flex-flow: column;
        width: 400px;
    }

    .category-item
    {
        display: flex;
        flex-flow: row;
        width: 100%;
        height: 30px;
    }

    .checkbox
    {
        display: block;
        width: 20px;
    }

    .checkbox-label
    {
        display: block;
        width: 350px;
    }

    h1
    {
        display: block;
        width: 100%;
    }
</style>

<div class="checkbox-set-container">
    {#each Object.entries(categories) as [category, games]}
    <div class="category">
        <h1>{category}</h1>
        {#each games as game}
        <div class="category-item">
            <div class="checkbox">
                <input 
                    type="checkbox"
                    id="cbox_{game}"
                    value={game}
                    bind:group={playedGames}
                />
            </div>
            <div class="checkbox-label">
                <label for="cbox_{game}">{game}</label>
            </div>
        </div>
        {/each}
    </div>
    {/each}
</div>

<p>{playedGames.length} / {totalGames}</p>
