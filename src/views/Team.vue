<template>
  <div class="container">

    <div class="row">

      <!-- /.col-lg-3 -->

      <div class="col">

        <div class="card mt-4">
          <div class="card-body">
            <h3 class="card-title">Nos équipes ! </h3>
            <div class="card" >
              <ul class="list-group list-group-flush text-center">
                <div v-for="group in localRecipientsGroup" :key="group.id">
                    <li class="list-group-item" >L'équipe {{group.title}}  {{group.icon}}
                        <a @click="detailsGroup(group.id)" class="btn btn-secondary btn-sm" role="button">Voir</a>
                    </li>
                </div>
              </ul>
            </div>
          </div>
        </div>
        <!-- /.card -->


        <!-- /.card -->

      </div>
      <!-- /.col-lg-9 -->

    </div>

  </div>
</template>

<script>
import {recipientsGroup} from "@/assets/js/recipientsGroup"

export default {
  name: 'Team',
  components: {
    
  },
  data:()=>({
    localRecipientsGroup:recipientsGroup
  }),
  methods:{
    detailsGroup(groupId){
      this.$router.push({
        name:'OneTeam',
        params:{
          groupId:groupId
        }
      });
      console.log(`on va ouvrir le groupe ${groupId} ☕`)
    }
  }
}
</script>
