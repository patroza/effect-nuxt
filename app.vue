<template>
  <div>
    Hello {{ effect }} {{ effect2 }}
  </div>
</template>

<script setup lang="ts">
import { Option, Schedule } from "effect"
import { Effect } from "effect"
import * as Effect2 from "effect/Effect"

type TestType = Effect<never, never, number>


const a: Effect<string, string, void> = Effect.succeed("hello")

const effect = Effect.succeed("world").pipe(Effect.runSync)
const effect2 = Effect2.succeed("x2").pipe(Effect.runSync)

// const shouldFailCompiler: Effect<never, never, string> = Effect.succeed(1)

const ao = Option.none()
const bo = Option.some(1)
const co = bo.pipe((_) => Option.map((_) => 2)(_))

const as = Schedule.identity()
const bs = as.pipe((_) => Schedule.map((_) => 2)(_))


</script>
