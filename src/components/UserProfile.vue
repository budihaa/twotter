<template>
    <div class="user-profile">
        <div class="user-profile__user-panel">
            <h1 class="user-profile__username">@{{ user.username }}</h1>
            <div class="user-profile__follower-count">
                <strong>Followers: </strong> {{ followers }}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "UserProfile",
    data() {
        return {
            followers: 0,
            user: {
                id: 1,
                username: "budihaa",
                firstName: "Budi",
                lastName: "Haryono",
                email: "budiharyono4@gmail.com",
                isAdmin: true,
            },
        };
    },
    computed: {
        fullName() {
            return `${this.user.firstName} ${this.user.lastName}`;
        },
    },
    methods: {
        followUser() {
            this.followers++;
        },
    },
    watch: {
        // Onchange
        followers(newCounter, oldCounter) {
            if (newCounter > oldCounter) {
                // alert('Hey you got new followers!');
            }
        },
    },
    mounted() {
        // this.followUser();
    },
};
</script>

<style scoped>
.user-profile {
    display: grid;
    grid-template-columns: 1fr 3fr;
    grid-gap: 50px;
    padding: 50px 5%;
}

.user-profile__username {
    font-size: 4.5vh;
    margin-bottom: 0.7rem;
    font-weight: bold;
}

.user-profile__user-panel {
    display: flex;
    flex-direction: column;
    padding: 20px;
    background-color: white;
    border-radius: 5px;
    border: 1px solid #dfe3e8;
    margin-bottom: auto;
}

.user-profile__admin-badge {
    background: rebeccapurple;
    color: white;
    border-radius: 5px;
    margin-right: auto;
    padding: 0 10px;
    font-weight: bold;
}

.user-profile__twoots-wrapper {
    display: grid;
    grid-gap: 10px;
    margin-bottom: auto;
}
</style>