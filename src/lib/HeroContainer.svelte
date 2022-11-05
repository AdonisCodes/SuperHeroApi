<script>
// @ts-nocheck
import { fade, blur, fly, slide, scale } from "svelte/transition";

    import Appearance from "./HeroContainer/Appearance.svelte";

// @ts-nocheck

    import Biography from "./HeroContainer/Biography.svelte";
    import MoreInfo from "./HeroContainer/MoreInfo.svelte";

// @ts-nocheck

    import Stats from "./HeroContainer/Stats.svelte";

    export let hero;
    let display = [true, false, false, false]


    function swapper(index) {

        if (display[index] == true) {
            return
        }
        if (display[index] == false) {
            display[0] = false
            display[1] = false
            display[2] = false
            display[3] = false

            display[index] = true
        }
    }
</script>

<div class="mainHeroContainer">
    <div class="HeroImage">
        <!-- svelte-ignore a11y-img-redundant-alt -->
        <img class="hover" src="{hero.image.url}" onerror="if (this.src != 'No-Image.jpg') this.src = 'No-Image.jpg'" alt="Hero">
    </div>

    <div>
        <h1 class="{hero.biography.publisher}">{hero.name}</h1>
        <div class="btn-Div">
            <button class="button {display[0]}" on:click={() => swapper(0)}>Stats</button>
            <button class="button {display[1]}" on:click={() => swapper(1)}>Biography</button>
            <button class="button {display[2]}" on:click={() => swapper(2)}>Appearance</button>
            <button class="button {display[3]}" on:click={() => swapper(3)}>More Info</button>
        </div>


        <div class="br"></div>

            {#if display[0] == true}
            <div in:slide class="DisplayInfo">
                <Stats {hero}/>
            </div>
            {/if}

            {#if display[1] == true}
            <div  in:scale class="DisplayInfo">
                <Biography {hero}/>
            </div>
            {/if}

            {#if display[2] == true}
            <div in:scale  class="DisplayInfo">
                <Appearance {hero}/>
            </div>
            {/if}


            {#if display[3] == true}
            <div in:slide  class="DisplayInfo">
                <MoreInfo {hero}/>
            </div>
            {/if}
    </div>


</div>

<style>


    img {
        object-fit: cover;
        height: 80vh;
        width: 50vh;
        max-height: 80vh;
        margin: 2vh auto;
        border-radius: 1vh;
    }

    .mainHeroContainer {
        display: flex;
        margin-top: 5vh;
        height: 80vh;
        flex-wrap: wrap;
        justify-content: center;
        gap: 10vh;
        vertical-align: middle;
    }

    button {
        width: 30vh;
    }

    .btn-Div {
        display: flex;
        align-items: center;
        flex-wrap: wrap;
        justify-content: center;
        gap: 1vh;
    }



    h1 {
        margin-bottom: 1vh;
    }

    .DisplayInfo {
        margin: 1vh 0;
    }

    .true {
        background-color: rgb(254, 72, 72);
    }

    @media screen and (max-width: 600px) {
    button {
    width: 50vh;
    }
}
</style>