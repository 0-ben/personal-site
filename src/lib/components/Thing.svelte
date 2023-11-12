<script lang="ts">
    export let name = '???';
    export let desc = '???';
    export let link = '/';
</script>

<div class="thing">
    <a href={link} target='_black'>
        <fieldset>
            <legend>
                <h3>{name}</h3>
            </legend>
            <p>
                {desc}
            </p>
        </fieldset>
    </a>
</div>

<style lang="scss">
    .thing {
        width: 10em;
        height: 10em;

        flex: 1 0 26%;

        margin: 0.5em;

        background-color: rgb(43, 56, 87);
        border-radius: 1em;

        a {
            color: inherit;
            text-decoration: none;
            
            fieldset {
                height: 80%;
                width: 80%;
                
                margin: auto auto;
    
                border: 0.2em solid rgb(154, 154, 154);
                border-radius: 0.2em;
    
                p {
                    margin: none
                }
            }
        }

    }
</style>