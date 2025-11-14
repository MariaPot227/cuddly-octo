<script>
    import { prevent_default } from "svelte/internal";
    import Header from "./UI/Header.svelte";
    import MeetupGrid from "./meetups/MeetupGrid.svelte";

    let title = '';
    let subtitle = '';
    let address = '';
    let contactEmail = '';
    let description = '';
    let imageUrl = '';

    let meetups = [
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

    function addMeetup() {
        const newMeetup = {
            id: Math.random().toString(),
            title: title,
            subtitle: subtitle,
            description: description,
            imageUrl: imageUrl,
            address: address,
            contactEmail: contactEmail
        };

        meetups = [...meetups, newMeetup]; 

    }
</script>

<Header />
<main>
    
    <form on:submit|preventDefault={addMeetup}>
        <div class="form-control">
            <label for="title">Title</label>
            <input type="text" bind:value={title}>
        </div>
        <div class="form-control">
            <label for="subtitle">Subtitle</label>
            <input type="text" bind:value={subtitle}>
        </div>
        <div class="form-control">
            <label for="address">Address</label>
            <input type="text"bind:value={address}>
        </div>
        <div class="form-control">
            <label for="imageUrl">ImageUrl</label>
            <input type="text" bind:value={imageUrl}>
        </div>
        <div class="form-control">
            <label for="email">Email</label>
            <input type="email" bind:value={contactEmail}>
        </div>
        <div class="form-control">
            <label for="description">Description</label>
            <textarea rows="3" bind:value={description}></textarea>
        </div>
        <button type="submit">Save</button>
    </form>

    <MeetupGrid {meetups}/>
</main>

<style>
    main {
        margin-top: 5rem;
    }
    
</style>
