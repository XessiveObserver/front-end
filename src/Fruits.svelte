<script>
    export let fruits = ['oranges', 'apples', 'bananas', 'grapes', 'berries']
</script>
<p>
    {#each fruits as fruit}
    <ul>
       {#if fruit.length < 7}
           <li>{fruit}</li>
        {/if}
    </ul>
    {/each}
</p>