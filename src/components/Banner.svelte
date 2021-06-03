<script>
   export let satisfaction = "87";
   export let nameDisplayed ='';
   import {fly,fade} from 'svelte/transition'
   /*The svg is directly embeded because it was easier to deal with  text
   The only props we have are satisfaction in % and the name that comes from Carousel*/
</script>

<svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 viewBox="0 0 964 970" style="enable-background:new 0 0 964 970;" xml:space="preserve">
<style type="text/css">
	.st0{fill:#FFFFFF;}
</style>
<path class="st0" d="M856.5,803.8L5.7,964L0,36.9C0,16.5,14.8,0,33,0h894.5c18.2,0,33,16.5,33,36.9l0.3,384.1
	C960.8,606.7,992.3,753.9,856.5,803.8z"/>
    <text x="100" y="20" font-family="Roboto">
        {#key satisfaction}
        <tspan in:fly={{ y: 200, duration: 2000 }}  dy="1.2em" class="warning" font-size="164" fill="var(--warning)"
            >{satisfaction}%</tspan
        ><br />
        {/key}
        
        <tspan x="100" dy="1.2em" font-size="96">DE NOS SPORTIFS</tspan>
        <tspan x="100" dy="1.2em" font-size="96">SONT SATISFAITS</tspan>
        <tspan x="100" dy="1.2em" fill="var(--info)" font-size="96"
            >ET VOUS ?</tspan
        >
        <tspan x="100" dy="3.5em" font-size="32" 
            >Comme {nameDisplayed}, nous espérons que chacun de nos</tspan
        >
        <tspan x="100" dy="1.2em" font-size="32"
            >fidèles sportifs continue d'être satisfait, jour après jour.</tspan
        >
    </text>
</svg>

<style>
    svg {
        filter: drop-shadow(0px 3px 50px rgb(104, 119, 135));
    }
    text {
        margin-top: 25%;
    }
    .warning {
        color: var(--warning);
    }
</style>
