<script>
  import { omit } from '../lib/utils';

  export let size = 'large';
  export let color = 'text-primary';

  const COLOR_OPTS = ['primary', 'accent', 'text-primary', 'text-accent'];

  const SIZE_OPTS = ['tiny', 'small', 'medium', 'large', 'enormous', 'gigantic'];
  if (!SIZE_OPTS.includes(size)) {
    size = 'large';
  }

  if (!COLOR_OPTS.includes(color)) {
    color = 'primary';
  }

  $: props = {
    ...omit($$props),
    class: `heading ${size} ${color} ${$$props.class || ''}`,
  };
</script>

<style lang="scss">
  span {
    --gigantic: 17.942rem;
    --enormous: 11.089rem;
    --huge: 6.854rem;
    --large: 4.236rem;
    --medium: 2.618rem;
    --small: 1.618rem;
    --tiny: 1rem;
    display: block;
    color: var(--brand);
    font-size: 10px;
  }

  .primary {
    color: var(--brand);
  }

  .accent {
    color: var(--dark-accent);
  }

  .text-primary {
    color: var(--white);
  }

  .text-accent {
    color: var(--grey);
  }

  .tiny {
    font-size: var(--tiny);
  }

  .small {
    font-size: var(--small);
  }

  .medium {
    font-size: var(--medium);
  }

  .large {
    font-size: var(--large);
  }

  .huge {
    font-size: var(--huge);
  }

  .enormous {
    font-size: var(--enormous);
  }

  .gigantic {
    font-size: var(--gigantic);
  }
</style>

<span {...props}><slot/></span>
