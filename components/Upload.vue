<template>
  <div>
    <label for="o32fjwef32">{{ type }}</label>
    <input
      id="o32fjwef32"
      type="file"
      name="imgage"
      :accept="accept"
      :capture="capture"
      :multiple="multiple"
    />
  </div>
</template>

<script>
const UPLOAD_TYPES = ['gallery', 'camera', 'pdf']
export default {
  name: 'FileUpload',
  props: {
    type: {
      type: String,
      default: UPLOAD_TYPES[0],
      validator: (val) => UPLOAD_TYPES.includes(val),
    },
  },
  computed: {
    capture() {
      return this.type === 'camera' ? 'environment' : undefined
    },
    multiple() {
      return this.type === 'gallery'
    },
    accept() {
      return this.type === 'pdf' ? 'application/pdf' : 'image/*'
    },
  },
}
</script>
