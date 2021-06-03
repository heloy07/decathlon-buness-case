<script>
    import {fade} from 'svelte/transition';
    import {getContext} from 'svelte';
    
    //variables
    export let name = "";
    export let color="";

    let activeSmile = false;
    
   
    const {selected} = getContext("state");
</script>
{#if !activeSmile}
<button on:click={()=> selected(name)} transition:fade>
    <span
        aria-label="Homepage"
        id="test"
        class="{name} vtmn-text-8xl tablet:vtmn-text-6xl mobile:vtmn-text-4xl"
        style="
               color:{color} "
    />
</button>
{/if}

<style>
    button:focus {
        border: none;
        outline: none;
    }
    
    span {
        opacity: 0.7;
    }
    span:hover {
        opacity: 0.8;
    }
</style>
