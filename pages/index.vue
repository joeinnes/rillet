<template>
  <section class="section">
    Editor:<br />

    <b-tabs v-model="selectedTab" class="block">
      <b-tab-item>
        <template slot="header">
          <div class="has-text-centered">
            <b-icon icon="text"></b-icon>
            <p>Text</p>
          </div>
        </template>
      </b-tab-item>
      <b-tab-item label="Photo" icon="camera"></b-tab-item>
      <b-tab-item label="Quote" icon="format-quote-open"></b-tab-item>
      <b-tab-item label="Link" icon="link-variant"></b-tab-item>
      <b-tab-item label="Chat" icon="forum"></b-tab-item>
      <b-tab-item label="Audio" icon="music-note"></b-tab-item>
      <b-tab-item label="Video" icon="movie"></b-tab-item>
    </b-tabs>
    {{ selectedTab }}
    {{ editorType }}
    <Editor :type="editorType"></Editor>

    <br />
  </section>
</template>

<script>
import Editor from '~/components/Editor'

export default {
  name: 'HomePage',

  components: {
    Editor
  },

  data() {
    return {
      selectedTab: 0
    }
  },

  computed: {
    editorType() {
      const listOfTypes = [
        'note',
        'image',
        'quote',
        'link',
        'chat',
        'song',
        'video'
      ]
      return listOfTypes[this.selectedTab]
    }
  }
}
</script>
