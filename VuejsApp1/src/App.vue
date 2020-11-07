<template>
    <div id="app">
        <div style="display:flex; margin:20px">
            <div style="margin-right:60px">
            <CCC  />
            </div>
            <div>
                <FSLC />
            </div>


        </div>
        
    </div>
</template>

<script>
    import CCC from './components/CCC.vue';
    import FSLC from './components/FSLC.vue'
    export default {
        name: 'app',
        components: {
            CCC, FSLC
        }
    };
</script>

<style>
</style>

