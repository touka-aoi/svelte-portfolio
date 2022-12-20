<script lang="ts">
  import github from '$lib/images/github.svg';
	import twitter from '$lib/images/twitter.svg';
  
  interface outerLink {
		name:string
		src:string
		loc:string
	}

  const links:outerLink[] = [
      {name: "github", src: "https://github.com/touka-aoi", loc:twitter},
      {name: "twitter", src: "https://twitter.com/touka_aoi", loc:github},
    ];

</script>

<!-- 外部リンク -->
<section>
  <div class = "flex justify-center gap-8">  
    {#each links as {name, src, loc}}
      <div>
        <a href={src}>
          <img src={loc} alt={name} width=32px height=32px/>
        </a>
      </div>
    {/each}
  </div>
</section>