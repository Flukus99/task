<template>
  <v-container fluid>
    <v-row class="row">
      <v-col cols="16" md="4">
        <div class="tarjeta">
          <h1>STAGGIN</h1>
          <v-card v-for="card in list1" :key="card.id" elevation="2">
            <h1>{{ card.nameTask }}</h1>
            <h3>{{ card.responsible }}</h3>
            <div class="d-flex jussfy-between">
              <h3>sagging</h3>
              <v-btn
                depressed
                color="primary"
                v-on:click="moveRight(card, list1)"
              >
                siguiente
              </v-btn>
            </div>
          </v-card>
        </div>
      </v-col>
      <v-col cols="12" md="4">
        <div class="tarjeta">
          <H1>WORKING</H1>
          <v-card v-for="card in list2" :key="card.id" elevation="2">
            <h1>{{ card.nameTask }}</h1>
            <h3>{{ card.responsible }}</h3>
            <div class="d-flex jussfy-between">
              <h3>sagging</h3>
              <v-btn
                depressed
                color="primary"
                v-on:click="moveLeft(card, list2)"
              >
                atras
              </v-btn>
              <v-btn
                depressed
                color="primary"
                v-on:click="moveRight(card, list2)"
              >
                siguiente
              </v-btn>
            </div>
          </v-card>
        </div>
      </v-col>
      <v-col cols="12" md="4">
        <div class="tarjeta">
          <H1>END</H1>
          <v-card v-for="card in list3" :key="card.id" elevation="2">
            <h1>{{ card.nameTask }}</h1>
            <h3>{{ card.responsible }}</h3>
            <div class="d-flex jussfy-between">
              <h3>sagging</h3>
              <v-btn
                depressed
                color="primary"
                v-on:click="moveLeft(card, list3)"
              >
                atras
              </v-btn>
            </div>
          </v-card>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "tasksList",

  data() {
    return {
      list1: [
        { id: 1, nameTask: "actualizar", responsible: "ivan" },
        { id: 2, nameTask: "borrar", responsible: "ivan" },
      ],
      list2: [],
      list3: [],
      moveRight(item, list) {
        let indexList = list.indexOf(item);
        if (list == this.list1) {
          this.list2.push(item);
          list = list.splice(indexList, 1);
          console.log(this.list1, this.list2);
        } else {
          this.list3.push(item);
          list = list.splice(indexList, 1);
          console.log(this.list1, this.list2);
        }
      },
      moveLeft(item, list) {
        let indexList = list.indexOf(item);
        this.list1.push(item);
        list = list.splice(indexList, 1);
        console.log(this.list1, this.list2);
      },
    };
  },
};
</script>

<style>
.row {
  height: 100vh;
}
.tarjeta {
  height: 100%;
  width: 100%;
  background-color: aliceblue;
}
</style>
