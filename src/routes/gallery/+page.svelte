<script>
  export let data;
  const {artworks} = data;
  console.log(artworks);
  // console.log(artworks.pagination);
</script>

<h1>My Gallery</h1>
<div>
  <a href="/gallery" onclick="location.reload()">&lt; Prev</a>
  <a href="/gallery" onclick="location.reload()">Next &gt;</a>
</div>
<hr>
<section>
  {#each artworks as { title, artist_title, image_id, date_display, medium_display }}
  <figure>
    <img src="https://www.artic.edu/iiif/2/{image_id}/full/843,/0/default.jpg" alt="">
    <figcaption><strong>{title}</strong> by {artist_title}<br>{date_display} | {medium_display}</figcaption>
  </figure>
  {/each}
</section>


<style>
  hr {
    border-color: rgb(255, 209, 209);
    height: 1px;
    border-style: dashed;
  }
  figure {margin: 0;}
  div {
    margin: 1em 0;
  }
  a {
    text-decoration: none;
    border: 1px solid #ccc;
    background-color: #DADADA;
    padding: .5em 1em;
    transition: all .2s ease;
  }
  a:hover {
    background-color: #FAFAFA;
  }
  section {
    padding: 2em;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 2em;
  }
  img {
    width: 100%;
    height: auto;
  }
</style>