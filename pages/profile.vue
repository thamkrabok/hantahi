<template>
  <div>
    <div class="side-bar">
      <v-btn
        depressed
        router
        :to="`/home`"
        class="mb-5"
      >
        <v-icon class="mr-3">mdi-arrow-left</v-icon>BACK
      </v-btn>
    </div>
    <p class="font-weight-bold">Profile</p>
    <!-- Detail -->
    <div class="d-flex flex-column" style="margin-top: 30px;">
      <!-- Loop Personal Detail -->
      <div v-for="item in showDetails" :key="item.name">
        <!-- name -->
        <p class="font-weight-bold">{{ item.name }}</p>
        <!-- value -->
        <p class="flex-grow-1 text-left">
          {{ item.value && item.value !== "" ? item.value : "-" }}
        </p>
      </div>
      <hr class="mb-3" />
      <div>
        <p class="font-weight-bold">Details</p>
        <div v-for="i in items" :key="i">
          <fieldDetails :params="i" class="mb-3" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import fieldDetails from "~/components/field";

export default {
  components: { fieldDetails },
  data() {
    return {
      items: 3,
      showDetails: [
        {
          name: "Name Surname",
          value: "Tong Hantahi"
        },
        {
          name: "Email",
          value: "123456789@gmail.com"
        },
        {
          name: "StudentID",
          value: "123456789"
        }
      ]
    };
  }
};
</script>

<style scoped>
.wrapper-page {
  padding: 20px;
}
</style>
