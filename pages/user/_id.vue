<template lang="html">
  <div class="pa4 code">
    hi {{user.id}}, you've been user since {{user.created | timeSince}}
  </div>
</template>

<script>
import axios from "~/plugins/axios"

export default {
  async asyncData({route}) {
    const response = await axios.get(`user/${route.params.id}.json`)
    return { user: response.data }
  }
}
</script>
