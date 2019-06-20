<template>
  <b-dropdown text="Import"
              variant="primary"
              split
              right
              @click="$emit('click', importUrl)">
    <b-dropdown-item-button @click="$emit('click', importUrl)">Import to Karabiner-Elements</b-dropdown-item-button>
    <b-dropdown-divider></b-dropdown-divider>
    <b-dropdown-item-button @click="$emit('show-json-click', id)">
      <small>Show JSON</small>
    </b-dropdown-item-button>
    <b-dropdown-item-button v-clipboard:copy="pageUrl + '#' + id"
                            v-clipboard:success="urlCopied"
                            v-clipboard:error="urlCopyFailed">
      <small>Copy URL</small>
    </b-dropdown-item-button>
    <b-dropdown-item-button v-clipboard:copy="pageUrl + jsonUrl"
                            v-clipboard:success="urlCopied"
                            v-clipboard:error="urlCopyFailed">
      <small>Copy JSON URL</small>
    </b-dropdown-item-button>
  </b-dropdown>
</template>

<script>
export default {
  props: [
    'id',
    'importUrl',
    'jsonUrl'
  ],
  data() {
    return {
      pageUrl: window.location.origin + window.location.pathname,
    }
  },
  methods: {
    urlCopied(e) {
      alert('You just copied: ' + e.text)
    },

    urlCopyFailed() {
      alert('Failed to copy texts')
    }
  }
}
</script>
