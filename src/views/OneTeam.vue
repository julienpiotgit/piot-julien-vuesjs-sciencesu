<template>
  <div class="container">

    <div class="row">

 

      <div class="col">
        <div class="card mt-4">
          <div class="card-body">
            <h3 class="card-title">Oh la belle équipe de {{currentGroup.title}} </h3>
            <h5 class="card-title">Composée de {{currentRecipient.length}} membres</h5>

                <div v-for="group in currentRecipient" :key="group.id" class="media mb-2" >
                  <img class="mr-3 rounded" style='height:120px' :src="group.avatar" alt="Generic placeholder image">
                  <div class="media-body">
                    <h5 class="mt-0">{{group.firstName}} {{group.lastName}}</h5>
                    <span class="badge badge-info">{{group.email}}</span>
                  </div>
                </div>

          </div>
        </div>

      </div>
      

    </div>

  </div>
</template>

<script>
import {recipientsGroup} from "@/assets/js/recipientsGroup"

export default {
  name: 'OneTeam',
  components: {
    
  },
  data:()=>({
    localRecipientsGroup:recipientsGroup,
    currentGroup:{},
    currentRecipient:{}
  }),
  created(){
      this.currentGroup = this.localRecipientsGroup.find(caf=>caf.id==this.$route.params.groupId);
      this.currentRecipient = this.currentGroup.recipients
      // this.countPerson = this.currentGroup.reduce((acc, obj) => obj.recipients+acc,0)
      console.log(this.currentRecipient.length)
  }
}
</script>
