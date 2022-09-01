<template>
  <div class="container-fluid">
    <Header :maxquotes="maxquotes" :quotelength="quotes.length"></Header>
    <Quote @addNewquote="NewQuote"></Quote>
    <QuoteAdd :quotes="quotes" @deletequote="deletequote"></QuoteAdd>
    <div class="row m-5">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Info: Click on a quote to delete it
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Swal from "sweetalert2";
import "sweetalert2/dist/sweetalert2.min.css";
import Quote from "./components/Quote.vue";
import QuoteAdd from "./components/QuoteAdd.vue";
import Header from "./components/Header.vue";
export default {
  data() {
    return {
      quotes: ["hello", "hello 2"],
      maxquotes:10
    };
  },
  methods: {
    NewQuote(data) {
      if(this.quotes.length>=10){
        alert("You Reach Max Quote !Pleae Delete Quote")
        return;
      }
      if(data =="" || data ==null){
        alert("Pleae Write Something");
        return;
      }
      this.quotes.push(data);
    },
    deletequote(index) {
      Swal.fire({
        title: "Are you sure?",
        text: "You won't be able to revert this!",
        icon: "warning",
        showCancelButton: true,
        confirmButtonColor: "#3085d6",
        cancelButtonColor: "#d33",
        confirmButtonText: "delete it!",
      }).then((result) => {
        if (result.isConfirmed) {
          this.quotes.splice(index, 1);
          Swal.fire("Deleted!", "Your file has been deleted.", "success");
        }
      });
      
    },
  },
  components: {
    Quote,
    QuoteAdd,
    Header
  },
};
</script>

<style>
body{
  background: linear-gradient(rgb(210, 210, 210),rgb(253, 252, 252));
}
   .swal2-popup {
   /* width:850px; */
   font-size:1.4rem !important;
  font-family: Georgia, serif;
}
</style>