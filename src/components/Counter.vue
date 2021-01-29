<template>
  <div>
    <section
      class="text-3xl flex justify-center content-center flex-col mx-auto text-center"
    >
      Buy Now
    </section>
    <section class="felx text-6xl justify-center content-center">
      <div class="label text-sm absolute bottom-0">days</div>
    </section>
    {{ displayDays }}
    {{ displayHours }}
    {{ displayminutes }}
    {{ displaySeconds }}
  </div>
</template>

<script>
export default {
  name: "Counter",
  data: () => ({
    displayDays: 0,
    displayHours: 0,
    displayminutes: 0,
    displaySeconds: 0,
  }),
};
</script>

<style lang="scss" scoped></style>
