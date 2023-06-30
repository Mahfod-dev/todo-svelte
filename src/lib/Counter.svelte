<script>
    let count = 0

    $:if(count>=10){
        alert(`Count is dangerously high!`)
        count=9
    }

    $:double = count * 2

    function increment(){
        count+=1
    }

    function decrement(){
        count-=1
    }

    function reset(){
        count=0
    }

    

</script>

<main>
    <h1>Count: {count}</h1>
    <p>{double}</p>
    <button on:click={increment}>Increment</button>
    <button on:click={reset}>Reset</button>
    <button on:click={decrement}>Decrement</button>


</main>

<style>
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
    }

    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 4em;
        font-weight: 100;
    }

    button {
        border-radius: 4px;
        padding: 1.5em 1em;
        margin:10px;
        background-color: #ff3e00;
        border: none;
        color: white;
    }
</style>