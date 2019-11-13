<template>
  <section>
    <b-field v-if="type === 'link'">
      <b-input
        v-model="linkText"
        type="url"
        icon="link-variant"
        placeholder="Link"
      ></b-input>
    </b-field>

    <b-field v-if="type === 'song'">
      <b-input
        v-model="linkText"
        type="url"
        icon="music-note"
        placeholder="Link to song"
      ></b-input>
    </b-field>

    <b-field v-if="type === 'video'">
      <b-input
        v-model="linkText"
        type="url"
        icon="movie"
        placeholder="Link to video"
      ></b-input>
    </b-field>

    <section v-if="type === 'image'">
      <b-field>
        <b-upload v-model="dropFiles" multiple drag-drop>
          <section class="section">
            <div class="content has-text-centered">
              <p>
                <b-icon icon="upload" size="is-large"></b-icon>
              </p>
              <p>Upload one or more photos</p>
            </div>
          </section>
        </b-upload>
      </b-field>

      <div class="tags">
        <span
          v-for="(file, index) in dropFiles"
          :key="index"
          class="tag is-primary"
        >
          {{ file.name }}
          <button
            @click="deleteDropFile(index)"
            class="delete is-small"
            type="button"
          ></button>
        </span>
      </div>
    </section>

    <b-field>
      <b-input
        v-model="title"
        icon="format-title"
        placeholder="Title"
      ></b-input>
    </b-field>

    <b-field>
      <b-input v-model="note" type="textarea" placeholder="Note"></b-input>
    </b-field>

    <b-collapse :open="false">
      <div slot="trigger" slot-scope="props" role="button">
        <b-icon :icon="props.open ? 'chevron-down' : 'chevron-up'"></b-icon>
      </div>
      <b-field>
        <b-taginput
          v-model="tags"
          ellipsis
          icon="tag-multiple"
          placeholder="#tags"
          autocomplete
          allow-new
        >
        </b-taginput>
      </b-field>
      <b-field>
        <b-input
          v-model="source"
          type="url"
          icon="link-variant"
          placeholder="Source"
        ></b-input>
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
      source: '',
      dropFiles: [],
      isComponentModalActive: true
    }
  }
}
</script>
