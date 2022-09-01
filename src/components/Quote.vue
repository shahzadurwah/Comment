<template>
  <div class="row justify-content-center mt-3 mb-3">
      <div class="col-sm-12 col-md-6 ">
          <form>
              <textarea v-model="quote"></textarea><br>
              <button class="btn btn-primary" @click.prevent="addNew">Add New</button>
          </form>
      </div>
  </div>
</template>

<script>
export default {
    name:'Quote',
    data(){
        return{
            quote:''
        }
    },
    methods:{
        addNew(){
            this.$emit('addNewquote', this.quote)
            this.quote=""
        }
    }

}
</script>

<style>
    textarea{
        width: 100%;
        padding: 20px 10px;
        border: 1px solid gray;
    }
    textarea:focus{
        outline: none;
        border-color: blue;
    }
    button{
        width: 100px;
    }
</style>