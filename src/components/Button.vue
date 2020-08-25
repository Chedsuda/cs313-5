<template>
  <div>
    <button @click="randomStart()" class="btn btn-danger">
      Start{{ randomNO }}
    </button>
    <div class="row">
      <div class="col-12">
        <button @click="randomDamage()" class="btn btn-success ">
          Attack{{ randomNO }}
        </button>
        <button @click="randomSpDamage()" class="btn btn-success ml-3">
          Special Attack{{ randomNO }}
        </button>
      </div>
    </div>

    <p v-if="hp1 <= -1">
      <img
        src="https://www.uokpl.rs/fpng/f/2-25278_iconos-lol-png.png"
        height="700"
        width="900"
      />
    </p>
    <p v-else-if="hp2 <= -1">
      <img
        src="https://www.pikpng.com/pngl/b/296-2965935_lol-of-league-of-legends-riot-legends-victory.png"
        height="500"
        width="500"
      />
    </p>

    <div class="row">
      <div class="col-4 ">
        <p>{{ randomPlayer }}</p>
        <p>HP : {{ hp1 }}</p>
        <img :src="image1" />
      </div>

      <div class="col-4">
        <br /><br /><br /><br />
        <img
          src="http://www.pngmart.com/files/11/Versus-Battle-Transparent-PNG.png"
          height="300"
          width="400"
        />
      </div>

      <div class="col-4">
        <p>{{ randomMonster }}</p>
        <p>HP : {{ hp2 }}</p>
        <img :src="image2" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      randomPlayerAttack: "",
      randomMonsterAttack: "",
      randomSpAttack: "",
      image1: "",
      image2: "",
      hp1: " ",
      hp2: " ",

      player: [
        { name: "Uchiha Sasuke", hp: 220, image: "./images/Uchiha.png" },
        { name: "Roy Mustang", hp: 180, image: "./images/Roy.png" },
        { name: "Kakashi", hp: 200, image: "./images/Kakashi.png" },
        { name: "Naruto", hp: 190, image: "./images/Naruto.png" },
      ],
      randomPlayer: "",

      //ค่าพลังของ ตัวละคร เข้าถึงโดย player[1].hp -= 20
      monster: [
        { name: "Majin Buu", hp: 250, image: "./images/Tigrex.png" },
        { name: "Estrellian", hp: 220, image: "./images/Estrellian.png" },
        { name: "Duremudira", hp: 210, image: "./images/Duremudira.png" },
        { name: "Garuba Daora", hp: 200, image: "./images/Garuba Daora.png" },
      ],
      randomMonster: "",
    };
  },
  props: {
    randomNO: String,
  },
  methods: {
    randomStart: function() {
      var chosenNumber1 = Math.floor(Math.random() * this.player.length);
      this.randomPlayer = this.player[chosenNumber1].name;
      this.hp1 = this.player[chosenNumber1].hp;
      this.image1 = this.player[chosenNumber1].image;
      var chosenNumber2 = Math.floor(Math.random() * this.monster.length);
      this.randomMonster = this.monster[chosenNumber2].name;
      this.hp2 = this.monster[chosenNumber2].hp;
      this.image2 = this.monster[chosenNumber2].image;
    },
    randomDamage: function() {
      this.randomPlayerAttack = Math.max(Math.floor(Math.random() * 10) + 1, 3);
      this.hp2 -= this.randomPlayerAttack;
      this.randomMonsterAttack = Math.max(
        Math.floor(Math.random() * 15) + 1,
        5
      );
      this.hp1 -= this.randomMonsterAttack;
    },
    randomSpDamage: function() {
      this.randomPlayerAttack = Math.max(
        Math.floor(Math.random() * 20) + 1,
        10
      );
      this.hp2 -= this.randomPlayerAttack;
      this.randomMonsterAttack = Math.max(
        Math.floor(Math.random() * 15) + 1,
        5
      );
      this.hp1 -= this.randomMonsterAttack;
    },
  },
};
</script>

<style></style>
