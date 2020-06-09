<script>
  export let segment;
</script>

<style>
  nav {
    border-right: 0.125rem solid var(--white-low-alpha);
    height: 100%;
    padding: 0;
    margin: 0;
    width: 20%;
  }

  nav .home {
    border-bottom: 0.125rem solid var(--white-low-alpha);
    color: var(--dark-accent);
    display: block;
    font-size: 2rem;
    padding-left: 0.5rem;
    width: 100%;
  }

  section {
    width: 100%;
  }

  section ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
  }

  section ul li {
    border-bottom: 0.0125rem solid var(--brand);
    padding: 1rem;
    width: 100%;
  }

  section ul li:hover {
    background-color: var(--brand-low-alpha);
    border-bottom: 0.0125rem solid var(--brand-high-alpha);
  }

  .heading {
    color: var(--dark-accent);
    font-weight: 700;
    text-transform: capitalize;
  }

  .heading:hover {
    background-color: unset;
    border-bottom: 0.0125rem solid var(--brand);
  }

  a {
    text-decoration: none;
    color: var(--brand);
  }

  a:hover ,
  [aria-current] {
    color: var(--dark-accent);
    font-weight: 700;
  }

  [aria-current] li{
    background-color: var(--brand-low-alpha);
    border-bottom: 0.0125rem solid var(--brand-high-alpha);
  }
</style>

<nav>
  <section>
    <ul>
      <a aria-current="{segment === undefined ? 'page' : undefined}" href="." class="home">Home</a>
      <li class="heading">Components</li>
      <a aria-current="{segment === "text-fields" ? 'page' : undefined}" href="/text-fields"><li>Text Fields</li></a>
      <a aria-current="{segment === "buttons" ? 'page' : undefined}" href="/buttons"><li>Buttons</li></a>
      <a aria-current="{segment === "checkbox-radio" ? 'page' : undefined}" href="/checkbox-radio"><li>Checkbox/Radio</li></a>
      <a aria-current="{segment === "date-pickers" ? 'page' : undefined}" href="/date-pickers"><li>Date Pickers</li></a>
      <a aria-current="{segment === "selects" ? 'page' : undefined}" href="/selects"><li>Selects</li></a>
      <a aria-current="{segment === "lists" ? 'page' : undefined}" href="/lists"><li>Lists</li></a>
      <a aria-current="{segment === "toasts" ? 'page' : undefined}" href="/toasts"><li>Toasts</li></a>
      <a aria-current="{segment === "dialogs" ? 'page' : undefined}" href="/dialogs"><li>Dialogs</li></a>
      <a aria-current="{segment === "drawers" ? 'page' : undefined}" href="/drawers"><li>Drawers</li></a>
      <a aria-current="{segment === "progress-bars" ? 'page' : undefined}" href="/progress-bars"><li>Progress Bars</li></a>
      <a aria-current="{segment === "tabs" ? 'page' : undefined}" href="/tabs"><li>Tabs</li></a>
      <a aria-current="{segment === "menus" ? 'page' : undefined}" href="/menus"><li>Menus</li></a>
      <a aria-current="{segment === "sliders" ? 'page' : undefined}" href="/sliders"><li>Sliders</li></a>
      <a aria-current="{segment === "tooltips" ? 'page' : undefined}" href="/tooltips"><li>Tooltips</li></a>
      <a aria-current="{segment === "alerts" ? 'page' : undefined}" href="/alerts"><li>Alerts</li></a>
      <a aria-current="{segment === "spinner" ? 'page' : undefined}" href="/spinner"><li>Spinner</li></a>
      <li class="heading">Typography</li>
      <a aria-current="{segment === "headings" ? 'page' : undefined}" href="/headings"><li>Heading</li></a>
      <a aria-current="{segment === "texts" ? 'page' : undefined}" href="/texts"><li>Text</li></a>
      <li class="heading">Layout</li>
      <a aria-current="{segment === "grid" ? 'page' : undefined}" href="/grid"><li>Grid</li></a>
      <li class="heading">Containers</li>
      <a aria-current="{segment === "cards" ? 'page' : undefined}" href="/cards"><li>Cards</li></a>
    </ul>
  </section>
</nav>
