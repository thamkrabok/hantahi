<template>
  <div class="wrapper-page">
    <div class="side-bar">
      <v-btn depressed router :to="`/home`" class="mb-5">
        <v-icon class="mr-3">mdi-arrow-left</v-icon>BACK
      </v-btn>
    </div>
    <div justify="center" align="center">
      <v-col cols="12" sm="8" md="6">
        <v-form ref="form" v-model="valid" lazy-validation>
          <div class="d-flex">
            <p class="mb-0 mr-3 pt-2">Field</p>
            <v-select
              v-model="field"
              :items="fields"
              style="margin-top: -8px;"
              :rules="[v => !!v || 'Item is required']"
              required
            ></v-select>
          </div>

          <div class="d-flex">
            <p class="mb-0 mr-3 pt-2">Due date & time</p>
            <v-text-field
              type="datetime-local"
              dense
              v-model="due_date"
              :rules="[v => !!v || 'Due Date is required']"
            />
          </div>

          <div class="d-flex">
            <p class="mb-0 mr-3 pt-2">Reason</p>
            <v-text-field
              dense
              v-model="reason"
              :rules="[v => !!v || 'Reason is required']"
            />
          </div>

          <div class="d-flex">
            <p class="mb-0 mr-3 pt-2">Phone</p>
            <v-text-field
              type="number"
              dense
              v-model="phone"
              :rules="[v => !!v || 'Phone is required']"
            />
          </div>
          <v-btn color="error" class="mr-4" @click="clear">
            Cancel
          </v-btn>

          <v-btn color="warning" @click="send">
            Send
          </v-btn>
        </v-form>
      </v-col>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      field: "",
      fields: ["A", "B", "C"],
      due_date: "",
      reason: "",
      phone: ""
    };
  },
  methods: {
    clear() {
      this.field = "";
      this.due_date = "";
      this.reason = "";
      this.phone = "";
    },
    send() {
      // console.log(this.field);
      // console.log(this.due_date);
      // console.log(this.reason);
      // console.log(this.phone);
    }
  }
};
</script>

<style scoped>
.wrapper-page {
  padding: 20px;
}
</style>
