<script setup>
let plan = ref("monthly");
// useState is a custom hook that returns the value of a state
useState("planName", () => plan.value);

function togglePlan() {
  plan.value === "monthly" ? (plan.value = "yearly") : (plan.value = "monthly");
}

// watch changes in plan state
watch(plan, () => {
  useState("planName").value = plan.value;
});
</script>
<template>
  <div class="flex items-center justify-center">
    <p
      class="font-bold"
      :class="plan !== 'monthly' ? 'text-darkGray' : 'text-lightGray'"
    >
      Anually
    </p>
    <span
      @click="togglePlan"
      class="relative mx-3 inline-block h-8 w-16 rounded-full bg-gradient-to-tr p-1 hover:cursor-pointer"
      :class="
        plan !== 'monthly'
          ? 'from-softViolet to-skyBlue'
          : 'from-skyBlue to-softViolet'
      "
    >
      <span
        class="bg-white absolute top-[50%] z-50 inline-block h-6 w-6 translate-y-[-50%] rounded-full bg-mist transition-all duration-300 content-['']"
        :class="plan !== 'monthly' ? 'translate-x-0' : 'translate-x-8'"
      ></span>
    </span>
    <p
      class="text-gray-600 font-bold"
      :class="plan === 'monthly' ? 'text-darkGray' : 'text-lightGray'"
    >
      Monthly
    </p>
  </div>
</template>
