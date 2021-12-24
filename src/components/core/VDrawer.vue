<template>
  <nav>
    <button>
      <img src="@/assets/images/guitar.png" alt="guitar" />
      <p>Guitar</p>
    </button>
    <button>
      <img src="@/assets/images/piano.png" alt="piano" />
      <p>Piano</p>
    </button>
    <button>
      <img src="@/assets/images/xylophone.png" alt="xylophone" />
      <p>Xylophone</p>
    </button>
  </nav>
</template>

<script>
export default {
  name: 'VDrawer',
}
</script>

<style scoped>
button {
  @apply flex items-center m-5;
}

p {
  @apply mx-5;
}
</style>
