<script>
    export let hero;
</script>

<div class="container">
    <div class="div">
        <div class="statdiv">
            <span class="material-symbols-outlined {hero.biography.publisher} ">grade</span>
            <h1>Intelligence</h1>
        </div>
        <div class="{hero.biography.publisher}1">
            <h2 >{hero.powerstats.intelligence}</h2>
        </div>
    </div>

    <div class="div">
        <div class="statdiv">
            <span class="material-symbols-outlined {hero.biography.publisher} ">grade</span>
            <h1>Strength</h1>
        </div>
        <div class="{hero.biography.publisher}1">
            <h2 >{hero.powerstats.strength}</h2>
        </div>
    </div>

    <div class="div">
        <div class="statdiv">
            <span class="material-symbols-outlined {hero.biography.publisher} ">grade</span>
            <h1>Speed</h1>
        </div>
        <div class="{hero.biography.publisher}1">
            <h2 >{hero.powerstats.speed}</h2>
        </div>
    </div>

    <div class="div">
        <div class="statdiv">
            <span class="material-symbols-outlined {hero.biography.publisher} ">grade</span>
            <h1>Combat</h1>
        </div>
        <div class="{hero.biography.publisher}1">
            <h2 >{hero.powerstats.combat}</h2>
        </div>
    </div>

    <div class="div">
        <div class="statdiv">
            <span class="material-symbols-outlined {hero.biography.publisher} ">grade</span>
            <h1>Durability</h1>
        </div>
        <div class="{hero.biography.publisher}1">
            <h2 >{hero.powerstats.durability}</h2>
        </div>
    </div>
    
    <div class="div">
        <div class="statdiv">
            <span class="material-symbols-outlined {hero.biography.publisher} ">grade</span>
            <h1>Power</h1>
        </div>
        <div class="{hero.biography.publisher}1">
            <h2 >{hero.powerstats.power}</h2>
        </div>
    </div>
    
</div>

<style>
    * {
        margin: 0 0 ;
    }
    .container {
        display: grid;
        grid-template-rows: repeat(5 , 1fr);
        background-color: rgba(0, 0, 0, 0);

    }

    h1 {
        font-size: 5vh;
    }

    .div {
        display: grid;
        grid-template-columns: 11fr 0.5fr;
        align-items: center;
        margin-top: 3.2vh;
        background-color: rgb(10, 10, 10);
        padding: 1vh 1vh;
        border-radius: 1vh;
        box-shadow: rgba(20, 20, 20, 0.1) 0px 1.5px 3px, rgba(85, 85, 85, 0.15) 0px 1.5px 3px;
    }
    .statdiv {
        display: grid;
        grid-template-columns: 0.5fr 11fr;
        align-items: center;
        column-gap: 1vh;
    }

    div {
        height: fit-content;
    }
</style>
