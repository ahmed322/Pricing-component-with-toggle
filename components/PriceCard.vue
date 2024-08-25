<script setup lang="ts">
import type { PlanDetails } from "../types/planDetail";
// prop to recive plans data
defineProps<{ planDetail: PlanDetails }>();

let plan = useState("planName");
</script>
<template>
  <section
    class="mt-11 flex items-center justify-center rounded-lg bg-[#fefefe] shadow-card-shadow"
  >
    <!-- start card  design -->
    <div
      class="bg-gray-200 bg-light border-1 min-h-[450px] w-[320px] rounded-l border-darkGray p-5 text-center leading-8 md:w-[380px] lg:w-[320px]"
    >
      <h2 class="mb-4 text-xl font-bold">
        {{ "Basic" }}
      </h2>
      <h3
        class="flex min-h-[70px] items-center justify-center text-6xl font-bold"
      >
        <TransitionGroup
          name="fade-transition"
          enter-active-class="transition duration-500 linear hidden op-0"
          leave-active-class="trasition duration-500 linear op100"
          enter-from-class="translate-y-[5px] opacity-0"
          enter-to-class="translate-y-[0px] opacity-100"
          leave-from-class="translate-y-[0px] opacity-100"
          leave-to-class="translate-y-[5px]  opacity-0"
        >
          <span class="text-4xl" key="1">$</span>
          <span v-if="plan === 'monthly'" key="2">
            {{ planDetail.price.monthly }}
          </span>
          <span v-else key="3"> {{ planDetail.price.yearly }} </span>
        </TransitionGroup>
      </h3>
      <ul class="mb-3 mt-6 font-bold">
        <li class="border-y border-borderColor p-3">
          {{ planDetail.options.Storage }} Storage
        </li>
        <li class="border-b border-borderColor p-3">
          {{ planDetail.options.UsersNumber }} Users Allowed
        </li>
        <li class="border-b border-borderColor p-3">
          Send Up To {{ planDetail.options.dataSent }} GB
        </li>
      </ul>
      <slot name="button" />
    </div>
  </section>
</template>
