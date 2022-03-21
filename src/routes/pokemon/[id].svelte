<script context="module">

    export async function load({fetch, params}) {
        const id  = params.id;
        console.log(id)
        const url = `https://pokeapi.co/api/v2/pokemon/${id}`;
        const res = await fetch(url);
        const pokeman = await res.json();

        return {props: {pokeman}}; 
    }

</script>
<script>
    export let pokeman;
    const type = pokeman.types[0].type.name;
    const id = `/#${pokeman.name}`;

    if(pokeman.id == 392) {
        pokeman.name = 'Fabio Roque';
        pokeman.type = 'Human';
        pokeman.height = '175cm';
        pokeman.weight = '85kg';
        pokeman.sprites['front_default'] = '/images/fabio.jpg';
    }
</script>


<div class="flex flex-col items-center">

    <a href={id} class="py-4 text-center">Go back</a>

    <h1 class="text-4xl font-semibold text-center pb-8">{pokeman.name}</h1>
    <p>type: <strong>{type}</strong> | height: <strong>{pokeman.height}</strong> | Weight: <strong>{pokeman.weight}</strong></p>
    
    <img class="card-image w-40" src={pokeman.sprites['front_default']} alt={pokeman.name}>
</div>