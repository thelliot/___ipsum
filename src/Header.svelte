<script>
export let title;
</script>

<header>
  <h1>
    {title}
    <span>(ipsum)</span>
  </h1>
</header>

<style>
header {
  color: #fff;
  background: #000;
  text-align: center;
  padding: 3rem 0;
}
h1 {
  font-size: calc(1em + 10vw);
  margin: 0;
}
span {
  display: block;
  font-size: 1rem;
}
</style>