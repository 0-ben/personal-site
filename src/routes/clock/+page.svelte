<script lang="ts">
    import { onMount } from "svelte";
    
    onMount(() => {
        let secondHand = document.querySelector('#seconds') as HTMLElement
        let minuteHand = document.querySelector('#minutes') as HTMLElement
        let hourHand = document.querySelector('#hours') as HTMLElement

        const update = () => {
            let d = new Date();
            let hr = d.getHours();
            let min = d.getMinutes();
            let sec = d.getSeconds();
            
            let hr_rotation = (30 * hr + min / 2) - 90
            let min_rotation = (6 * min) - 90;
            let sec_rotation = (6 * sec) - 90;
            
            hourHand.style.transform = `rotate(${hr_rotation}deg)`;
            minuteHand.style.transform = `rotate(${min_rotation}deg)`;
            secondHand.style.transform = `rotate(${sec_rotation}deg)`;
        }
        
        update()
        setInterval(update, 1000)
    })

</script>

<div id="clock"></div>
<div id="seconds" class="hand"></div>
<div id="minutes" class="hand"></div>
<div id="hours" class="hand"></div>
<div id="origin"></div>


<style lang="scss">
    // @import url('./css.css');
    :global(main) {
        margin: 1em auto !important;
        --height: calc(100vh - 4em) !important;
    }
    
    #seconds {
        --col: #F66;
        $width: 20em;
        left: calc(50vw - (#{$width} / 2));
        width: $width;
        height: 1em;
    }

    #minutes {
        --col: #333;
        $width: 40em;
        left: calc(50vw - (#{$width} / 2));
        width: $width;
        height: 1em;
    }
    #hours {
        --col: #333;
        $width: 30em;
        left: calc(50vw - (#{$width} / 2));
        width: $width;
        height: 1em;
    }
    
    
    .hand, #origin, #clock {
        z-index: 5;
        position: absolute;
    }

    .hand {
        top: 50vh;
        background: linear-gradient(to left, var(--col) 50%, transparent 50%);
    }

    #clock {
        $diameter: 80vh;
        top: calc(51vh - (#{$diameter} / 2));
        left: calc(50vw - ($diameter / 2));

        background-color: #DDD;
        border-radius: 50%;
        width: 80vh;
        height: 80vh;

    }

    #origin {
        background-color: red;
        border-radius: 50%;
        width: 3em;
        height: 3em;

        left: calc(50vw - 1.5vw);
        top: 50vh;
    }

</style>