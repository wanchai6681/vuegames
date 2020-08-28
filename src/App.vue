<template>
<div id="app" class="container">

    <div class="fullscreen-viedo-wrap ">
        <video src="./assets/bg.mp4" loop autoplay muted></video>
    </div>
    <div class="overlay"></div>

    <div class="row mt-5">
        <div class="col-md-4"></div>
        <div class="col-md-4 content "> <button @click="show = !show" class="btn btn-danger  mb-3 ">Start</button>

            <transition name="fade">
                <div v-if="show " class="content mb-3">
                    <Wan @Imgmonster="imgmonster" @Imghero="imghero" @Heroname="Heroname" @HeroHP="HeroHp" @Monstername="Monstername" @MonsterHP="MonsterHP"></Wan>
                </div>

            </transition>
        </div>

        <div class="col-md-4"></div>
    </div>
       <div class="row d-flex justify-content-center">
        <div class="col-md-4">

        </div>
        <div class="col-md-4 content ">
            <Wbutton @atk="Attack" @SPATK="$SPAttack" @RandomATK="Attackback" @RandomSPATK="SPAttackback"> </Wbutton>

        </div>
        <div class="col-md-4">

        </div>

    </div>

    <div class="row d-flex mb-5">

        <div class=" col-md-5 content">
            <h1>{{heroname}} </h1>
            <div class="d-flex justify-content-center">
                <H5>HP :</H5>
                <b-progress :value="HPHero" :max="HPHeromax" show-value variant="danger" height="25px" class="w-75 md-2  ml-2"></b-progress>
            </div>

        </div>
        <div class="col-md-2 content"></div>
        <div class="col-md-5 content">
            <h1>{{monstername}}</h1>
            <div class="d-flex justify-content-center">
                <H5>HP :</H5>
                <b-progress :value="HPMonster" :max="HPMonstermax" show-value variant="danger" height="25px" class="w-75 md-2 ml-2  "></b-progress>
            </div>
        </div>

    </div>
    <div class="row ">
        <div class="col-md-3"></div>
        <div class="col-md-6 content">
            
           
          

        </div>
        <div class="col-md-3"></div>
    </div>

    <div class="row">
        <div class="col-md-5 content d-flex justify-content-center">
            <p v-if="imgHero" v-bind:style="{width: fsizeH_W + 'px' , height: fsizeH_H + 'px'}"><img :src="imgHero" alt="" class="img-fluid"></p>

        </div>

        <div class="col-md-2 content flex-column">
            
            <div class="p-5">
                <h1>VS</h1>
            </div>

        </div>

        <div class="col-md-5 content d-flex justify-content-center">
            <p v-if="imgMonster"  v-bind:style="{ width: fsizeM_W + 'px' , height: fsizeM_H + 'px'}"><img :src="imgMonster" alt="" class="img-fluid"></p>

        </div>

    </div>

 
  
            <modal v-if="HPHero <= 0 && HPMonster > 0 && heroname != ''"  @$reset="$reset" @reset="reset" @close="showModal = false"  >
                <h3 slot="header">YOU LOUSE</h3>
            </modal>
            <modal v-if="HPMonster <= 0 && HPHero > 0 && heroname != ''"  @$reset="$reset" @reset="reset" @close="showModal = false"  >
                <h3 slot="header">YOU WIN</h3>
            </modal>
            <modal v-if="(HPHero<=0 && HPMonster <= 0 ) && heroname != ''"  v-bind="reset" @$reset="$reset" @reset="reset" @close="showModal = false"  >
                <h3 slot="header">DRAW</h3>
            </modal>

</div>
</template>

<script>
import Wbutton from "./components/Wbutton"
import Wan from "./components/Wan.vue"
import modal from "./components/modal.vue"
import './csstyle.css'

export default {
    name: 'App',
    el: "#App",

    prop: {

    },

    components: {
        Wbutton,
        Wan,
        modal

    },

    data: function () {
        return {
            show: false,
            showModal: false,
            n: 0,
            HPHero: 0,
            heroname: "",
            monstername: "",
            HPMonster: 0,
            atk: 0,
            imgHero: '',
            imgMonster: '',
            HPHeromax: 0,
            max: 0,
            HPMonstermax: 0,
            fsizeM_W: 500,
            fsizeH_W : 500,
            fsizeM_H: 300,
            fsizeH_H : 300


        }

    },
    methods: {

        Heroname(value) {
            this.heroname = value
            console.log("emit", this.heroname)
        },
        HeroHp(value) {
            this.HPHero = value
            this.HPHeromax = value
            this.fsizeH_H = value*2
            this.fsizeH_W = value*2
            console.log("emit", this.HPHero)
        },
        Monstername(value) {
            this.monstername = value
            console.log("emit m", this.monstername)
        },

        MonsterHP(value) {
            this.HPMonster = value
            this.HPMonstermax = value
            this.fsizeM_H = value*2
            this.fsizeM_W = value*2
            console.log("emit mhp", this.HPMonster)
        },
        Attack(value) {
            this.atk = value
            this.fsizeM_W -= value*1.5
            this.fsizeM_H -= value*1.5
            this.HPMonster -= this.atk
        },

        $SPAttack(value) {
            this.atk = value
            this.fsizeM_W -= value
            this.fsizeM_H -= value
            this.HPMonster -= this.atk
        },
        Attackback(value) {
            this.atk = value
            this.fsizeH_W -= value*1.5
            this.fsizeH_H -= value*1.5
            this.HPHero -= this.atk
        },

        SPAttackback(value) {

            this.atk = value
            this.fsizeH_W -= value
            this.fsizeH_H -= value
            this.HPHero -= this.atk
        },

        imghero(value) {
            this.imgHero = value
            console.log(this.imgHero)

        },
        imgmonster(value) {
            this.imgMonster = value
        },

        $reset(value){
            
            this.heroname = value
            this.monstername=value
            this.imgHero = value
            this.imgMonster = value

        },
        reset(value){
            this.HPHero = value
            this.HPMonster = value
            this.fsizeM_W= 300,
            this.fsizeH_W = 300,
            this.fsizeM_H=100,
            this.fsizeH_H = 100
        }

    }

}
</script>

<style>

</style>
