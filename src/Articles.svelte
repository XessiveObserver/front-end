<script>
   import { onMount } from "svelte";
   const apiURL = "http://127.0.0.1:8000/articles";
   let data = [];

   onMount (async () => {
        const response = await fetch(apiURL);
        data = await response.json();
   });
</script>
    
        {#each data as item}
           <p>
                {item.article_title}
           </p> 
           <p>
                <img src="{item.article_image}" alt="{item.article_title}">
           </p>
           <p>
                {@html item.article_body}
           </p>
           <p>
                {item.article_author}
           </p>
           <p>
                {item.date_of_creation}
           </p>
        {/each}
    
<style>
    p img {
        width: 20em;
        height: 20em;
    }
</style>