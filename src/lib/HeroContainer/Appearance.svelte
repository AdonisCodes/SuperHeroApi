<script>
    export let hero
    $: heroApnc = hero.appearance
</script>

<div class="div">



        {#if heroApnc.gender == 'Male'}
        <div class="gender DisplayDiv" style="background-color: #09141e ;">
            <h2>Gender</h2>
        <h2 style="font-size:4vh ;" class="material-symbols-outlined">  
            male
        </h2>
        </div>
        {/if}


        {#if heroApnc.gender == 'Female'}
        <div class="gender DisplayDiv" style="background-color: rgb(73, 24, 34);">
            <h2>Gender</h2>
        <h2 style="font-size:4vh ;" class="material-symbols-outlined">   
            female
        </h2>
        </div>
        {/if}

        {#if heroApnc.gender == "null"}
        <div class="gender DisplayDiv" style="background-color: rgb(73, 24, 34);">
            <h2>Gender</h2>
        <h2 style="font-size:4vh ;" class="material-symbols-outlined">   
            transgender
        </h2>
        </div>
        {/if}

        <div class="gender DisplayDiv" >
            <h2>weight</h2>
        <h2 style="font-size:4vh ;" class="material-symbols-outlined">   
           
                <p>{heroApnc.weight[0]} </p>
        </h2>
        </div>

        
        {#if heroApnc.race == 'Human'}
        <div class="gender DisplayDiv">
            <h2>Race</h2>
        <h2 style="font-size:4vh ;" class="material-symbols-outlined">   
            man
        </h2>
        </div>
        {/if}

        {#if  heroApnc.race == "null" }
        <div class="gender DisplayDiv" style="background-color: rgb(117, 68, 52);">
            <h2>Race</h2>
        <h2 style="font-size:4vh ;" class="material-symbols-outlined">   
            question_mark
        </h2>
        </div>
        {:else}
        <div class="gender DisplayDiv" style="background-color: rgb(117, 68, 52);">
            <h2>Race</h2>
        <h2 style="font-size:4vh ;" class="material-symbols-outlined">   
            no_accounts
        </h2>
        </div>
        {/if}



        <div class="gender DisplayDiv" >
        <h2 style="font-size:5vh ;" class="material-symbols-outlined">  
            visibility 
        </h2>

        <h2 style="color:{heroApnc['eye-color']} ;">
            {heroApnc['eye-color']}
        </h2>
        </div>

        <div class="gender DisplayDiv" style="background-color: rgb(38, 71, 20);">
            <h2>Height</h2>
        <h2 style="font-size:4vh ;" class="material-symbols-outlined">   
           
                <p>{heroApnc.height[0]} ft</p>
        </h2>
        </div>


        <div class="gender DisplayDiv" >
            <h2>Hair</h2>
        <h2 style="color:{heroApnc["hair-color"]};">   
           
               {heroApnc["hair-color"]}
        </h2>
        </div>
</div>


<style>
    .div {
        display: grid;
        align-items: center;
        margin-top: 1.5vh;
        border-radius: 1vh;

        vertical-align: middle;
        margin: 0 auto;
    }

    .DisplayDiv {
        display: grid;
        grid-template-columns: 11fr 0.5fr;
        align-items: center;
        column-gap: 1vh;
        box-shadow: rgba(20, 20, 20, 0.1) 0px 1.5px 3px, rgba(85, 85, 85, 0.15) 0px 1.5px 3px;
        padding: 1.5vh 2vh;
        justify-content: center;
        border-radius: 1vh;
        margin-top: 2.2vh;
        background-color: rgb(10, 10, 10);
    }


    h2 {
        font-size: 2.7vh;
        margin: 0 0;
        display: inline-block;
    }

    p {
        margin: 1vh 0 ;
        display: inline-block;
        font-size: 1.6vh;
        display: flex;
    }
</style>