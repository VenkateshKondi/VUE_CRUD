<script setup lang="ts">
 import UserService from '@/services/UserService.ts'
import { ref } from "@vue/reactivity"
import { onMounted } from "vue";
let users = ref([])


function getAllUsers() {
  this.users = UserService.getData()
  
}


function deleteItem(i){
  if(confirm('Do you want to delete this user?')){
      this.users.splice(i-1,1);
    }
}
</script>

 <template>
  <!-- <prep>{{users}}</prep> -->
  <button class="btn btn-info m-2" @click="getAllUsers()">READ</button>
  <div class="container-fluid"  v-if="users!=0">
    <div class="row">
      <div class="col-12">
        <table class="table lg-shadow mt-1">
          <thead>
            <tr style="text-align: center">
              <th>ID</th>
              <th>NAME</th>
              <th>SHORT NAME</th>
              <th>MAIL-ID</th>
              <th></th>
              <th></th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="user in users" :key="user.id">
              <td class="text-center align-middle">{{ user.id }}</td>
              <td class="text-center align-middle">{{ user.name }}</td>
              <td class="text-center align-middle">{{ user.shortName }}</td>
              <td class="text-center align-middle">{{ user.mail }}</td>
              <td class="text-center align-middle">
              
                <router-link :to="{name:'edit',params:{id:user.id}}">  <button type="button" class="btn btn-outline-primary btn-rounded">
                  Edit
                </button></router-link>
              </td>
              <td class="text-center align-middle">
                <button type="button" class="btn btn-outline-danger" @click="deleteItem(user.id)">
                  Del 
                </button>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
  
</template>
