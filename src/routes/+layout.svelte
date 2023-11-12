<script lang="ts">
    import '@fontsource/ubuntu';
    import './main.scss'

</script>

<main>
    <slot />
</main>

<style lang="scss">
    main {
        width: 80vw;
        min-width: 80vw;

        height: calc(100vh - 20em);

        margin: 10em auto;
        padding: 1em;

        background-color: #333333AA;
        border-radius: 1em;
    }
</style>