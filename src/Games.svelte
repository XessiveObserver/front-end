<script>
    export let games = [
        {
            'name': 'Chess',
            'definition': 'Is a game of logical thinking.'
        },
        {
            'name': 'Tennis',
            'definition': 'Tennis is a game competed for in opens.'
        },
        {
            'name': 'Basket ball',
            'definition': 'The most engaging game that works the whole body out.'
        },
        {
            'name': 'Net ball',
            'definition': 'Is like basket ball for the females.'
        }
    ]

    export let showGames = true;
    export const toggleGames = () => {showGames = !showGames}
</script>
<main>
    <button on:click="{toggleGames}">
        {#if showGames}
            +
        {:else}
            -
        {/if}
    </button>
    <h4>Games</h4>
    {#if !showGames}
    <ul>
        {#each games as game}
            <li><h2>{game.name}</h2></li>
            <li><p>{game.definition}</p></li>
        {/each}
    </ul>
    {/if}
</main>

<style>
    button {
        border-radius: 10px;
        float: right;
        margin-right: 8px;
        background-color: lightgreen;
        color:green;
        font-weight: bolder;
    }
    ul li {
        list-style: none;
    }
    h4{
        background-color: lightgreen;
        height: 20px;
        width: 60px;
        font-weight: bold;
        text-align: center;
        border-radius: 5px;
        margin-inline:inherit;
    }
</style>