<template>
    <transition name="modal" >
        <div class="modal-mask content">
          <div class="modal-wrapper">
            <div class="modal-container">
              <div class="modal-header">
                <slot name="header">
                  
                </slot>
              </div>

              <div class="modal-body">
                <slot name="body">
                  Please Start
                </slot>
              </div>
              <div class="modal-footer">
                <slot name="footer">
                  <button class="modal-default-button btn-danger" @click="$emit('close',false),$emit('reset',0),$emit('$reset','')">
                    OK
                  </button>
                </slot>
              </div>
            </div>
          </div>
        </div>
      </transition>
</template>

<script>


export default {
    name:"modal",

    props:{
        lable: String
    },
        data: function() {
return {
          showModal: false
          
        };
}
      

}
</script>

<style>


</style>