<script>
    export let hobbies = ['swiming', 'rock climbing', 'adventure', 'reading', 'travelling'];
</script>
<main>
    <h2>Hobbies</h2>
    {#each hobbies as hobby}
    <ul>
       {#if hobby.length < 10}
           <li>{hobby}</li>
        {/if}
    </ul>
    {/each}
</main>
<style>
    ul li{
        list-style:disc;
    }
    h2 {
        background-color: lightgreen;
        width: 100px;
        border-radius: 8px;
    }
</style>