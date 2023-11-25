<script lang="ts">
    import { onMount } from "svelte";
    
    const oneDayMS = 24 * 60 * 60 * 1000
    const oneHourMS = 60 * 60 * 1000
    const oneMinMS = 60 * 1000

    onMount(() => {
        const end = new Date((new Date()).getFullYear(), 11, 25)
        const daysLeftElement = document.querySelector('#daysLeft .actualNumber') as HTMLElement
        const hoursLeftElement = document.querySelector('#hoursLeft .actualNumber') as HTMLElement
        const minsLeftElement = document.querySelector('#minsLeft .actualNumber') as HTMLElement
        const secondsLeftElement = document.querySelector('#secondsLeft .actualNumber') as HTMLElement
        
        setInterval(() => {
            const now = new Date();
            const distance = Math.abs((now.valueOf() - end.valueOf()));
            
            var days = Math.floor(distance / oneDayMS);
            var hours = Math.floor((distance % oneDayMS) / oneHourMS);
            var minutes = Math.floor((distance % oneHourMS) / oneMinMS);
            var seconds = Math.floor((distance % oneMinMS) / 1000);
            
            daysLeftElement.innerText = days.toString()
            hoursLeftElement.innerText = hours.toString()
            minsLeftElement.innerText = minutes.toString()
            secondsLeftElement.innerText = seconds.toString()
        }, 1000)
    })
    
    
</script>
    
<h2 id="daysLeft" class="num">
    <span class="actualNumber"></span>
    <br/>days
</h2>
<h2 id="hoursLeft" class="num">
    <span class="actualNumber"></span>
    <br/>hours
</h2>
<h3 id="minsLeft" class="num">
    <span class="actualNumber"></span>
    <br/>minutes
</h3>
<h3 id="secondsLeft" class="num">
    <span class="actualNumber"></span>
    <br/>seconds
</h3>


<style lang="scss">
    @import url('https://fonts.googleapis.com/css2?family=Kdam+Thmor+Pro&display=swap');
    
    :global(body) {
        display: flex;
        align-items: center;
        justify-items: center;

        flex-direction: row;
        
        margin: 0;
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
    
</style>