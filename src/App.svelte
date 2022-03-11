<script>
    import { Router, Route } from "svelte-routing";
    import Home from "./MainPage.svelte";
    import TnvdPage from "./Tndv-page.svelte";

    export let url = "";
    $: console.log(url)

</script>

<Router url="{url}">

    <div>
        <Route path="/"><Home /></Route>
        <Route path="/tnvd"><TnvdPage /></Route>
    </div>
</Router>