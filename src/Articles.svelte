<script>
   import { onMount } from "svelte";
   const apiURL = "http://127.0.0.1:8000/posts";
   let data = [];

   onMount (async () => {
        const response = await fetch(apiURL);
        data = await response.json();
   });
</script>
    
        {#each data as item}
           <p>
                {item.title}
           </p> 
           <p>
               {item.category}
          </p> 
           <p>
                <img src={item.image} alt={item.title}>
           </p>
           <p>
                {@html item.body}
           </p>
           <p>
                {item.publisher}
           </p>
           <p>
                {item.date_created}
           </p>
        {/each}
    
<style>
    p img {
        width: 20em;
        height: 20em;
    }
</style>