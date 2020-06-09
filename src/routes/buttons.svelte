<script>
  import Plus from "svelte-material-icons/Plus.svelte";
  import Button from "../components/Button.svelte";
  import Alert from "../components/Alert.svelte";

  let value = "";
  let isLoading = true;
  let buttonClicked = false;
  let infoButtonClicked = false;
  let warningButtonClicked = false;
  let errorButtonClicked = false;

  function handleButtonClick() {
    buttonClicked = true;

    setTimeout(() => {
      buttonClicked = false;
    }, 5000);
  }

  function handleInfoButtonClicked() {
    infoButtonClicked = true;

    setTimeout(() => {
      infoButtonClicked = false;
    }, 5000);
  }
  function handleWarningButtonClicked() {
    warningButtonClicked = true;

    setTimeout(() => {
      warningButtonClicked = false;
    }, 5000);
  }
  function handleErrorButtonClicked() {
    errorButtonClicked = true;

    setTimeout(() => {
      errorButtonClicked = false;
    }, 5000);
  }
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
  <title>SavageUI - Buttons</title>
</svelte:head>
<article>
  <Alert
    variant="success"
    title="You clicked a button"
    text="Good for you"
    show={buttonClicked} />
  <Alert
    variant="info"
    title="You clicked a button"
    text="Good for you"
    show={infoButtonClicked} />
  <Alert
    variant="warning"
    title="You clicked a button"
    text="Good for you"
    show={warningButtonClicked} />
  <Alert
    variant="error"
    title="You clicked a button"
    text="Good for you"
    show={errorButtonClicked} />
  <h2>Buttons</h2>
  <Button>Default</Button>
  <Button type="primary" onclick={handleButtonClick}>Primary</Button>
  <Button type="accent" onclick={handleButtonClick}>Accent</Button>
  <Button type="success" onclick={handleButtonClick}>Success</Button>
  <Button type="info" onclick={handleInfoButtonClicked}>Info</Button>
  <Button type="warning" onclick={handleWarningButtonClicked}>Warning</Button>
  <Button type="danger" onclick={handleErrorButtonClicked}>Danger</Button>
  <Button type="primary" onclick={handleButtonClick} rounded>
    Rounded
  </Button>
  <Button type="primary" onclick={handleButtonClick} disabled>
    Disabled
  </Button>
  <Button type="primary" onclick={handleButtonClick} link>Link</Button>
  <Button type="primary" onclick={handleButtonClick} text>Text</Button>
  <Button type="primary" onclick={handleButtonClick} loading={isLoading}>
    Test the loading
  </Button>
  <Button type="primary" onclick={handleButtonClick} iconLeft={Plus}>
    Add
  </Button>
  <Button type="primary" onclick={handleButtonClick} iconRight={Plus}>
    Add
  </Button>
  <Button type="primary" onclick={handleButtonClick} block>Block</Button>
</article>
