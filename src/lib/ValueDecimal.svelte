<script>
    export let value;
    export let min;
    export let max;
    export let precision;

    const handleChange = (e) => {
        // TODO
        value = e.target.value;
        if (!isNaN(precision))
        {
            value.toFixed(precision);
        }
        if (value > max)
            value = max;
        if (value < min)
            value = min;
        // -------------------------
    }
</script>
<div class="tooltip tooltip-right" data-tip= "Max: {max ?? 'none'} |  Min: {min ?? 'none'} | Precision: {precision ?? 'none'}">
<!--    TODO -->
    <input
      type="number"
      min="{min ?? ''}"
      max="{max ?? ''}"
      bind:value ="{value}"
      class="input input-bordered w-full border-accent"
      on:change ="{handleChange}"
    />
<!--         -->
</div>
