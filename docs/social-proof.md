## Example usage

```
<script lang="ts">
  import { Section, Social } from 'flowbite-svelte-blocks';
</script>

<Section name="social">
  <Social>
    <div class="flex flex-col items-center justify-center">
      <dt class="mb-2 text-3xl md:text-4xl font-extrabold">73M+</dt>
      <dd class="font-light text-gray-500 dark:text-gray-400">developers</dd>
    </div>
    <div class="flex flex-col items-center justify-center">
      <dt class="mb-2 text-3xl md:text-4xl font-extrabold">1B+</dt>
      <dd class="font-light text-gray-500 dark:text-gray-400">contributors</dd>
    </div>
    <div class="flex flex-col items-center justify-center">
      <dt class="mb-2 text-3xl md:text-4xl font-extrabold">4M+</dt>
      <dd class="font-light text-gray-500 dark:text-gray-400">organizations</dd>
    </div>
  </Social>
</Section>
```