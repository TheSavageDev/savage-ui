<script>
  import Alert from "../components/Alert.svelte";
</script>

<style>
  article {
    padding: 0.125rem;
  }

  article h2 {
    border-bottom: 0.125rem solid var(--brand-low-alpha);
    color: var(--white);
    font-size: 3rem;
    margin-bottom: 1rem;
    text-shadow: 1px 1px var(--brand-low-alpha);
  }
</style>

<svelte:head>
  <title>SavageUI - Alerts</title>
</svelte:head>
<article>
  <h2>Alerts</h2>
  <h3>Default</h3>
  <Alert
    show
    variant="success"
    title="Success"
    text="This is a success alert" />
  <Alert
    show
    variant="warning"
    title="Warning"
    text="This is a warning alert" />
  <Alert show variant="error" title="Error" text="This is an error alert" />
  <Alert
    show
    variant="info"
    title="Informational"
    text="This is an informational alert" />
</article>
<article>
  <h3>Filled</h3>
  <Alert
    show
    filled
    variant="success"
    title="Success"
    text="This is a success alert" />
  <Alert
    show
    filled
    variant="warning"
    title="Warning"
    text="This is a warning alert" />
  <Alert show filled variant="error" title="Error" text="This is an error alert" />
  <Alert
    show
    filled
    variant="info"
    title="Informational"
    text="This is an informational alert" />
</article>
<article>
  <h3>No Icons</h3>
  <Alert
    show
    icon={false}
    variant="success"
    title="Success"
    text="This is a success alert" />
  <Alert
    show
    icon={false}
    variant="warning"
    title="Warning"
    text="This is a warning alert" />
  <Alert show icon={false} variant="error" title="Error" text="This is an error alert" />
  <Alert
    show
    icon={false}
    variant="info"
    title="Informational"
    text="This is an informational alert" />
</article>
<article>
  <h3>No Title</h3>
  <Alert
    show
    icon={false}
    variant="success"
    text="This is a success alert" />
  <Alert
    show
    icon={false}
    variant="warning"
    text="This is a warning alert" />
  <Alert show icon={false} variant="error" text="This is an error alert" />
  <Alert
    show
    icon={false}
    variant="info"
    text="This is an informational alert" />
</article>
<article>
  <h3>Outlined</h3>
  <Alert
    show
    outlined
    variant="success"
    title="Success"
    text="This is a success alert" />
  <Alert
    show
    outlined
    variant="warning"
    title="Warning"
    text="This is a warning alert" />
  <Alert show outlined variant="error" title="Error" text="This is an error alert" />
  <Alert
    show
    outlined
    variant="info"
    title="Informational"
    text="This is an informational alert" />
</article>
