<script>
    export let post = [
    {
        title: 'Security', content: 'Study Security well jack!'
    },
    {
        title: 'Web design', content: 'Study web design and devs well jack!'
    },
    {
        title: 'Data Science', content: 'Study Data science well jack!'
    }
]

let prefix = '';
let title ='';
let content = '';
let i = 0;

$: filteredPost = prefix ? post.filter(article =>{
    const postDetail = `${article.title}, ${article.content}`;
    return postDetail.toLowerCase().startsWith(prefix.toLowerCase());
}): post;

$: selected = filteredPost[i];
$: resetInputs(selected);

function create(){
    post = post.concat({title, content})
    i = post.length - 1;
    title = content = '';
}

function update(){
    selected.title = title;
    selected.content = content;
    post = post;
}

function remove(){
    // remove from source post array not selected array
    const index = post.indexOf(selected);
    post = [...post.slice(0, index), ...post.slice(index + 1)];

    title = content = '';
    i = Math.min(i, filteredPost.length - 2);
}

function resetInputs(article) {
    title = article ? article.title : '';
    content = article ? article.content : '';
}
</script>
<h2>Create Article</h2>
<input placeholder='filter prefix' bind:value={prefix}>

<select bind:value={i} size={5}>
    {#each filteredPost as article, i}
        <option value={i}>{article.title}, {article.content}</option>
    {/each}
</select>

<label><input bind:value={title} placeholder="title"></label>
<label><input bind:value={content} placeholder="content"></label>

<div class="buttons">
    <button class="create" on:click={create} disabled={!title || !content}>Create</button>
    <button class="update" on:click={update} disabled={!title || !content || !selected}>Update</button>
    <button class="delete" on:click={remove} disabled={!selected}>Delete</button>
</div>

<style>
    * {
        font-family: inherit;
        font-size: inherit;
    }
    input {
        display: block;
        margin: 0 0 0.5em 0;
        border-radius: 8px;
    }
    select {
        float: left;
        margin: 0 1em 1em 0;
        widows: 14em;
        border-radius: 10px;
    }
    .buttons{
        clear: both;
        
    }
    .create {
        border-radius: 8px;
        background-color: seagreen;
        color:azure;
        font-weight: bold;
    }
    .update {
        border-radius: 8px;
        background-color:rgb(15, 70, 221);
        color:azure;
        font-weight: bold;
    }
    .delete {
        border-radius: 8px;
        background-color: red;
        color:azure;
        font-weight: bold;
    }
</style>