<script>
    import App,{bill1} from "../App.svelte";
    import App1,{bill2} from "../App.svelte";
    import App2,{bill3} from "../App.svelte";


</script>

<main>
    <h2 class="left-side">bill for slot1= {bill1()}</h2>
    <h2 class="left-side">bill for slot2= {bill2()}</h2>
    <h2 class="left-side">bill for slot3= {bill3()}</h2>
</main>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;600;700;800;900&display=swap');

    .left-side{
    margin-left: 50px;
    }
</style>