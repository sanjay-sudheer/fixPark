


<script>
    import App,{slot} from "../App.svelte";
</script>

<main>
    <h2 class="left-side">available slots in thrikkakara: {slot()}</h2> 
</main>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;600;700;800;900&display=swap');

    .left-side{
    margin-left: 50px;
    }
</style>