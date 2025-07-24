<script lang="ts">
    import { onMount } from "svelte";
    
    const oneDayMS = 24 * 60 * 60 * 1000
    const oneHourMS = 60 * 60 * 1000
    const oneMinMS = 60 * 1000

    let remainingDays = '0';
    let remainingHours = '0';
    let remainingMins = '0';
    let remainingSeconds = '0';

    let chosenDay = 25

    onMount(() => {
        
        setInterval(() => {
            const end = new Date((new Date()).getFullYear(), 11, chosenDay)
            
            const now = new Date();
            const distance = Math.abs((now.valueOf() - end.valueOf()));
            
            var days = Math.floor(distance / oneDayMS);
            var hours = Math.floor((distance % oneDayMS) / oneHourMS);
            var minutes = Math.floor((distance % oneHourMS) / oneMinMS);
            var seconds = Math.floor((distance % oneMinMS) / 1000);
            
            remainingDays = days.toString()
            remainingHours = hours.toString()
            remainingMins = minutes.toString()
            remainingSeconds = seconds.toString()
        }, 1000)
    })
    
    
</script>
    
<h2 id="daysLeft" class="num">
    <span class="actualNumber">{remainingDays}</span>
    <br/>days
</h2>
<h2 id="hoursLeft" class="num">
    <span class="actualNumber">{remainingHours}</span>
    <br/>hours
</h2>
<h3 id="minsLeft" class="num">
    <span class="actualNumber">{remainingMins}</span>
    <br/>minutes
</h3>
<h3 id="secondsLeft" class="num">
    <span class="actualNumber">{remainingSeconds}</span>
    <br/>seconds
</h3>

<input class="dayInput" type="number" bind:value={chosenDay}/>

<style lang="scss">
    @import url('https://fonts.googleapis.com/css2?family=Kdam+Thmor+Pro&display=swap');
    
    :global(body) {
        display: flex;
        align-items: center;
        justify-items: center;
        flex-direction: column;
        
        margin: 8px;
        background-image: url("https://c4.wallpaperflare.com/wallpaper/483/164/960/cozy-christmas-tree-decorations-holiday-wallpaper-preview.jpg") !important;
        background-repeat: no-repeat !important;
        background-attachment: fixed !important;
        background-size: cover !important;

        text-align: center;

    }
    :global(main) {
        background: none !important;
        
        width: inherit !important;
        min-width: inherit !important;
        height: inherit !important;

        margin: 1em auto !important;
        padding: 0 !important;

    }
    
    h2.num {
        font-size: 3em;
    }
    h3.num {
        font-size: 2.5em;
    }
    
    .num {
        font-family: 'Kdam Thmor Pro', sans-serif;
        color: white;

        margin: 0.5em;

        .actualNumber {
            background-color: wheat;
            border-radius: 0.2em;
            color: #333;
            
            padding: 0.3em;
        }
    }

    .dayInput {
        position: absolute;
        bottom: 1em;
        left: 1em;
        
        height: 0.5em;
        width: 1em;

        -moz-appearance: textfield;
        appearance: textfield;

        &::-webkit-outer-spin-button,
        &::-webkit-inner-spin-button {
        -webkit-appearance: none;
        margin: 0;
        }
    }
    
</style>