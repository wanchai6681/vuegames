<template>
<div id="app">
    <div class="row">
        <div class="col-md-4"></div>
        <div class="col-md-4"> <button @click="show = !show">Start</button>

            <transition name="fade">
                <div v-if="show">
                    <Wan  @Imgmonster="imgmonster" @Imghero="imghero" @Heroname="Heroname" @HeroHP="HeroHp" @Monstername="Monstername" @MonsterHP="MonsterHP"></Wan>
                </div>

            </transition>
        </div>

        <div class="col-md-4"></div>
    </div>
    <div class="row">
        <div class="col-md-4">

        </div>
        <div class="col-md-4">
            <Button @atk="Attack" @SPATK="$SPAttack" @RandomATK="Attackback" @RandomSPATK="SPAttackback"> </Button>
        </div>
        <div class="col-md-4">

        </div>
    </div>

    <div class="row">

        <div class="col-md-6">
            <h1>Hero : {{heroname}} | HP : {{HPHero}}</h1>
        </div>

        <div class="col-md-6">
            <h1>Monster : {{monstername}} | HP : {{HPMonster}}</h1>
        </div>

        
    </div>
    <div class="row">
            <div class="col-md-3"></div>
            <div class="col-md-6">
                
                    <p v-if="HPHero <= 0 && HPMonster > 0 && heroname != ''" >You Louse Plaese Restart</p>
                    <p v-if="HPMonster <= 0 && HPHero > 0 && heroname != ''" >You WIN Plaese Restart</p>
                    <p v-if="(HPHero<=0 && HPMonster <= 0 ) && heroname != ''" >Draw Plaese Restart</p>
                
                
            </div>
            <div class="col-md-3"></div>
   
        </div>

    <div class="row">
        <div class="col-md-6">
            <p v-if="imgHero"><img :src="imgHero" alt="" class="img-fluid image"></p>

        </div>

        <div class="col-md-6">
            <p v-if="imgMonster"><img :src="imgMonster" alt="" class="img-fluid image"></p>

        </div>

    </div>
</div>
</template>

<script>
import Button from "./components/Button"
import Wan from "./components/Wan"


export default {
    name: 'App',

    components: {
        Button,
        Wan
       

    },
    data: function () {
        return {
            show: false,
            n: 0,
            HPHero: 0,
            heroname: "",
            monstername: "",
            HPMonster: 0,
            atk: 0,
            imgHero: '',
            imgMonster: ''

        }

    },
    methods: {

        Heroname(value) {
            this.heroname = value
            console.log("emit", this.heroname)
        },
        HeroHp(value) {
            this.HPHero = value
            console.log("emit", this.HPHero)
        },
        Monstername(value) {
            this.monstername = value
            console.log("emit m", this.monstername)
        },

        MonsterHP(value) {
            this.HPMonster = value
            console.log("emit mhp", this.HPMonster)
        },
        Attack(value) {
            this.atk = value
            this.HPMonster -= this.atk
        },

        $SPAttack(value) {
            this.atk = value
            this.HPMonster -= this.atk
        },
        Attackback(value) {
            this.atk = value
            this.HPHero -= this.atk
        },

        SPAttackback(value) {
            this.atk = value
            this.HPHero -= this.atk
        },

        imghero(value) {
            this.imgHero = value
            console.log(this.imgHero)

        },
        imgmonster(value) {
            this.imgMonster = value
        },

    }

}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top:  50px;

}

.fade-enter-active,
.fade-leave-active {
    transition: opacity .5s;
}

.fade-enter,
.fade-leave-to {
    opacity: 0;
}

.image {
    width: 500px;
    height: 400px;
}

</style>
