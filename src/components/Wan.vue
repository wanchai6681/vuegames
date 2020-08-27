<template>
<div id="Wan">

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
                    image: 'https://www.google.com/search?q=anakin+skywalker+gif&tbm=isch&ved=2ahUKEwjotbuF3bvrAhWSxXMBHbTmBUEQ2-cCegQIABAA&oq=Anakin+Skywalker+&gs_lcp=CgNpbWcQARgAMgQIIxAnMgIIADICCAAyAggAMgIIADICCAAyAggAMgIIADICCAAyAggAOgQIABBDUILjCVjT6glg2_AJaABwAHgAgAFZiAGxAZIBATKYAQCgAQGqAQtnd3Mtd2l6LWltZ8ABAQ&sclient=img&ei=7NRHX-iPA5KLz7sPtM2XiAQ&bih=758&biw=1440&client=safari#imgrc=lcZcsABPGonSsM&imgdii=knNXxjHqAHv1JM'
                },
                {
                    name: 'Ironman',
                    hp: 500,
                    image: 'https://www.google.com/search?q=Ironman+gif&tbm=isch&ved=2ahUKEwi7y5vT3bvrAhWEBrcAHZfpAYoQ2-cCegQIABAA&oq=Ironman+gif&gs_lcp=CgNpbWcQAzIECAAQQzICCAAyAggAMgIIADICCAAyAggAMgIIADICCAAyAggAMgIIAFDPhQNYz4UDYPeJA2gAcAB4AIABUIgBUJIBATGYAQCgAQGqAQtnd3Mtd2l6LWltZ8ABAQ&sclient=img&ei=j9VHX_vHBoSN3LUPl9OH0Ag&bih=758&biw=1440&client=safari#imgrc=4U4dPnnPHxebqM&imgdii=TjQH9Mdd1Ula1M'
                },
                {
                    name: 'spiderman',
                    hp: 660,
                    image: 'https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/c9be30e5-5d79-4c7e-b734-3ce0a28bb294/d9v33ow-f1b00729-ae43-443c-a5d7-2a5113590301.gif?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOiIsImlzcyI6InVybjphcHA6Iiwib2JqIjpbW3sicGF0aCI6IlwvZlwvYzliZTMwZTUtNWQ3OS00YzdlLWI3MzQtM2NlMGEyOGJiMjk0XC9kOXYzM293LWYxYjAwNzI5LWFlNDMtNDQzYy1hNWQ3LTJhNTExMzU5MDMwMS5naWYifV1dLCJhdWQiOlsidXJuOnNlcnZpY2U6ZmlsZS5kb3dubG9hZCJdfQ.wDP60l2_VRv5FQAYbYJTPzxe9uBgHh0ot6QDvevoQZk'
                },
                {
                    name: 'Payut',
                    hp: 50,
                    image: 'https://www.google.com/search?q=Payut+gif&tbm=isch&ved=2ahUKEwjLrNvr3bvrAhVN43MBHbkGCSoQ2-cCegQIABAA&oq=Payut+gif&gs_lcp=CgNpbWcQA1DDvAJYw7wCYLnDAmgAcAB4AIABSIgBSJIBATGYAQCgAQGqAQtnd3Mtd2l6LWltZ8ABAQ&sclient=img&ei=wtVHX8vDHc3Gz7sPuY2k0AI&bih=758&biw=1440&client=safari#imgrc=jsUGf2vLSNKqoM&imgdii=bf_1AJOUpF-uNM'
                },
            ],

            monster: [
                {
                    name: 'Darth Vader',
                    hp: 800,
                    image: 'https://www.google.com/search?q=Darth+Vader+gif&tbm=isch&ved=2ahUKEwiS9vD_3bvrAhWCT3wKHYLVDU8Q2-cCegQIABAA&oq=Darth+Vader+gif&gs_lcp=CgNpbWcQAzIECCMQJzICCAAyAggAMgIIADICCAAyAggAMgIIADICCAAyAggAMgIIAFD1twFY9bcBYPnAAWgAcAB4AIAB2gGIAdoBkgEDMi0xmAEAoAEBqgELZ3dzLXdpei1pbWfAAQE&sclient=img&ei=7NVHX5LQL4Kf8QOCq7f4BA&bih=758&biw=1440&client=safari#imgrc=qFyL7yVrEG4XtM&imgdii=F8rPL_dHRuBoQM'
                },
                {
                    name: 'Thnos',
                    hp: 990,
                    image: 'https://www.google.com/search?q=Thnos+gif&tbm=isch&ved=2ahUKEwiv07WM3rvrAhVNNrcAHYI7Cs0Q2-cCegQIABAA&oq=Thnos+gif&gs_lcp=CgNpbWcQAzIGCAAQChAYUIjSAli32gJghN0CaABwAHgAgAFIiAGNAZIBATKYAQCgAQGqAQtnd3Mtd2l6LWltZ8ABAQ&sclient=img&ei=B9ZHX--zBM3s3LUPgveo6Aw&bih=758&biw=1440&client=safari#imgrc=yQmhtdzxeVnMFM'
                },
                {
                    name: 'Cell',
                    hp: 434,
                    image: 'https://www.google.com/search?q=Cell%20gif&tbm=isch&tbs=rimg%3ACUr5axB1s22JYQKC-6qK9wVd&client=safari&hl=en-GB&sa=X&ved=0CCcQuIIBahcKEwi4zfyv3rvrAhUAAAAAHQAAAAAQDA&biw=1440&bih=758#imgrc=_IhiuvJhsurfuM'
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
