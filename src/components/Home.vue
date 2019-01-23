<template>
    <div>
        <h1>{{ msg }}</h1>
        <div class="formulaire">
            <div>
                <tr class="Clesvalues">
                    <td><input type="text" placeholder="Value 1" v-model="v1"/></td>
                    <td><input type="text" placeholder="Value 2" v-model="v2"/></td>
                    <td><input type="text" placeholder="Value 3" v-model="v3"/></td>
                    <td><input type="submit" name="Valider" v-on:click="sol = solve(v1, v2, v3)"/></td>
                </tr>
            </div>
            <div>
                <tr>
                    <p>For {{ v1 }} + {{ v2 }} = {{ v3 }}</p>
                </tr>
            </div>
        </div>
        <div class="formulaire">
            <tr>
                <p>Solution : {{ sol }}</p>
            </tr>
        </div>
    </div>
</template>

<script>
    import {res} from './Solveur.js';

    export default {
        data: function () {
            return {
                v1: '',
                v2: '',
                v3: '',
                sol: '',
            }
        },
        name: "Home.vue",
        props: {
            msg: String
        },
        methods: {
            solve : function (v1, v2, v3){
                let message = JSON.parse(JSON.stringify(res(v1, v2, v3)));
                let finalRes = "";
                for(var toto in message.values){
                    finalRes += " key = " + toto + " values = " + message.values[toto].value;
                }
                return finalRes;
            }
        }
    }
</script>

<style scoped>
.formulaire {
    display: flex;
    justify-content: space-around;
}

.Clesvalues{
    display: flex;
    flex-direction: column;
}

.for{
    border-style: solid;
}
</style>