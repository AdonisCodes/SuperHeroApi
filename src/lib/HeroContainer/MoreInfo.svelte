<script>
    export let hero;
    $: heroMore = hero
</script>

<div class="div">
    <div class="containerDiv">
        <h2>
            <span class="material-symbols-outlined {hero.biography.publisher} ">grade</span>
            <span class="span">Work:</span> {heroMore.work.occupation}</h2>
        <p><span class="span" style="margin-right:1vh ;">Locations:</span> {heroMore.work.base}</p>
    </div>
</div>

<div class="div">
    <div class="containerDiv">
        <h2>
            <span class="material-symbols-outlined {hero.biography.publisher} ">grade</span>
            <span class="span">Teams:</span> 
        </h2>
        <p >{heroMore.connections["group-affiliation"]}</p>
    </div>
</div> 

<div class="div">
    <div class="containerDiv">
        <h2>
            <span class="material-symbols-outlined {hero.biography.publisher} ">grade</span>
            <span class="span">Family:</span> 
        </h2>
        <p>{heroMore.connections.relatives}</p>


    </div>
</div>


<style>
    .div {
        display: grid;
        grid-template-rows: auto;
    }

    .span {
        color: rgb(45, 45, 45);
        margin: 0 0;
    }

    h2 {
        margin: 0vh 0;
        margin-top: 2vh;
    }

    .containerDiv {
        margin-top: 2.5vh;
        background-color: rgb(10, 10, 10);
        padding: 0vh 2vh;
        display: grid;
        align-items: center;
        border-radius: 1vh;
        box-shadow: rgba(20, 20, 20, 0.1) 0px 1.5px 3px, rgba(85, 85, 85, 0.15) 0px 1.5px 3px;
    }

    p {
        max-width: 80ch;
        margin-left: 5vh;
    }
</style>