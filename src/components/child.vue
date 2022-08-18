<template>
   <div>
   <div></div>
        <input
          @click="handleDecrease"
          type="button"
          value="-"
          class="btn button-minus border icon-shape icon-sm lh-0 bg-dark text-light"
          data-field="quantity"
        />
        <input
          id="kfUnitsLeaking"
          type="number"
          step="1"
          v-model="kfData.kf_units_leaking"
          name="quantity"
          @change="handleInputChange($event)"
          class="form-control quantity-field border-0 text-center w-25"
        />
        <input
          @click="handlePlus"
          type="button"
          value="+"
          class="btn button-plus border icon-shape icon-sm lh-0 bg-dark text-light"
          data-field="quantity"
        />
   </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    sendChildData: {
      type: Function,
    }
  },
  data() {
    return {
      kfData: {
        kf_units_leaking: 0,
      },
    }
  },
  methods:{
    handlePlus(){
      this.$set(this.kfData,'kf_units_leaking',this.kfData.kf_units_leaking+1)
      this.sendChildData(this.kfData.kf_units_leaking)
    },
    handleDecrease(){
       this.$set(this.kfData,'kf_units_leaking',this.kfData.kf_units_leaking-1)
        this.sendChildData(this.kfData.kf_units_leaking)
    },
    handleInputChange($event){
      this.$set(this.kfData,'kf_units_leaking',parseInt($event.target.value))
      this.sendChildData(this.kfData.kf_units_leaking)
    }
  }
}
</script>

<style scoped>

</style>