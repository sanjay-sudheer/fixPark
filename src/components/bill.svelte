<script>
    import App,{bill1} from "../App.svelte";
    import App1,{bill2} from "../App.svelte";
    import App2,{bill3} from "../App.svelte";

    let amount=0

    
    
</script>






<main>
    <h2 class="left-side">Select Slot</h2>
    <button class="left-side" id="parking" on:click={()=>(amount= bill1())}>Slot 1</button>
    <button class="left-side" id="parking" on:click={()=>(amount= bill2())}>Slot 2</button>
    <button class="left-side" id="parking" on:click={()=>(amount= bill3())}>Slot 3</button>

    <h3 class="left-side">Your bill is: ₹ {amount}
    </h3>

</main>


<style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;600;700;800;900&display=swap');

    .left-side{
    margin-left: 50px;
    }

    #parking{
    background: black;
    color: white;
    border: none;
    padding: 20px;
    font-size: 1em;
    margin-right: 20px;
    border-radius: 10px;
}
</style>