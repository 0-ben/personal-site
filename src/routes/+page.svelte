<script lang="ts">
    import Thing from '$lib/components/Thing.svelte'
</script>

<div id="title">
    <h1>Ben</h1>
    <h3>I program things, sometimes.</h3> 
</div>

<div id="things">
    <h4>Things I've made I want to share: </h4>

    <div id="things-container">
        <Thing 
            name="Clock"
            desc="Basic clock that I made in ~30 minutes."
            link="/clock"
        />
        <Thing 
            name="Christmas Countdown"
            desc="Basic countdown to the next Christmas"
            link="/christmas_countdown"
        />
        <!-- redacted due to suspicion causing blocks -->
        <!-- <Thing 
            name="vsware.js"
            desc="A TS/JS wrapper for the user-facing VSWare API."
            link="https://github.com/0-ben/vsware.js"
        /> -->
        <Thing 
            name="picopassword"    
            desc="A basic CircuitPython program to enter a string on a button press."
            link="https://github.com/0-ben/picopassword"
        />
        <Thing />
        <Thing 
            name="... and more!"
            desc="View more projects on my Github"
            link="https://github.com/0-ben?tab=repositories"
        />
    </div>
</div>

<style lang="scss">
    #title, #things {
        text-align: center;
        
        height: min-content;
    }

    #title {
        display: grid;
        place-items: center;

        h1, h3 {
            margin: 0.5em 0;
        }

        background-color: rgba(195, 72, 243, 0.212);
        border-radius: 1em;
    }

    #things {
        background-color: rgba(88, 88, 88, 0.212);
        border-radius: 1em;
        
        padding: 0.5em;
        margin-top: 2em;
        
        #things-container {
            display: flex;
            flex-direction: row;
            flex-wrap: wrap;

            justify-content: center;
        }

    }
</style>
