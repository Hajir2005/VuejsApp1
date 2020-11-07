<template>
    <div>
        <h1>Free Space Loss Calculation</h1>
        <p class='form-inline'>L<sub>dB</sub> = 20log(<input @focus="$event.target.select()" class='form-control form-control-sm' type='text' v-model="f" />) + 20log(<input @focus="$event.target.select()" class='form-control form-control-sm' type='text' v-model="d" />) - 147.56dB</p>
        <p>L<sub>dB</sub> = {{calcLdb()}}dB</p>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                f: `f x 10^9 (GHz)`,
                d: 'd x 10^6 (km)'
            }
        },
        methods: {
            calcLdb: function() {
                if(Number(this.f) && Number(this.d)){
                    return 20 * Math.log10(this.f) + 20 * Math.log10(this.d) - 147.56; 
                }
                return '';

            }
        },
    }
</script>

