<template>
  <v-flex xs12 sm1 md1 class="mr-4">
    <div class="caption grey--text">
      {{ $t('torrent.progress') | titleCase }}
    </div>
    <v-progress-linear :value="torrent.progress" height="20" :style="phoneLayout ? '' : 'width: 80%;'" :color="`torrent-${state}`" rounded>
      <span class="caption white--text"> {{ torrent.progress }}% </span>
    </v-progress-linear>
  </v-flex>
</template>

<script lang="ts">
import { TorrentDashboardItem } from '@/mixins'
import { defineComponent } from 'vue'
import { Torrent } from '@/models'

export default defineComponent({
  name: 'Progress',
  mixins: [TorrentDashboardItem],
  props: {
    torrent: Torrent
  }
})
</script>
