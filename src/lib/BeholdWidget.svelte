<script >
  import { onMount, createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  /** @type {string} */
  export let feedId;

  onMount(() => {
    const existingScriptEl = document.querySelector(
      '[src*="https://w.behold.so/widget.js"]'
    )
    if (existingScriptEl || customElements.get("behold-widget")) return

    const scriptEl = document.createElement("script")
    scriptEl.src = "https://w.behold.so/widget.js"
    scriptEl.type = "module"
    document.body.appendChild(scriptEl)
  });
</script>

<behold-widget on:load={() => dispatch('load')} feed-id={feedId}></behold-widget>