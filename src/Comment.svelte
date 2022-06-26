<script>
    export let name;
    export let rating;


    function ratingIsPresent() {
        if (rating === undefined) {
            return false
        }
        const keys = Object.keys(rating)
        return keys.length !== 0 && keys.indexOf("stars") > -1 && keys.indexOf("color") > -1
    }

</script>

<article>
    <div class="header">

        <div class="details">
            <h4>{name}</h4>
            {#if ratingIsPresent()}
                {#each Array(rating.stars) as _, index (index)}
                    <span class="material-symbols-outlined {rating.color}">star</span>
                {/each}
                {#each Array(5 - rating.stars) as _, index (index)}
                    <span class="material-symbols-outlined">grade</span>
                {/each}
            {/if}
        </div>
    </div>
    <div class="body">
        <slot></slot>
    </div>
</article>

<style>
    article {
        background-color: #fff;
        border: 1px #ccc solid;
        border-radius: 4px;
        padding: 1rem;
    }

    .red {
        color: red;
    }

    .blue {
        color: blue;
    }

    .black {
        color: black;
    }

    .header {
        align-items: center;
        display: flex;
    }

    .details {
        flex: 1 1 auto;
        margin-left: 0.5rem
    }

    h4 {
        margin: 0;
    }

    .body {
        margin-top: 0.5rem;
    }

    .body :global(p) {
        margin: 0;
    }
</style>