<template>
  <section>
    <section v-if="type === 'link'">
      <b-field label="Link">
        <b-input v-model="linkText" type="url"></b-input>
      </b-field>
    </section>
    <section v-if="type === 'song'">
      <b-field label="Song">
        <b-input v-model="linkText" type="url"></b-input>
      </b-field>
    </section>
    <section v-if="type === 'video'">
      <b-field label="Video">
        <b-input v-model="linkText" type="url"></b-input>
      </b-field>
    </section>
    <b-field label="Note">
      <b-input v-model="note" type="textarea"></b-input>
    </b-field>
    <b-field label="Add some tags">
      <b-taginput
        v-model="tags"
        ellipsis
        icon="label"
        placeholder="Add a tag"
        autocomplete
        allow-new
      >
      </b-taginput>
    </b-field>
  </section>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      linkText: '',
      note: '',
      tags: []
    }
  }
}
</script>
