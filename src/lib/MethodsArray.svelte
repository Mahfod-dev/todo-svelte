<script lang="ts">
    let sumArr = [1, 2, 3, 4, 5, 6, 7, 8, 9];

    const person = [{
        name: 'John',
        age: 30,
        hobbies: ['Sports', 'Cooking'],
        role: [2, 'author']
    },
    {
        name: 'Elsa',
        age: 18,
        hobbies: ['Eating', 'Cooking'],
        role: [1, 'developer']
    }


];


    export let answer: string;

    function addNum(){
       
    sumArr = [...sumArr, sumArr.length + 1]

    }
  

    $:result = sumArr.reduce((a, b) => a + b, 0)



</script>


<main>
<button on:click={addNum}>
        add num
</button>
<p>{result}</p>
<p>{answer}</p>

{#each person as p}
    <div>
        <h2>{p.name}</h2>
        <p>{p.age}</p>
        <p>{p.hobbies}</p>
        <p>{p.role}</p>
    </div>
{/each}



</main>