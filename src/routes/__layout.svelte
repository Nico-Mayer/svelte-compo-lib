<script>
  import "@unocss/reset/tailwind.css"
  import "uno.css"

  import { isDark } from "../stores/dark"
  import { themeCheck } from "../lib/composables/darkMode"
  import { onMount } from "svelte"
  onMount(() => {
    // this sets the stor value of isDark on page load
    if (themeCheck()) {
      $isDark = true
    } else {
      $isDark = false
    }
  })
</script>

<main>
  <slot />
</main>

<style>
  :root {
    background-color: #e7e5e4;
    color: #374151;
  }
  :root.dark {
    background-color: #374151;
    color: #e7e5e4;
  }
</style>
