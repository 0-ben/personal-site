<script lang="ts">
    import '@fontsource/ubuntu';
    import './main.scss'
    import Email from '$lib/components/Email.svelte';

</script>

<div id="notice">
    <h4>If you believe any content of this website to be in violation of any rights you hold, please contact <Email address="admin@benb.my" /></h4>
</div>

<main style="--height: auto;">
    <slot />
</main>

<style lang="scss">
    #notice {
        text-align: center;
        height: max-content;

        background-color: #111111aa;
        padding: 0.5em;

        h4 {
            margin: 0;
        }
    }
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