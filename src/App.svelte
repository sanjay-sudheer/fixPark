<script context="module">
	var intReading
	var slot1
	var slot2
	var slot3


	export function bill1(){
	  return slot1
	}
	export function bill2(){
	  return slot2
	}
	export function bill3(){
	  return slot3
	}
	export function slot(){
	  return intReading
	}


</script>
<script>

let activetab

import slots from './components/slots.svelte'
import bill from  './components/bill.svelte'
import payment from './components/payment.svelte'

    	
// Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
const firebaseConfig = {
  apiKey: "AIzaSyBP34IUxNk-WQgbhGYu-VZNTICPeezR1LY",
  authDomain: "fixpark-b0e26.firebaseapp.com",
  databaseURL: "https://fixpark-b0e26-default-rtdb.asia-southeast1.firebasedatabase.app",
  projectId: "fixpark-b0e26",
  storageBucket: "fixpark-b0e26.appspot.com",
  messagingSenderId: "4937575055",
  appId: "1:4937575055:web:68c077e0cb8277a1b4defa"
};

// Initialize Firebase
firebase.initializeApp(firebaseConfig);
var database = firebase.database();

var dataIntPath = 'test/int'
var slot1path='slot1/int'
var slot2path='slot2/int'
var slot3path='slot3/int'

// Get a database reference
const databaseInt = database.ref(dataIntPath);
const databaseslot1=database.ref(slot1path)
const databaseslot2=database.ref(slot2path)
const databaseslot3=database.ref(slot3path)

// Variables to save database current values



// Attach an asynchronous callback to read the data

databaseslot1.on('value', (snapshot) => {
  slot1 = snapshot.val();
  console.log(slot1);
}, (errorObject) => {
  console.log('The read failed: ' + errorObject.name);
});

databaseslot2.on('value', (snapshot) => {
  slot2 = snapshot.val();
  console.log(slot2);
}, (errorObject) => {
  console.log('The read failed: ' + errorObject.name);
});

databaseslot3.on('value', (snapshot) => {
  slot3 = snapshot.val();
  console.log(slot3);
}, (errorObject) => {
  console.log('The read failed: ' + errorObject.name);
});

databaseInt.on('value', (snapshot) => {
  intReading = snapshot.val();
  console.log(intReading);
}, (errorObject) => {
  console.log('The read failed: ' + errorObject.name);
});

function senddata(){
    database.ref('/gate').set(
      {
        int : 1
      }
    )

    activetab = payment
}


</script>


<main>
	
	<div class="left-side">
		<h1>fixPark</h1>
		<h2>We help people from being stranded!🚧</h2>
		<button id="parking" on:click={()=>(activetab = slots)}>See Parking Space</button>
		<button id="parking" on:click={()=>(activetab = bill)}>Show Bill</button>
    <button id="parking" on:click={()=>(senddata())}>Pay Bill</button>
	</div>
	<img src="https://images.pexels.com/photos/1004409/pexels-photo-1004409.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" alt="" class="back">
	<svelte:component this={activetab}/>
	
  
	

</main>

<style>
	
	@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;600;700;800;900&display=swap');

.left-side{
    margin-left: 50px;
}
.back {
    position: fixed;
	top: 0px;
    right: -20%;
    height: 100vh;
    width: 100vh;
    object-fit: cover;
    border-radius: 50%;
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
@media (max-width:1000px) {
    .back{
        position: absolute;
        top: -40%;
        right: 10%;
        display: block;
        width: 70vw;
        height: 70vw;


    }
    .left-side{
      justify-content: center;
      align-items: center; 
      text-align: center; 
    }
}
</style>