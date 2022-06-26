<script>
    export let title;
</script>

<article>
    <div>
        <h2>{title}</h2>
        <a href="https://en.wikipedia.org/wiki/The_Comedy_of_Errors">Wikipedia Summary</a>: The Comedy of Errors is one
        of <b>William Shakespeare's</b> early plays. It is his shortest and one of his most farcical comedies, with a
        major part of the humour coming from slapstick and mistaken identity, in addition to puns and word play.
    </div>
    <div class="detail">
        <h3>Details</h3>
        <slot name="details"></slot>
    </div>
    <div>
        <h3>Reviews</h3>
        <slot name="reviews"></slot>
    </div>
</article>

<style>
    article {
        border: 1px #ccc solid;
        border-radius: 4px;
        position: relative;
    }

    article > div {
        padding: 1.25rem;
    }

    h2,
    h3 {
        margin: 0 0 0.5rem;
    }

    h3 {
        font-size: 0.875rem;
        font-weight: 500;
        letter-spacing: 0.08em;
        text-transform: uppercase;
    }

    .detail {
        background-color: #eee;
        border-top: 1px #ccc solid;
    }
</style>