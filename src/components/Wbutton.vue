<template>
  <div>
    <button @click="reloadPage()" class="btn btn-dark">Start</button>
    <div class="row">
        <div class="col-5">
          <img style="width:50%" :src="selectedplayer.img"  alt="">
        </div>
        <div class="col-2">
          <div class="row">
            <img style="width:20%" :src="versus"  alt="">
          </div>
        </div>
        <div class="col-5">
          <img style="width:5 0%" :src="selectedmonster"  alt="">
    </div>
    </div>
    <div class="row">
      <div class="col-6" >
        Player : {{selectedplayer.name}}
        <br>
         <img  v-bind:style="{width: php + 'px'}"  :src="phpbar"  alt="" height="15px">
         {{php}}
      </div>
      <div class="col-6">
        Monster
        <br>
        <img  v-bind:style="{width: mhp + 'px'}"  :src="mhpbar"  alt="" height="15px">
        {{mhp}}
      </div>
    </div>
    <br/>
    <br/>
    <button @click="random()" v-bind:disabled="end"  class="btn btn-dark" >Attack</button>{{space}}
    <button @click="SPrandom()" v-bind:disabled="end" class="btn btn-dark" >SPAttack</button>
    <div id="result">
      <div v-if="mhp==0 || php==0">
        <div v-if="mhp < php">       
        Player win
    </div>
    <div v-else-if="php < mhp">
        Monster win
    </div>
    <div v-else-if="mhp==php">
        Draw
    </div>
      </div>
    </div>
    
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      end : false,
      space : "",
      phpbar : 'https://i.imgur.com/Q5xIoUa.png',
      mhpbar : 'https://i.imgur.com/Q5xIoUa.png',
      versus : 'https://media0.giphy.com/media/l4pTkNEd2P4MWo9iw/source.gif',
         monster : [
            'https://data.whicdn.com/images/326805782/original.gif',
            'https://thumbs.gfycat.com/BruisedGrimyGalago-size_restricted.gif',
            'https://i.makeagif.com/media/10-28-2015/C03MEO.gif',
            'https://www.khaosodenglish.com/wp-content/uploads/2017/04/ten-punch-man.gif',
        ],
        player : [
          {name : "",img :'https://media0.giphy.com/media/Mir5fnHxvXrTa/giphy.gif'},
            {name : "",img : 'https://i.pinimg.com/originals/be/17/d2/be17d2237e14cdd73caa8cf1d7e54d09.gif'},
            {name : "",img : 'https://media3.giphy.com/media/TkDVr6D3OgqEqcLIYP/giphy.gif'},
            {name : "",img : 'https://media3.giphy.com/media/TkDVr6D3OgqEqcLIYP/giphy.gif'},
        ],
        selectedmonster: {name:"",img:null},
        selectedplayer : {name:"",img:null},
      ppower: "",
      mpower: "",
      php: 250,
      mhp: 150,
      term: false,
        
    };
  },
  methods: {
    reloadPage : function(){
    window.location.reload()
  },
    random: function () {
      this.ppower = Math.floor(Math.random() * 7 + 3);
      this.mhp = this.mhp - this.ppower;
      if(this.php<=0){
        this.php = 0
        this.end = true
      }else if(this.mhp<=0){
        this.mhp = 0
        this.end = true
      }else if(this.mhp<=0&&this.php<=0){
        this.mhp = 0
        this.php = 0
      }
      this.mpower = Math.floor(Math.random() * 7 + 3);
      this.php = this.php - this.mpower;
      if(this.php<=0){
        this.php = 0
        this.end = true
      }else if(this.mhp<=0){
        this.mhp = 0
        this.end = true
      }else if(this.mhp<=0&&this.php<=0){
        this.mhp = 0
        this.php = 0
      }
    },
    SPrandom: function () {
      this.ppower = Math.floor(Math.random() * 10 + 5);
      this.mhp = this.mhp - this.ppower;
      if(this.php<=0){
        this.php = 0
        this.end = true
      }else if(this.mhp<=0){
        this.mhp = 0
        this.end = true
      }else if(this.mhp<=0&&this.php<=0){
        this.mhp = 0
        this.php = 0
      }
      this.mpower = Math.floor(Math.random() * 10 + 5);
      this.php = this.php - this.mpower;
      if(this.php<=0){
        this.php = 0
        this.end = true
      }else if(this.mhp<=0){
        this.mhp = 0
        this.end = true
      }else if(this.mhp<=0&&this.php<=0){
        this.mhp = 0
        this.php = 0
      }
    },
    randommonster (items) {
      return items[Math.floor(Math.random()*items.length)];
    },
    randomplayer (items) {
      return items[Math.floor(Math.random()*items.length)];
    },
  },
  created() {
    this.selectedmonster = this.randommonster(this.monster)
    this.selectedplayer = this.randomplayer(this.player)
  },
  
};
</script>

<style>
#result{
  height : 50px;
  font-size : 200%;
  color :aliceblue;
}
</style>