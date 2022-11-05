<script>
// @ts-nocheck
import { fade, blur, fly, slide, scale } from "svelte/transition";

    export let search;
    import { createEventDispatcher } from 'svelte'
    let EventDispatcher = createEventDispatcher()
    function handleHeroSwap() {
        EventDispatcher('onHeroSearchClick', search)

    }
</script>

<div in:slide out:slide class="hover" on:mousedown={() => handleHeroSwap()}>
    <div>
        <!-- svelte-ignore a11y-missing-attribute -->
        <img src="{search.image.url}" onerror="if (this.src != 'No-Image.jpg') this.src = 'No-Image.jpg'">
            <h2 class="{search.biography.publisher}">{search.name}</h2>
    </div>
</div>


<style>
    div {
        display: grid;
        grid-template-columns: 2fr 5fr;
        margin-top: 0.5vh;
        color: white;
        background-color: rgba(20, 20, 20, 0.4);
        width: 39vh;
        align-items: center;
        
    }

    img {
        height: 15vh;
        width: 10vh;
        object-fit: contain;
    }

    h2 {
        text-align: left;
        margin-left: 2vh;
        font-size: 3vh;
    }

    

</style>