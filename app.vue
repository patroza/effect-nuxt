<template>
  <div>
    Hello {{ effect }}
  </div>
</template>

<script setup lang="ts">
import { Effect } from "effect"

const effect = Effect.succeed("world").pipe(Effect.runSync)

</script>
