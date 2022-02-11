<script>
    export let pokeman; 
</script>

<a
id={pokeman.name} 
class="p-6 bg-gray-100 text-gray-800 text-center rounded-md shadow-sm hover:bg-gray-200 hover:shadow-md flex flex-col items-center"
href={`/pokemon/${pokeman.id}`}>
    <img class="h-40 w-40" src={pokeman.image} alt={pokeman.name}>
    <h2 class="font-semibold capitalize text-2xl">{pokeman.id}. {pokeman.name}</h2>
</a>