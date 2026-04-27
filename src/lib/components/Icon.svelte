<script>
    const { name, variant = "regular"} = $props();

    let pack = $derived.by(() => {
        switch (variant) {
            case "regular": 
                return "ph";
            case"fill":
                return "ph-fill";
            default: 
                return "ph";
        }
    });
</script>

/* inserisco il link delle icone nell'head di questo documento e non 
in +layout.svelte perché altrimenti tutte le pagine caricherebbero le icone anche quando
non vengono usate */
<svelte:head>
    <link
      rel="stylesheet"
      type="text/css"
      href="https://cdn.jsdelivr.net/npm/@phosphor-icons/web@2.1.1/src/regular/style.css"
    />

    <link
      rel="stylesheet"
      type="text/css"
      href="https://cdn.jsdelivr.net/npm/@phosphor-icons/web@2.1.1/src/fill/style.css"
    />
</svelte:head>
  
<i class="{pack} ph-{name}"></i> 