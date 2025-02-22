<script lang="ts">
    import CategoryCheckbox from "$lib/CategoryCheckbox.svelte";
    import categories from "$lib/GameCategoryList.json";
</script>

<style>
    h1
    {
        font-family: Arial, Helvetica, sans-serif;
        font-size: 40px;
        text-align: center;
    }
</style>

<h1>Variety Gamer Score 2025</h1>
<CategoryCheckbox categories={categories} />