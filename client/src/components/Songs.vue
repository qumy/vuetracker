<template>
  <v-layout column>
    <v-flex xs6 v-if="isUserLoggedIn">
      <panel>
      </panel>
    </v-flex>
  </v-layout>
</template>

<script>
import {mapState} from 'vuex'
export default {
  computed: {
    ...mapState([
      'isUserLoggedIn'
    ])
  }
}
</script>
