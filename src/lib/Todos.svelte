<script lang=ts>
	
let inputValue=''
let results:string[] = []

$:console.log(inputValue)



function handleSubmit(e){
    e.preventDefault()
   if(inputValue === '') return

   if(inputValue === 'mahfod'){
    console.log("hello")
    alert(`hello ${inputValue}`)
}

    results = [...results,inputValue]

    inputValue = ''

    
}

function deleteTodo(id:number){

  const arrIndex = results.filter((_,index)=>{
    return index !== id
  })
results = [...arrIndex]

}

function updateTodo(id:number){
if(inputValue === '') return
  results =  results.map((result,index)=>{
        if(index === id){
            return inputValue
        }else{
            return result
        }
    })

}




</script>


<main>
    <h1>Todo</h1>
    <form on:submit={handleSubmit}>
    <input type="text" id="text" bind:value={inputValue}/>

    <button class="btn" type="submit">Submit</button>

    </form>

    <ul>
        {#each results as result, index}
            <li class="list">
                {result}
                <br style="margin: 10px;">
                <button on:click={() => deleteTodo(index)} class="btn">x</button>
                <button class="btn" on:click={()=> updateTodo(index)}>
                    Update ui
                </button>
            </li>
        {/each}
     
    </ul>

</main>

<style>
    .btn{
        padding: 0.25rem;
        font-size: x-small;
        margin-left: 10px ;
    }
    .list{
        display: flex;
       
    }
</style>