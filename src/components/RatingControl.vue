
<template>
       <ul>
          <!-- type=button so it doesnt submit the form -->
          <li :class="{active: activeOption === 'poor'}"><button type="button" @click="activate('Poor')">Poor</button></li> 
          <li :class="{active: activeOption === 'average'}"><button  type="button" @click="activate('Average')">Average</button></li>
          <li :class="{active: activeOption === 'great'}"><button  type="button" @click="activate('Great')">Great</button></li>
        </ul>
</template>
<script>
export default {
          data(){
               return {
                    activeOption:this.option
               }     
          },
          methods:{
          activate(option){
                 this.activeOption = option;
                 this.$emit('update:modelValue', option);
          }
          }
}
</script>

<style scoped>
.active{
          border-color:purple;
}
.active button{
    color:red
}
ul{

  list-style:none;
  margin: 0.5rem 0;
  padding:0;
  display: flex;
}
li{
 margin:0 1rem;
 border: 1px solid #ccc;
 padding: 1rem;
 display: flex;
 justify-content: center;
 align-items: center;
}
button{
          font:inherit;
          border: none;
          background-color: transparent;
          cursor: pointer;
}



</style>