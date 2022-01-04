<script>
  import "./styles.css";
  import { Link } from "svelte-navigator";
  import {
    Collapse,
    Navbar,
    NavbarToggler,
    NavbarBrand,
    Nav,
    NavItem,
  } from "sveltestrap";

  const navOptions = [
    { label: "Home", to: "/" },
    { label: "Films", to: "films" },
    { label: "TV Series", to: "tvseries" },
    { label: "Animes", to: "animes" },
  ];

  let isOpen = false;

  const handleUpdate = (e) => {
    isOpen = e.detail.isOpen;
  };
</script>

<Navbar color="dark" dark expand="md">
  <NavbarBrand href="/">My TV Time</NavbarBrand>
  <NavbarToggler on:click={() => (isOpen = !isOpen)} />
  <Collapse {isOpen} navbar expand="md" on:update={handleUpdate}>
    <Nav class="ms-auto" navbar>
      {#each navOptions as option}
        <NavItem>
          <Link to={option.to}>{option.label}</Link>
        </NavItem>
      {/each}
    </Nav>
  </Collapse>
</Navbar>
