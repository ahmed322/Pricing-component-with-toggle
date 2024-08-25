<script setup lang="ts">
useHead({
  title: "Frontend Mentor | Pricing component with toggle",
  link: [
    {
      rel: "icon",
      type: "image/png",
      sizes: "32x32",
      href: "/favicon-32x32.png",
    },
  ],
});
// <link rel="icon" type="image/png" sizes="32x32" href="./images/favicon-32x32.png">

// <title>Frontend Mentor | [Challenge Name Here]</title>
</script>

<template>
  <div class="relative bg-no-repeat">
    <NuxtRouteAnnouncer />
    <NuxtPage />

    <div class="attribution mt-8 text-center">
      Challenge by
      <NuxtLink
        to="https://www.frontendmentor.io?ref=challenge"
        target="_blank"
        class="text-skyBlue hover:text-softViolet"
        >Frontend Mentor</NuxtLink
      >. Coded by
      <NuxtLink
        class="text-skyBlue hover:text-softViolet"
        to="https://github.com/ahmed322"
        target="_blank"
        >AMK</NuxtLink
      >.
    </div>
  </div>
</template>

<style>
/* change back ground image in  */
body {
  background-image: url("./assets/images/bg-top.svg"),
    url("./assets/images/bg-bottom.svg");
  background-position:
    top right,
    0% 130%;
  background-repeat: no-repeat, no-repeat;
}
</style>
