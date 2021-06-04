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
	<div class="vtmn-border-b-4 mobile:vtmn-rounded-b-3xl vtmn-border-orange vtmn-rounded-br vtmn-rounded-b vtmn-rounded-4xl">
		<!--logo-->
		<img
			class="vtmn-w-2/12 mobile:vtmn-w-4/12 logo"
			src="./Logos_Web/Logo_Decathlon_RVB.png"
			alt="Decathlon Logo"
		/>
		<div class="content ">
			<div class="vtmn-grid mobile:vtmn-grid-cols-1 vtmn-grid-cols-2 ">
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
		.logo{
			/*width:100px !important;*/
		}
	}
	@media(max-width:900px){
		.logo{
			/*width:200px!important;*/
		}
	}
	.logo {
		
		
		margin-top: 50px;
		/*width: 300px;*/
		margin-left: 8%;
	}
	@media(min-width:600px){
		.banner{
		position:relative;
		right:-5%;
		z-index:2;
		
	}
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
