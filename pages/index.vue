<template>
  <section class="section">
    Editor:<br />

    <Editor type="link"></Editor>

    <br />
  </section>
</template>

<script>
import Editor from '~/components/Editor'

export default {
  name: 'HomePage',

  components: {
    Editor
  }
}
</script>
