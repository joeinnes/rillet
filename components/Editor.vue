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
    <b-field label="Title">
      <b-input v-model="title"></b-input>
    </b-field>
    <b-field label="Note">
      <b-input v-model="note" type="textarea"></b-input>
    </b-field>
    <b-collapse :open="false">
      <div slot="trigger" slot-scope="props" role="button">
        <b-icon :icon="props.open ? 'menu-up' : 'menu-down'"></b-icon>
      </div>
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
      <b-field label="Source">
        <b-input v-model="source" type="url"></b-input>
      </b-field>
    </b-collapse>
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
      title: '',
      tags: [],
      source: ''
    }
  }
}
</script>
