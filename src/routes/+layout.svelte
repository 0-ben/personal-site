<script lang="ts">
    import '@fontsource/ubuntu';
    import './main.scss'

</script>

<main style="--height: auto;">
    <slot />
</main>

<style lang="scss">
    main {
        width: 80vw;
        min-width: 80vw;

        height: var(--height);

        margin: 10em auto;
        padding: 1em;

        background-color: #333333AA;
        border-radius: 1em;
    }
</style>