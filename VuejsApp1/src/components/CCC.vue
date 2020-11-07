<template>
    <div >
        <h1>Channel Capacity Calculator</h1>
        <p>S = Blog<sub>2</sub>(1 + SNR)</p>
        <p>SNR<sub>dB</sub>=10log<sub>10</sub>SNR</p>

        <p class='form-inline'>SNR<sub>dB</sub> = <input class='form-control form-control-sm' type='text' v-model="SNR" /></p>
        <p>10log<sub>10</sub>SNR = {{SNR}}</p>
        <p>log<sub>10</sub>SNR = {{SNR}} / 10</p>
        <p> = {{Math.round((SNR / 10) * 100) / 100}}</p>
        <p><u>SNR = {{SNRRes}}</u></p><br/>
        <p class='form-inline'>B = <input class='form-control form-control-sm' type='text' v-model="B" /></p>
        <p>C = B log<sub>2</sub> (1 + SNR)</p>
        <p> = {{B}} x 10<sup>6</sup>log<sub>2</sub> (1 + {{SNRRes}})</p>
        <p>log<sub>2</sub>({{SNRandOne}}) = log({{SNRandOne}})/ log<sub>2</sub> = {{this.round(Math.log10(SNRandOne) ,2)}}/{{this.round(Math.log10(2) ,4)}} = {{SecondRes}}</p>
        <p>C = {{B}} x 10<sup>6</sup> * {{SecondRes}}</p>
        <p> = {{B*Math.pow(10,6) * SecondRes / Math.pow(10,6)}} Mbps</p>

        <p>M = ?</p>
        <p>C = 2Blog<sub>2</sub>M</p>
        <p class='form-inline'>C = <input class='form-control form-control-sm' v-model='C'/></p>
        <p>{{C}} x 10<sup>6</sup> = {{B}} * 2 * 10<sup>6</sup>log<sub>2</sub>M</p>
        <p>log<sub>2</sub>M = {{C}} x 10<sup>6</sup> / {{B * 2}} x 10<sup>6</sup> = {{round(log2M,2)}} </p>
        <p>logM = {{log2M}} x log2 = {{logM}}</p>
        <p>M = 10<sup>{{logM}}</sup> = {{round(Math.pow(10,logM),4)}}</p>
        <p> = {{round(Math.pow(10,logM),2)}}</p>


        
    </div>
</template>

<script>
    export default {
        name: 'CCC',
       
        data() {
            return {
                SNR: 35,
                B:0,
                C:0
            }
        },
        computed: {
            SNRRes() {
                return this.round(Math.pow(10, this.round((this.SNR / 10) ,2)) ,2);
            },
            SNRandOne() {
                return this.round(this.SNRRes + 1,2);
            },
            SecondRes(){                
                return this.round((Math.log2(this.SNRandOne)) ,4);
            },
            log2M(){
                return (this.C * Math.pow(10,6)) / (this.B*2* Math.pow(10,6))
            },
            logM(){
                return this.round(this.log2M * Math.log10(2),4);
            }
            
        },
        methods: {
            round(number,decimals) {                
                return Math.round(number * Math.pow(10,decimals))/ Math.pow(10,decimals);
            }
        },
    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>

