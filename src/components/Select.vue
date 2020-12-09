<template>
  <div class="select-wrap">
    <div class="select"
         @click="showOptions = !showOptions, isSelected = !isSelected"
         :class="{'active': isSelected}">
      {{value ? value : 'Выберите пол'}}
      <span></span>
    </div>
    <div class="option"
         v-show="showOptions"
         v-for="(val, key) in selectOption"
         :key="key"
         :label="val"
         @click="selected(val)"
    >{{ val }}</div>
  </div>
</template>

<script>
export default {
  name: "Select.vue",
  props: {
    selectOption: {
      type: Object
    },
    select: {
      default: false
    },
    value: {
      default: false
    }
  },
  data(){
    return {
      showOptions: false,
      isSelected: false
    }
  },
  methods: {
    selected(newVal) {
      this.showOptions = !this.showOptions
      this.isSelected = !this.isSelected
      this.$emit('update:value', newVal )
    }
  }
}
</script>

<style>
  .select-wrap{
    width: 300px;
    text-align: center;
  }
  .option, .select{
    padding: 10px 20px;
  }
  .select{
    position: relative;
    border: 1px solid #ccc;
  }
  .select.active span{
    transform: rotate(45deg);
  }
  span{
    position: absolute;
    right: 10%;
    display: inline-block;
    width: 10px;
    height: 10px;
    border-top: 1px solid;
    border-left: 1px solid;
    transform: rotate(225deg);
  }
  .option{
    background-color: #ececec;
    border: 1px solid #ccc;
    border-top: none;
  }
</style>