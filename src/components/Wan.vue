<template>
<div id="Select">

    <button @click="random">
        random
    </button>

</div>
</template>

<script>
export default {
    data: function () {
        return {
            player: [{
                    name: 'Anakin Skywalker',
                    hp: 800,
                    image: 'img/bc3c5f18fda1171262442a752f8693dd.gif'
                },
                {
                    name: 'Ironman',
                    hp: 500,
                    image: 'img/tenor.gif'
                },
                {
                    name: 'spiderman',
                    hp: 660,
                    image: 'https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/c9be30e5-5d79-4c7e-b734-3ce0a28bb294/d9v33ow-f1b00729-ae43-443c-a5d7-2a5113590301.gif?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOiIsImlzcyI6InVybjphcHA6Iiwib2JqIjpbW3sicGF0aCI6IlwvZlwvYzliZTMwZTUtNWQ3OS00YzdlLWI3MzQtM2NlMGEyOGJiMjk0XC9kOXYzM293LWYxYjAwNzI5LWFlNDMtNDQzYy1hNWQ3LTJhNTExMzU5MDMwMS5naWYifV1dLCJhdWQiOlsidXJuOnNlcnZpY2U6ZmlsZS5kb3dubG9hZCJdfQ.wDP60l2_VRv5FQAYbYJTPzxe9uBgHh0ot6QDvevoQZk'
                },
                {
                    name: 'Payut',
                    hp: 50,
                    image: 'img/tenors.gif'
                },
            ],

            monster: [
                {
                    name: 'Darth Vader',
                    hp: 800,
                    image: 'img/bc3c5f18fda1171262442a752f8693dd.gif'
                },
                {
                    name: 'Thnos',
                    hp: 990,
                    image: 'img/original.gif'
                },
                {
                    name: 'Cell',
                    hp: 434,
                    image: 'img/7d3.gif'
                }
            ]
        }
    },
    methods: {
        pickName: function (n) {

            console.log("name :", this.player[n].name)
        },

        randomHero: function (min, max) {

            return Math.max(Math.floor(Math.random() * max) + 1, min)

        },

        random: function () {
            this.nH = this.randomHero(0, 3)
            this.nM = this.randomHero(0, 6)
            this.name_hero = this.player[this.nH].name //สุ่ม hero เก็บในตัวแปร ชื่อ
            this.hp_hero = this.player[this.nH].hp //สุ่ม hero เก็บในตัวแปร hp

            this.name_monster = this.monster[this.nM].name //สุ่ม moster เก็บในตัวแปร ชื่อ
            this.hp_monster = this.monster[this.nM].hp

            this.$emit("Heroname", this.name_hero)
            this.$emit("HeroHP", this.hp_hero)

            this.$emit("Monstername", this.name_monster)
            this.$emit("MonsterHP", this.hp_monster)

            console.log("name :", this.name_hero)
            console.log("hp :", this.hp_hero)

            console.log("name :", this.name_monster)
            console.log("hp :", this.hp_monster)

            this.imghero = this.player[this.nH].image
            this.imgmonster = this.monster[this.nM].image
            
            this.$emit("Imghero",this.imghero)
            this.$emit("Imgmonster",this.imgmonster)
          
        }
    },

}
</script>

<style>

</style>
