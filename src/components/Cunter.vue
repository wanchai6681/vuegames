<template>
<div>
  <div id="example-1">
  <button @click="upFunction" class="btn btn-dark">{{lable}}</button>
  <button @click="downFunction" class="btn btn-dark ml-3">-</button>
</div>
</div>
</template>

<script>
export default {
 data: function (){
     return{
    counter: 0,
    fsize:50,
    }
  },
  props: {
    lable: String
  },
  methods: {


  }
}
</script>

<style>

</style>