<script>
  export let segment;

  let isMenuOpen = false;
  const homePage = false;
  const closeMenu = () => {
    isMenuOpen = false;
  };
  const toggleMenu = () => {
    isMenuOpen = !isMenuOpen;
  };
</script>

<style>
  .header {
    z-index: 99;
    position: fixed;
    width: 100%;
    margin: 0 auto;
  }
  .header-top {
    display: flex;
    justify-content: space-between;
    padding: 1rem 1.5rem;
  }
  h1 {
    margin: 0;
    font-size: 36px;
  }
  h1 a {
    color: var(--black);
  }

  .wrapper-menu {
    margin-top: 4px;
    width: 26px;
    height: 26px;
    display: none;
    flex-direction: column;
    justify-content: space-between;
    cursor: pointer;
    transition: transform 330ms ease-out;
  }
  .wrapper-menu.open {
    transform: rotate(-45deg);
  }

  .light-menu .header-top h1 a {
    color: var(--white);
    text-shadow: 2px 2px var(--dark-grey);
  }
  .light-menu nav ul li a {
    color: var(--light-grey);
    text-shadow: 1px 1px 3px var(--dark-grey);
  }
  .light-menu:hover {
    color: var(--white);
  }

  nav {
    position: fixed;
    padding: 5rem 1.5rem;
    z-index: 9;
  }
  ul li {
    padding: 10px 0;
    margin: 0;
  }
  li a {
    color: var(--medium-grey);
  }
  li a:hover {
    color: var(--black);
  }

  .active {
    color: var(--black);
  }
  .sub-nav {
    padding: 0;
  }
  .sub-nav a {
    text-transform: uppercase;
    font-size: 12px;
    margin-left: 20px;
  }

  nav ul li.nav a {
    transition: font-size var(--transition-time) ease;
    font-size: 48px;
  }

  .nav a {
    font-size: 48px;
  }
  .nav a:hover {
    font-size: 72px;
  }

  @media only screen and (max-width: 768px) {
    .header-top {
      background: var(--dark-grey);
    }
    .header-top h1 a {
      color: var(--white);
      text-shadow: 2px 2px var(--dark-grey);
    }
    .wrapper-menu {
      display: flex;
    }
    .line-menu {
      background-color: #fff;
      border-radius: 1px;
      width: 100%;
      height: 6px;
    }
    .line-menu.half {
      width: 50%;
    }
    .line-menu.start {
      transition: transform 330ms cubic-bezier(0.54, -0.81, 0.57, 0.57);
      transform-origin: right;
    }
    .line-menu.start.open .line-menu.start {
      transform: rotate(-90deg) translateX(3px);
    }
    .line-menu.end {
      align-self: flex-end;
      transition: transform 330ms cubic-bezier(0.54, -0.81, 0.57, 0.57);
      transform-origin: left;
    }
    .line-menu.end.open .line-menu.end {
      transform: rotate(-90deg) translateX(-3px);
    }

    nav {
      overflow-y: hidden;
      max-height: 500px;
      transition-property: all;
      transition-duration: 0.5s;
      transition-timing-function: cubic-bezier(0, 1, 0.5, 1);
      width: 100%;
      background: var(--dark-grey);
      box-shadow: 0 3px 3px rgba(0, 0, 0, 0.12), 0 3px 2px rgba(0, 0, 0, 0.24);
    }
    nav.closed {
      padding: 0 1.5rem;
      max-height: 0;
    }
    ul {
      padding-bottom: 10px;
    }
    ul li .active {
      color: var(--light-grey);
    }
    li a {
      color: var(--grey);
    }
    li a:hover {
      color: var(--light-grey);
    }
  }
</style>

<aside class={segment === undefined ? 'light-menu' : ''}>
  <div class="header">
    <div class="header-top">
      <h1>
        <a class={segment === undefined ? 'active' : ''} href=".">
          <strong>ERIC SARTORIUS</strong>
        </a>
      </h1>
      <div
        class={`wrapper-menu ${isMenuOpen ? 'open' : ''}`}
        on:click={toggleMenu}>
        <div class="line-menu half start" />
        <div class="line-menu" />
        <div class="line-menu half end" />
      </div>
    </div>
  </div>
  <nav on:click={closeMenu} class={`${isMenuOpen ? '' : 'closed'}`}>
    <ul>
      <li class="nav">
        <a class={segment === 'about' ? 'active' : ''} href="about">about</a>
      </li>
      <li class="nav">
        <a
          rel="prefetch"
          class={segment === 'portfolio' ? 'active' : ''}
          href="portfolio">
          portfolio
        </a>
      </li>
      <li class="nav">
        <a
          rel="prefetch"
          class={segment === 'blog' ? 'active' : ''}
          href="blog">
          blog
        </a>
      </li>
      <li class="nav">
        <a class={segment === 'contact' ? 'active' : ''} href="contact">
          contact
        </a>
      </li>
    </ul>
  </nav>
</aside>
