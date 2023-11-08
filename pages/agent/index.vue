<script setup>
  const { data: agents, pending } = useFetch(
    "https://valorant-api.com/v1/agents",
    {
      query: {
        isPlayableCharacter: true,
      },
    }
  )
</script>

<template>
  <v-theme-provider theme="dark" with-background>
    <v-img src="/bg.gif" cover>
      <v-container>
        <div>
          <v-btn
            variant="text"
            prepend-icon="mdi-arrow-left"
            @click="navigateTo('/')"
          >
            Menu Utama
          </v-btn>
        </div>

        <h1 class="mb-6">Agents</h1>

        <agent-list :agents="agents?.data" />
      </v-container>
    </v-img>
  </v-theme-provider>
</template>
