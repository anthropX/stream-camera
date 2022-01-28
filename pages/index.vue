<template>
  <div>
    <Upload type="gallery" />
    <Upload type="camera" />
    <Upload type="pdf" />

    <center>
      <video ref="video" width="640" height="480" autoplay></video>
    </center>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  mounted() {
    const video = this.$refs.video
    const mediaStream = new MediaStream()
    video.srcObject = mediaStream
  },
}
</script>
