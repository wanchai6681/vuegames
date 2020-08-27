<template>
<div id="Button">
    <Button @click="$attk">battle</Button>
    <Button @click="$Spattk">Attack </Button>
</div>
</template>

<script>
export default {
    el: '#Button',
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
