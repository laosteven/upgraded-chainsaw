<template>
  <v-container>
    <v-row>
      <v-col cols="12" sm="2">
        <v-card width="400">
          <v-img
            height="200px"
            src="https://i.kym-cdn.com/photos/images/newsfeed/001/347/160/0c0.png"
          >
            <v-app-bar flat color="rgba(0, 0, 0, 0)">
              <v-app-bar-nav-icon color="white"></v-app-bar-nav-icon>

              <v-toolbar-title class="text-h6 white--text pl-0">
                Players
              </v-toolbar-title>

              <v-spacer></v-spacer>

              <v-btn color="white" icon>
                <v-icon>mdi-dots-vertical</v-icon>
              </v-btn>
            </v-app-bar>

            <v-card-title class="white--text mt-8">
              <v-avatar size="56">
                <img
                  alt="user"
                  src="https://bostonglobe-prod.cdn.arcpublishing.com/resizer/RHDkOXAijJlc7rv8Owlk19kcyt4=/1440x0/arc-anglerfish-arc2-prod-bostonglobe.s3.amazonaws.com/public/Y5GUIDYVWJGVFP5MWNYJR5375I.png"
                />
              </v-avatar>
              <p class="ml-3">Yvonnnn</p>
            </v-card-title>
          </v-img>

          <v-card-text>
            <v-timeline align-top dense>
              <v-timeline-item
                small
                v-for="(player, index) in players"
                :key="index"
              >
                <div>
                  <div class="font-weight-normal">
                    <strong>{{ player }}</strong>
                  </div>
                </div>
              </v-timeline-item>
            </v-timeline>
          </v-card-text>
        </v-card>
      </v-col>

      <v-col cols="12" sm="8">
        <v-card min-height="70vh" rounded="lg">
          <v-card-text>
           <v-card-title>BB keep your eyes on me</v-card-title>
           <v-btn @click="forYvonBB">Click me to randomize</v-btn>
           <v-img v-if="isClickedOnce" :src="url" />
          </v-card-text>
        </v-card>
      </v-col>

      <v-col cols="12" sm="2">
        <v-sheet rounded="lg" min-height="268">
          <!--  -->
        </v-sheet>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",
  data: () => ({
    isClickedOnce: false,
    url: '',
    players: [
      "LALALA",
      "Akuce",
      "KAA KAA BOO",
      "KKBOO",
      "YES",
      "anise regretting to give me ideas",
      "WAOW",
    ],
  }),
  mounted() {
    this.url = process.env.VUE_APP_FUDURU_URL;
  },
  methods: {
    forYvonBB() {
      this.isClickedOnce = true;
    },
  }
};
</script>

<style scoped>
</style>