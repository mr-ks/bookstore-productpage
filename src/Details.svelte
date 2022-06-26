<script>
    export let details;
</script>

<article>

    <ul>
        <li>
            <div style="text-align: center;">
                <p>Type</p>
                <span class="material-symbols-outlined">book</span>
                <p class="bold">{details.type}</p>
            </div>
        </li>
        <li>
            <div style="text-align: center;">
                <p>Pages</p>
                <span class="material-symbols-outlined">auto_stories</span>
                <p class="bold">{details.pages}</p>
            </div>
        </li>
        <li>
            <div style="text-align: center;">
                <p>Publisher</p>
                <span class="material-symbols-outlined">apartment</span>
                <p class="bold">{details.publisher}</p>
            </div>
        </li>
        <li>
            <div style="text-align: center;">
                <p>Language</p>
                <span class="material-symbols-outlined">language</span>
                <p class="bold">{details.language}</p>
            </div>
        </li>
        <li>
            <div style="text-align: center;">
                <p>ISBN-13</p>
                <span class="material-symbols-outlined">confirmation_number</span>
                <p class="bold">{details.isbn13}</p>
            </div>
        </li>
    </ul>


</article>

<style>
    .bold {
        font-weight: bold;
    }

    ul {
        list-style: none;
        padding: 0;
        margin: 0.5rem;
        display: flex;
    }

    @media (max-width: 600px) {
        ul {
            flex-direction: column;
        }
    }

    li {
        padding: 0.5rem;
        flex: 1 1 50%;
        min-width: 200px;
    }

    .material-symbols-outlined {
        font-variation-settings: 'FILL' 0,
        'wght' 100,
        'GRAD' 200,
        'opsz' 96
    }

</style>