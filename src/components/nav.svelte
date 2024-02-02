<script>
  let isMenuOpen = false;

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }
</script>

<nav class='w-100 p-4'>
  <div class='flex justify-between'>
    <div class='w-100'>
      <a href="/"><h1 class='text-3xl font-bold'>Mary Ann Hadley</h1></a>
    </div>
  {#if !isMenuOpen}
		<ul class='flex justify-center hidden'>
			<li class='px-3 text-xl'><a href="/">Home</a></li>
			<li class='px-3 text-xl'><a href="/graphic design">Graphic Design</a></li>
			<li class='px-3 text-xl'><a href="/blog">Art</a></li>
			<li class='px-3 text-xl'><a href="/contact">Contact Me</a></li>
		</ul>
		<div class='w-100 flex justify-end hidden'>
			<a href="https://www.instagram.com/_mhadley" target="_blank" rel="noopener noreferrer"><i class="fab fa-instagram fa-2x"></i></a>
			<a class='px-2' href="https://www.linkedin.com/in/mary-ann-hadley/" target="_blank" rel="noopener noreferrer"><i class="fab fa-linkedin fa-2x"></i></a>
		</div>
  {/if}
		<button class="burger-menu {isMenuOpen ? 'open' : 'closed'}" on:click={toggleMenu}>
			<i class="{isMenuOpen ? 'fa-solid fa-x' : 'fa-solid fa-bars'} fa-2xl"></i>
    </button>
  </div>
	{#if isMenuOpen}
		<div class='w-full flex justify-center'>
			<ul class='text-center text-xl'>
				<li><a href="/">Home</a></li>
				<li><a href="/graphic design">Graphic Design</a></li>
				<li><a href="/blog">Art</a></li>
				<li><a href="/contact">Contact Me</a></li>
				<li>My Socials</li>
				<div class='flex justify-evenly'>
					<li><a href="https://www.instagram.com/_mhadley" target="_blank" rel="noopener noreferrer"><i class="fab fa-instagram fa-2x"></i></a></li>
					<li><a href="https://www.linkedin.com/in/mary-ann-hadley/" target="_blank" rel="noopener noreferrer"><i class="fab fa-linkedin fa-2x"></i></a></li>
				</div>
			</ul>
		</div>
	{/if}
</nav>

<style>
  /* Add styles for burger menu */
  .burger-menu {
    cursor: pointer;
    transition: transform 0.3s ease; /* Add a transition effect on the transform property */

  }
  .burger-menu.open {
    transform: rotate(180deg); /* Apply a different transformation for the open state */
  }

  i {
    transition: opacity 0.3s ease; /* Add a transition effect on the opacity property */
  }

  .burger-menu.closed i.fa-bars {
    opacity: 1;
  }

  .burger-menu.open i.fa-bars {
    opacity: 0;
  }

  .burger-menu.closed i.fa-x {
    opacity: 0;
  }

  .burger-menu.open i.fa-x {
    opacity: 1;
  }

  /* Add media query to hide the menu on larger screens */
  @media (min-width: 768px) {
    .burger-menu {
      display: none;
    }
    /* Show navigation links on larger screens */
    ul {
      display: flex;
    }
		div {
			display: flex;
		}
  }
</style>
