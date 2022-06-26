<script>
    import Project from './Project.svelte'
    import Comment from './Comment.svelte'
    import Details from "./Details.svelte";

    async function fetchData(url) {
        const response = await fetch(url)
        if (response.ok) {
            const data = await response.json()
            return data
        } else {
            console.log(`Failing with http status code ${response.status} - ${response.statusText}. Rendering error screen`)
            throw new Error(response.statusText);
        }
    }
</script>

<header>
    <div class="navbar sub-navbar">
        <div class="container d-flex">
            <div class="title">Bookstore</div>
        </div>
    </div>
</header>

<ul>
    <li>
        <Project
                title="The Comedy of Errors">
            <div slot="details">
                {#await fetchData(`/api/details/1`)}
                    <p>loading</p>
                {:then details}
                    <Details details="{details}"/>
                {:catch error}
                    <p style="color: red">{error.message}</p>
                {/await}
            </div>
            <div slot="reviews">
                {#await fetchData(`/api/reviews/1`)}
                    <p>loading</p>
                {:then reviews}
                    {#each reviews as review}
                        <Comment name="{review.reviewer}" rating="{review.rating}">
                            <p>{review.text}</p>
                        </Comment>
                    {/each}
                {:catch error}
                    <p style="color: red">{error.message}</p>
                {/await}
            </div>
        </Project>
    </li>
</ul>
<style>

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

    header {
        color: #0F1111;
    }

    .title {
        color: white;
        font-size: larger;
    }

    header .navbar.sub-navbar {
        height: 60px;
        background-color: #045462;
        font-size: 15px;
        padding-top: 0;
        padding-bottom: 0;
        box-shadow: 0px 0px 4px rgba(0, 0, 0, 0.25);
        z-index: 1;
    }

</style>