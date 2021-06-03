<script>
    import Icon from "./Icon.svelte";
    import { fade, fly } from "svelte/transition";
    import { setContext, getContext } from "svelte";
    import iconsData from '../data/icons';
    

    export let satisfaction;
    let iconClicked = false;
    //contains svgs names and colors
    let iconNames = [...iconsData];
    const state = {
        selected: selectIcon,
    };
    /*When an Icon is selected, 
    every other icons disappear and the props satisfaction is passed
    to the parent then to the Banner with a new value*/
    function selectIcon(iconName) {
        iconNames = iconNames.filter((icon) => icon.className === iconName);
        iconClicked = true;
        switch (iconName) {
            case "vtmx-emotion-laugh-line":
                satisfaction+=2;
                break;
            case "vtmx-emotion-fill":
                satisfaction++;
                break;
            case "vtmx-emotion-normal-line":
                
                break;
            case "vtmx-emotion-sad-line":
                satisfaction--;
                break;
            case "vtmx-emotion-unhappy-line":
                satisfaction-=2;
                break;
            default:
        }
    }
    setContext("state", state);
</script>

<div class="content">
    {#if !iconClicked}
        <div class="vtmn-grid vtmn-grid-cols-5 vtmn-space-x-0 ">
            {#each iconNames as { className, color }}
                <Icon name={className} {color} />
            {/each}
        </div>
    {:else}
        <h2
            in:fly={{ y: 200, duration: 2000 }}
            out:fade
            class="message vtmn-text-7xl tablet:vtmn-text-2xl mobile:vtmn-text-2xl"
        >
            Merci pour ton avis
        </h2>
        <div in:fly={{ y: 200, duration: 2000 }}>
            <Icon name={iconNames[0].className} color={iconNames[0].color} />
        </div>
    {/if}
</div>

<style>
    .message {
        color: var(--info);
        text-align: center;
        font-weight: 600;
    }
    .content {
        width: fit-content;
        width: -moz-fit-content; /*Firefox*/
        margin: auto;
    }
</style>
