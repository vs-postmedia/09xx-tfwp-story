<script>
    // IMPORTS
    import Scrolly from '../helpers/Scrolly.svelte';
    import Steps from '../data/steps.js';

    // PROPS
    export let currentStep;
</script>


<Scrolly bind:value={currentStep}>
    {#each Steps as step, i}
        <li class="step" class:active={currentStep === i}>
            <div class="step-content">{@html step}</div>
        </li>
    {/each}
</Scrolly>


<!-- STYLES -->
<style>
    .step {
        display: flex;
        height: 90vh;
        justify-content: center;
        line-height: 1.25rem;
        opacity: 0.3;
        place-items: center;
        transition: opacity 300ms ease;
    }
    .step:first-of-type {
        top: -50%;
        opacity: 1;
    }
    .step.active {
        opacity: 1;
    }
    .step-content {
        background: rgba(255,255,255,0.85);
        padding: 0.75rem 1rem;
        max-width: 80%;
    }
    /* dunno why but this doesn't work - has to be in main.css  */
    .step-content .scroll-more {
	    display: block;
	    font-family: BentonSansCond-BoldItalic;
	    margin-top: 10px;
        text-align: center;
    }
</style>