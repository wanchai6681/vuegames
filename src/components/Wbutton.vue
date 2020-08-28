<template>
<div id="AttackButton">
    <button @click="$attk" class="btn btn-warning mr-3">Attack</button>
    <button @click="$Spattk" class="btn btn-warning">Special Attack</button>
</div>
</template>

<script>
export default {
    el: '#AttackButton',
    data: function () {
        return {
            
        };
    },

    props: {
        lable: String
    },

    methods:{
        randomDamage: function (min, max) {
            
            return Math.max(Math.floor(Math.random() * max) + 1, min)
            
           
        },
        $attk : function (){
            this.atk = this.randomDamage(3,10)
            this.$emit("atk",this.atk)
            console.log("Attack :",this.atk)

            this.atk = this.randomDamage(3,10)
            this.$emit("RandomATK" , this.atk)
            console.log("Atk back",this.atk)
        },

        $Spattk : function (){
            this.spatk = this.randomDamage(10,20)
            this.$emit("SPATK",this.spatk)
            console.log("Special Attack :",this.spatk)

            this.spatk = this.randomDamage(10,20)
            this.$emit("RandomSPATK" , this.spatk)
            console.log("SPATK back",this.spatk)
        },

        
        
        
    }

}
</script>

<style>

</style>
