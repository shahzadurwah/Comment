
<template>
  <div class="row m-5">
    <div class="col-sm-6 col-md-4 " v-for="(d, index) in quotes" :key="d" @click="deleteQuote(index)">
      <div class="panel panel-default">
        <div class="panel-body quotes">
          {{ d }}
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "QuoteAdd",
  
    props:['quotes'],
    methods:{
        deleteQuote(index){
            this.$emit('deletequote',index)
        }
    }

};
</script>

<style>
.panel-body{
    font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
    font-size: 24px;
    color: #6e6e6e;
}
.quotes{
    cursor: pointer;
}
.quotes:hover{
    background-color: #ffe2e2;
}
</style>