<template>
  <div>
    <h1>Ticket Details</h1>
    <div class="ticket">
      <h3>Ticket ID:</h3>
      <span>{{ticketDetails.ticketId}}</span>
      <h3>Ticket source:</h3>
      {{ticketDetails.source}}
      <h3>Image URL:</h3>
      {{ticketDetails.postImageUrl}}
      <h3>Video URL:</h3>
      {{ticketDetails.postVideoUrl}}
      <h3>Post Description:</h3>
      {{ticketDetails.postDesc}}
      <h3>Count of Dislikes:</h3>
      {{ticketDetails.countOfDislike}}
      <h3>Comments:</h3>
      <br/>
      <textarea rows="10" cols="30"></textarea>
      <br />
      <uploadimage></uploadimage>
      <button @click="(router.push )">Close</button>
    </div>
    <navbar></navbar>
  </div>
</template>

<script>
import navbar from "../components/navbar.vue";
import uploadimage from "../components/image.vue";
import { mapGetters } from "vuex";
export default {
  name: "ticketdetails",
  components: {
    navbar,
    uploadimage
  },
  created() {
    this.$store.dispatch("details");
  },
  computed: {
    ...mapGetters(["results"]),
    ticketDetails() {
        return this.results;
    }
  }
};
</script>

<style scoped>
.ticket {
  border: 1px solid black;
  border-radius: 20px;
  box-shadow: 10px 10px 10px 10px;
  padding: 50px;
  margin-left: 25%;
  margin-right: 25%;
  margin-top: 2%;
  background-color: rgb(233, 233, 247);

}
h1 {
  text-align: center;
}

</style>