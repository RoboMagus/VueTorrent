<template>
  <v-flex xs6 sm1 md1>
    <div class="caption grey--text">
      {{ $t('torrent.availability') | titleCase }}
    </div>
    <div>
      {{ availability }}
    </div>
  </v-flex>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { Torrent } from '@/models'

export default defineComponent({
  name: 'Availability',
  props: {
    torrent: Torrent
  },
  computed: {
    availability() {
      if (this.torrent && this.torrent.availability !== -1) {
        return this.torrent.availability
      }

      return 'N/A'
    }
  }
})
</script>
