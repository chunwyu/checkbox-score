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
        padding: 10px;

        font-family: Arial, Helvetica, sans-serif;
    }

    .category
    {
        display: flex;
        flex-flow: column;
        width: 200px;
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

    .total-score-box
    {
        margin: auto;
        width: 50%;
        border: 1px solid #990000;
        font-family: Arial, Helvetica, sans-serif;
    }

    .total-score-text
    {
        font-size: 28px;
        text-align: center;
    }

    .score
    {
        font-size: 40px;
        text-align: center;
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

<div class="total-score-box">
    <div class="total-score-text">
        <p>Total score</p>
    </div>

    <div class="score">
        <p>{playedGames.length} / {totalGames}</p>
    </div>
</div>
