<script>
    import carouselData from '../data/carousel';
    import Carousel from "svelte-carousel";
    
    //the name of the person of the current carousel image
    export let nameDisplayed = '';
    //data from json
    const carouselPhotos = [...carouselData];
  
</script>

<div class="masked">
    <Carousel
        let:loaded
        autoplay={true}
        arrows={false}
        dots={false}
        on:pageChange={(event) =>{
            nameDisplayed=carouselPhotos[event.detail].name;
            }
        }
            
    >
        {#each carouselPhotos as { image, name, text, date }, imageIndex (image)}
            <div class="img-container">
                {#if loaded.includes(imageIndex)}
                    <div class="carousel-container">
                        <img src={image} alt="carouselimg" />

                        <div
                            class="txt-image 
                                    mobile:vtmn-text-xs 
                                    tablet:vtmn-text-sm
                                    small-desktop:vtmn-text-xl 
                                    medium-desktop:vtmn-text-2xl  
                                    vtmn-text-4xl 
                                    vtmn-text-grey-light-3
                                    "
                        >
                            <div class="vtmn-text-4xl">
                                {name}
                                <span class="vtmn-text-lg">{date}</span>
                            </div>

                            {text}
                        </div>
                    </div>
                {/if}
            </div>
        {/each}
    </Carousel>
</div>

<style>
    .masked {
        width: 100%;
        height: 100%;
        background-color: white;
        -webkit-mask-image: url(../assets/rounded_rectangle_flip.svg);
        mask-image: url(../assets/rounded_rectangle_flip.svg);
        -webkit-mask-repeat: no-repeat; /*Firefox*/
    }
    .carousel-container {
        position: relative;
    }
    img {
        max-width: none;
        width: 160%;
    }
    .txt-image {
        position: absolute;
        text-align: left;
        top: 60%;
        left: 50%;
        width: 80%;
        text-shadow: 2px 2px #000000;
        transform: translate(-50%, -50%);
    }
    @media (max-width: 1200px) {
        .txt-image {
            top: 25%;
            left: 40%;
            width: auto;
        }
    }
    @media (max-width: 600px) {
        .txt-image {
            display: none;
        }
    }

    #quote {
        color: white;
        position: relative;
        top: 15%;
        left: 25%;
        font-size: 5em;
        font-family: "Roboto";
    }
</style>
