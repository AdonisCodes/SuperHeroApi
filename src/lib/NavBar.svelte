<script>
    import Logo from "./NavBar/Logo.svelte";
    import Search from "./NavBar/Search.svelte";

    export let val



</script>


    <div>
        <div class="logo">
            <div class="center">
                <Logo />
            </div>

        </div>
        
        <Search result={val} on:onHeroSearchClick/>
    </div>



<style>
    div {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        vertical-align: middle;
        text-align: center;
        align-items: center;
    }

    .logo {
        margin-right: auto;
    }


</style>