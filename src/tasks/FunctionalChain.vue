<script setup lang="ts">
import { MICard, MITag } from "mechtaui";
/*******************************************

ЗАДАЧА: написать конфигурируемую цепочку вызовов функций,
чтобы в консоль выводилась отформатированная марка авто.
Пример интерфейса и вызова

getCar(конфигурация регистра: нижний | верхний | undefined).print('марка авто', 'модель')
getCar(toUpper).print('Honda', 'Fit') --> HONDA FIT


Модульный стиль
Фабричный метод
Функциональный стиль 
Использует замыкания 

/******************************************* */
type CaseTransform = "UpperCase" | "LowerCase" | undefined;

const getCar = (caseTransform: CaseTransform) => {
  return {
    print: (brand: string, model: string) => {
      let formatted = `${brand} ${model}`;
      if (caseTransform === "LowerCase") {
        formatted = formatted.toLowerCase();
      } else if (caseTransform === "UpperCase") {
        formatted = formatted.toUpperCase();
      }
      console.log(formatted);
    },
  };
};

getCar("UpperCase").print("Toyota", "Camry");
getCar("LowerCase").print("Toyota", "Corolla");
getCar(undefined).print("Mercedes-benz", "E 350");

</script>

<template>
    <div class="flex flex-col gap-4">
        <MITag tag-value="./tasks/FunctionalChain.vue" type="info"></MITag>
        <MICard class="flex flex-col gap-4">
            <h2 class="font-semibold mb-2">FunctionalChain</h2>
            <code>
                ЗАДАЧА: написать конфигурируемую цепочку вызовов функций,
                чтобы в консоль выводилась отформатированная марка авто.
            </code>

            <p>Пример интерфейса и вызова:</p>

            <code>
            getCar(конфигурация регистра: нижний | верхний | undefined).print('марка авто', 'модель')
            getCar(toUpper).print('Honda', 'Fit') -> HONDA FIT
            </code>

            <p>Будет полезным придерживаться даннных принципов:</p>
            <ul>
                <li>Модульный стиль (инкапсуляция вспомогательных функций)</li>
                <li> Фабричный метод </li>
                <li> Функциональный стиль (чистые функции, отсутствие мутаций)</li>
                <li> Использует замыкания</li>
            </ul>
        </MICard>
    </div>
</template>
