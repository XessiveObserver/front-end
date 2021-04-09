<script>
    export let topics = [
        {
            'name': 'Algorithms',
            'definition': 'An algorith is the way a program executes.'
        },
        {
            'name': 'Data Structures',
            'definition': 'Data structures can be Lists or Arrays, Dictionaries or Maps.'
        },
        {
            'name': 'Syntax',
            'definition': 'Syntax is a way a computer programme is styled.'
        },
        {
            'name': 'Debugging',
            'definition': 'Debugging is simply fixing bugs in code.'
        }
    ]

    export let showTopics = true;
    export const toggleTopics = () => {showTopics = !showTopics}
</script>
<main>
    <button on:click="{toggleTopics}">
        {#if showTopics}
            +
        {:else}
            -
        {/if}
    </button>
    <h4>Topics</h4>
    <ul>
        {#each topics as topic}
        {#if !showTopics}
            <li><h2>{topic.name}</h2></li>
            <li><p>{topic.definition}</p></li>
            {/if}
        {/each}
    </ul>
    
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