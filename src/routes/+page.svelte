<script lang="ts">
    import CategoryCheckbox from "$lib/CategoryCheckbox.svelte";
    let categoriesList = {
        "FPS": [
            "Call of Duty",
            "Bioshock"
        ],
        "RPG": [
            "Final Fantasy",
            "Mass Effect",
            "Baldur's Gate"
        ]
    };
</script>

<h1>wtf?</h1>
<CategoryCheckbox categories={categoriesList} />