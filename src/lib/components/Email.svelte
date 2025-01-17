<script lang="ts">
    export let address = ''
</script>

<a href={`mailto:${address}`}>{address}</a>

<style lang="scss">
    a {
        color: greenyellow;

        &:hover, &:active {
            color: rgb(124, 185, 32);
        }
    }
</style>