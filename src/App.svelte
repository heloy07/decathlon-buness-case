<script>
	import Carousel from "./components/Carousel.svelte";
	import Banner from "./components/Banner.svelte";
	import Rating from "./components/Rating.svelte";
	import {setContext} from 'svelte';
	//variables
	export let name;
	export let satisfaction = 87;
	let nameDisplayed = '';
	
	//state, for the size of this project state and context are not really relevant,
	//we could only be using props drilling but I want to test it
	const state = {
        changeSatisfaction: changeSatisfaction,
		selected: selectIcon,
    };
	
	//state functions
	function changeSatisfaction(){
		satisfaction++;
	}
	function selectIcon(name){
		console.log('selectedicon'+name);
	}
	setContext(state,"state");
</script>

<main
	class="vtmn-border-double vtmn-border-2 vtmn-border-grey vtmn-rounded-3xl"
>
	<div class="vtmn-border-b-4 vtmn-border-orange vtmn-rounded-br">
		<!--logo-->
		<img
			class="logo"
			src="./Logos_Web/Logo_Decathlon_RVB.png"
			alt="Decathlon Logo"
		/>
		<div class="content ">
			<div class="vtmn-grid vtmn-grid-cols-2 ">
				<div class="banner">
					<Banner bind:satisfaction bind:nameDisplayed/>
				</div>
				<div class="carousel">
					<Carousel bind:nameDisplayed/>
				</div>
			</div>
			<div class="rating">
				<Rating bind:satisfaction/>
			</div>
			
		</div>
	</div>

</main>

<style>
	main {
		text-align: center;
		margin: 0 auto;
		background: url("../assets/background.svg");
		background-repeat: no-repeat;
	}

	@media (min-width: 640px) {
		main {
			overflow: hidden;
		}
		.content {
			width: 90%;
			margin-left: 5%;
			margin-top: 5%;
		}
	}
	@media (max-width: 639px) {
		.content {
			width: 90%;
			margin-left: 5%;
			margin-top: 5%;
		}
	}
	.logo {
		
		
		margin-top: 50px;
		width: 250px;
		margin-left: 8%;
	}
	.banner{
		position:relative;
		right:-5%;
		z-index:2;
		height:fit-content(100em);
	}
	.carousel{
		position:relative;
		margin-top:10%;
	}
	.rating{
		margin-top: -10%;
		margin-bottom:5%;
		z-index:3;
		
		
	}
</style>
