<script>
    import MeetupItems from "./MeetupItems.svelte";

    export let meetups;
</script>

<section class="meetups">
    {#each meetups as meetup}
        <MeetupItems title={meetup.title} subtitle={meetup.subtitle} imageUrl={meetup.imageUrl} description={meetup.description} address={meetup.address} email={meetup.contactEmail}/>
    {/each}
</section>

<style>
    .meetups {
        display: grid;
        grid-template-columns: 1fr;
        grid-gap: 1rem;
        width: 100%;
        margin-top: 5rem;
    }
    @media (min-width: 768px) {
        .meetups {
            grid-template-columns: repeat(2, 1fr);
        }
    }
</style>