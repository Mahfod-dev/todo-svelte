<script lang=ts>



async function getPostList(){
   
    try {
         const response = await fetch('https://jsonplaceholder.typicode.com/posts')
    const data = await response.json()
    
        return data
    
    } catch (error) {
        throw new Error("fetch not right");
         
    }
   
}

let promise = getPostList()

function handleClick(){
    promise = getPostList()
}

function mouseEnter(e){
  e.target.style.color = "purple"
}


</script>


<main>
    <button on:click={handleClick}>
        See all the posts
    </button>

  
{#await promise}
	<p>...waiting</p>
{:then posts}
        {#each posts as item}
        <ul>
            <li 
            on:mouseenter={mouseEnter}
            
            >{item.body}</li>
            </ul>
        {/each}
{:catch error}
	<p style="color: red">{error.message}</p>
{/await}
   

  
</main>

