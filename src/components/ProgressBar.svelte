<script>
  import { omit } from "../lib/utils";

  export let height = "small";
  export let value = 0;
  export let max = 100;
  export let valueText = null;
  export let color = null;

  const normalizedValue = (value / max) * 100;

  $: props = {
    ...omit($$props),
    class: `progress ${color} ${height} ${$$props.class || ""}`,
  };
</script>

<style>
  progress {
    -webkit-appearance: none;
    appearance: none;
    display: block;
    margin: 0.5rem;
    width: 100%;
  }

  progress::-webkit-progress-bar {
    background-color: #e2e2e2;
    border-radius: 2px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.25) inset;
  }

  progress::-webkit-progress-value {
    background-color: var(--brand);
  }

  progress.america::-webkit-progress-value {
    background-image: -webkit-linear-gradient(transparent 33%, transparent 66%),
      -webkit-linear-gradient(left, #bf0a30, #fff, #002868);
  }
  progress.red::-webkit-progress-value {
    background-color: var(--danger);
  }
  progress.orange::-webkit-progress-value {
    background-color: var(--warning);
  }
  progress.yellow::-webkit-progress-value {
    background-color: var(--dark-accent);
  }
  progress.green::-webkit-progress-value {
    background-color: var(--success);
  }
  progress.blue::-webkit-progress-value {
    background-color: var(--info);
  }
  progress.purple::-webkit-progress-value {
    background-color: rgb(101, 0, 190);
  }
</style>

<progress
  {...props}
  max={100}
  aria-valuemax={100}
  aria-valuemin={0}
  {value}
  aria-valuenow={normalizedValue}
  aria-valuetext={valueText}
  tabIndex="-1" />
