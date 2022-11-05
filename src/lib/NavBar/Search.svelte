<script>
// @ts-nocheck



    import axios from 'axios'
    import SearchItem from './SearchBar/SearchItem.svelte';
    let searchInput = ''
    $: searchInput, getSearchResults()
    export let result = [];

    async function  getSearchResults() {
        if (searchInput === '') {
            result = []
        }
        if (searchInput.length < 3) {
            return
        }

        try {

        let search = await axios.get(`https://www.superheroapi.com/api.php/105815209009679/search/${searchInput}`)
        result = await search.data.results

        if (result.response == 'error') {
            result = []
        }

        } catch (error) {

        let e = error
        result = []
        }
    }


</script>
<div on:mousedown={() => result = []}>
    <div class="div hover">
        <input type="text" bind:value={searchInput} placeholder="Search a superhero..." />
        <button on:click={() => getSearchResults()} class="material-symbols-outlined">
                search
        </button>


    </div>

    <div class="items">
        {#if result != []}
        {#each result as result}
        <SearchItem on:onHeroSearchClick search={result}/>
        {/each}
        {/if}
    </div>
</div>



<style>
    .div {
        display: flex;
        align-items: center;
        border: solid gray 0.2vh;
        height: 5.8vh;
        width: 42vh;
        overflow: hidden;
        border-radius: 3vh;
        vertical-align: middle;
        justify-content: center;
        margin-top: 2vh;
        text-align: center;
    }

    input {
        height: 6vh;
        width: 35vh;
        border: none;
        outline: none;
        background-color: rgba(0, 0, 0, 0);
        padding-left: 2vh;
        font-size: 2vh;

    }

    button {
        border-radius: 0px;
        outline: none;
        background-color: rgba(0, 0, 0, 0);
        color: gray;
        font-size: 3vh;
    }

    .items {
        z-index: 100;
        position: absolute;
        width: 42vh;
        margin-top: 2vh ;
        min-height: 0vh;
        max-height: 30vh;
        overflow-y: scroll;
        overflow-x: hidden;
    }

</style>