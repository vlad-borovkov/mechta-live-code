<script setup lang="js">
import { MICard, MITag } from "mechtaui";
// что вернут эти сравнения?
function checkComparisons() {
  console.log("1)", 0 == "0"); // ?
  console.log("2)", 0 === "0"); // ?
  console.log("3)", "" == false); // ?
  console.log("4)", "" === false); // ?
  console.log("5)", 0 || "0"); // ?
  console.log("6)", 0 && "0"); // ?
  console.log("7)", false || ""); // ?
  console.log("8)", false && ""); // ?
  console.log("9)", null == undefined); // ?
  console.log("10)", null === undefined); // ?
}

// checkComparisons();
</script>

<template>
  <div class="flex flex-col gap-4">
    <MITag tag-value="/tasks/Compare.vue" type="info"></MITag>
    <MICard>
      <h2 class="font-semibold mb-2">Compare</h2>
      <p>Что вернут в консоль эти сравнения?<br /> Ответы оставляй напротив каждого. <br /> По завершению, запустим
        <MITag type="outline" tag-value="checkComparisons()"></MITag></p>
    </MICard>
  </div>
</template>
