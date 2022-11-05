<script>
    export let hero
    $: heroBio = hero.biography
</script>

<div style="background-color: rgba(0, 0, 0, 0);">
    <div>
        <h2>Full-name:</h2>
        <p>{heroBio['full-name']}</p>
    </div>

    <div>
        <h2>Alter-egos:</h2>
        <p>{heroBio["alter-egos"]}</p>
    </div>

    <div>
        <h2>Aliases:</h2>
        {#each heroBio.aliases as alias}
            <p> <span class="{heroBio.publisher}"> - </span>{alias}</p>
        {/each}
    </div>

    <div>
        <h2>Place-of-birth:</h2>
        <p># {heroBio["place-of-birth"]}</p>
    </div>

    <div>
        <h2>Publisher:</h2>
        <p># {heroBio.publisher}</p>
    </div>
</div>

<style> 
    h2 {
        font-size: 3.7vh;
        margin: 0.5vh 1vh;
        color: rgb(50, 50, 50);

    }

    p {

        margin: 0.2vh 0 ;
        font-size: 2.5vh;
        margin-left: 3vh ;

    }

    span {
        font-size: 3vh;
        text-align: center;
        margin-right: 1vh;
    }

    div {
        display: grid;
        grid-template-rows: auto;
        background-color: rgb(10, 10, 10);
        border-radius: 1vh;
        margin-top: 2vh;
        box-shadow: rgba(20, 20, 20, 0.1) 0px 1.5px 3px, rgba(85, 85, 85, 0.15) 0px 1.5px 3px;
        align-items: center;
        min-width: 50vh;
        max-width: 120vh;
        padding: 1vh 0;

    }
</style>