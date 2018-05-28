<template>
  <div id="app" style="text-align: left; padding: 10vw">
    <button @click="addDay">Add day</button>  
    <div>
      <div class="box">
        <DatePicker :startDate="startDate"/>
      </div>   
    </div>    
  </div>
</template>

<script>
import DatePicker from 'components/DatePicker.vue';

export default {
  components: {
    DatePicker
  },

  data() {
    return {
      startDate: new Date(),
      day: 0
    }
  },

  mounted() {  
    console.log(this.startDate.getDate())
    this.day = this.startDate.getDate()
  },

  methods: {  
    addDay() {
      this.day++
      this.startDate = new Date(this.startDate.getFullYear(), this.startDate.getMonth(), this.day, this.startDate.getFullYear(), 0, 0, 0, 0)
    }
  }
};

</script>

<style>
body,
html {
  font-family: 'Source Sans Pro', sans-serif;
}

.box {
  width: 100%;
}
</style>
