<script>
    import Header from "./UI/Header.svelte";
    import MeetupItems from "./meetups/MeetupItems.svelte";

    const meetups = [
        {
            id: "m1",
            title: "Coding Bootcamp",
            subtitle: "Learn to code in 2 hours",
            description:
                "In meetup, we will have experts teach you how to code",
            imageUrl:
                "https://images.squarespace-cdn.com/content/v1/5fa1522044bdda192713063c/1d041c11-e762-4641-993b-591c9de72b76/Coffee+Beer+Cafe+in+Tiaong%2C+Quezon",
            address: "27th New Road, 23562 New York",
            contactEmail: "code@test.com",
        },
        {
            id: "m2",
            title: "Swim Together",
            subtitle: "Swimming lessons",
            description:
                "In meetup, we will have experts teach you how to swim",
            imageUrl:
                "https://kidsonboard.co.nz/wp-content/uploads/2016/07/Moana-Pool-440x230.jpg",
            address: "27th Moana Pool, 11111 New York",
            contactEmail: "swim@test.com",
        },
    ];
</script>

<Header />

<section class="meetups">
    {#each meetups as meetup}
        <MeetupItems title={meetup.title} subtitle={meetup.subtitle} imageUrl={meetup.imageUrl} description={meetup.description} address={meetup.address} email={meetup.contactEmail}/>
    {/each}
</section>

<style>
    .meetups {
        margin-top: 5rem;
    }
</style>
