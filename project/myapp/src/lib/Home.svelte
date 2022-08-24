<script>
    import {fade,fly} from 'svelte/transition'
    export let pageName  = "GOod page"
    let hasAdded = false;
    
    let names = [1,2,3]

    const changeName = ()=>{
        pageName = "we are changed"
        hasAdded = true;
        names.push(4);
        console.log("LOG ::: names",names)
    }
</script>

<div>
    <h1 transition:fly>Home Page : {pageName}</h1>
    <input placeholder="Enter title here"  bind:value={pageName}/>
    {#if hasAdded === true}
        <h1 transition:fly>Home Page : {pageName}</h1>
    {/if}
    {#each names as name}
        <h3 transition:fly>{name}</h3>
    {/each}
    <button on:click={changeName}>Add Stuff</button>

</div>