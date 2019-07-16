<script>
export default {
  name: 'fileUpload',
  data: () => ({
    types: [''],
    cards: ['1', '2', '3'],
    socials: [
      {
        icon: 'fab fa-facebook',
        color: 'green'
      },
      {
        icon: 'fab fa-linkedin',
        color: 'cyan darken-1'
      },
      {
        icon: 'fab fa-instagram',
        color: 'red lighten-3'
      }
    ]
  }),

  methods: {
    getImage () {
      const min = 550
      const max = 560

      return Math.floor(Math.random() * (max - min + 1)) + min
    }
  }
}
</script>

<template>
  <div>
    <v-card flat tile>
      <v-toolbar
        color="cyan"
        dark
      >
        <v-toolbar-side-icon></v-toolbar-side-icon>

        <v-toolbar-title>REMOTE.MODULE.TEST.MODULE</v-toolbar-title>

        <v-spacer></v-spacer>

        <v-btn icon>
          <v-icon>search</v-icon>
        </v-btn>
      </v-toolbar>

      <v-toolbar
        color="blue"
        dark
      >
        <v-toolbar-title>File Upload </v-toolbar-title>

        <v-spacer></v-spacer>

        <span>Total file size: <b>28.54 kB</b> of max <b>5.12 MB </b>Total files: <b>4</b> of max <b>10</b></span>
      </v-toolbar>

      <v-container
        v-for="type in types"
        :key="type"
        fluid
        grid-list-md
        grey
        lighten-4
      >
        <v-subheader>{{ type }}</v-subheader>

        <v-layout row wrap>
          <v-flex
            v-for="card in cards"
            :key="card"
            xs3
          >
            <v-card>
              <v-img
                :src="`https://picsum.photos/200/300?image=${getImage()}`"
                height="300px"
              >
              <span
                class="headline white--text pl-3 pt-3"
                v-text="card.title"
              ></span>
              </v-img>
              <v-card-actions class="white justify-center">
                <v-text-field
                  value="This is title"
                  label="Title"
                  readonly
                ></v-text-field>
                <span><b>14.4 kB</b></span>
                <v-icon large >cloud_upload</v-icon>
                <v-icon large >delete</v-icon>
              </v-card-actions>
            </v-card>
          </v-flex>
          <v-flex xs3>
            <v-card>
              <v-icon class="icon_align"> note_add </v-icon>

              <v-card-actions class="white justify-center">
                <span>Drop files here, <b>browse</b> or import from..</span>
              </v-card-actions>
            </v-card>
          </v-flex>
        </v-layout>
        <v-btn color="blue">Upload
          <v-icon>cloud_upload</v-icon>
        </v-btn>
      </v-container>
    </v-card>
  </div>
</template>
<style scoped>
.icon_align {
  font-size: 300px;
  width: 100%
}
</style>
