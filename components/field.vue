<template>
  <div>
    <v-card>
      <v-card-text>
        <v-col>
          <v-row>
            <div>
              <p>
                สนาม :
                {{ params }}
              </p>
            </div>
            <div class="ml-5">
              <p>
                สถานะ :
                {{ status }}
              </p>
            </div>
            <v-btn class="ml-auto" color="red">ยกเลิก</v-btn>
          </v-row>
          <v-row>
            <div>
              <p>
                วันที่ทำการจอง :
                {{ date1 }}
              </p>
            </div>
            <div class="ml-5">
              <p>
                วันที่จอง :
                {{ date2 }}
              </p>
            </div></v-row
          >
          <v-row>
            <div>
              <p>
                หมายเหตุ :
                {{ reason }}
              </p>
            </div>
          </v-row>
        </v-col>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
export default {
  props: ["params"],
  data() {
    return {
      status: "กำลังดำเนินการ",
      date1: "18/10/2021",
      date2: "19/10/2021 12.00pm - 13.00pm",
      reason: "bla bla bla"
    };
  },
  methods: {
    cancel() {}
  }
};
</script>

<style scoped></style>
