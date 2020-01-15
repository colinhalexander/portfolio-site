<script>

</script>

<nav>
  <p>
    {"{"} <a href="#about">about</a>,  <a href="#portfolio">portfolio</a>,  <a href="#contact">contact</a> {"}"}
  </p>
  <div>
    <img src="https://www.shareicon.net/data/2016/06/20/606964_github_4096x4096.png" alt="github" />
    <img src="/media/LI-In-Bug.png" alt="linkedin" />
    <img src="/media/medium-logo.png" alt="medium" />
  </div>
</nav>

<style>
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    background-color: darkslategray;
    padding: 10px 10px;
  }

  nav > * {
    width: max-content;
  }

  a, p {
    color: white;
    font-weight: 400;
  }

  div {
    display: flex;
    align-items: center;
  }

  img {
    width: 60px;
    padding: 0 5px;
  }

  img:nth-child(2) {
    width: 50px;
  }

  img:hover {
    cursor: pointer;
  }
</style>