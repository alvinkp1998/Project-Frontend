<template>
  <div>
    <div class="container">
      <h3 class="text-center">Skill Test Front End</h3>
      <div class="row mt-5">
        <div class="col-md-5">
          <div id="list-programmer">
            <h4>PROGRAMMER</h4>
            <div
              class="input-group mb-3"
              v-for="item in listProgrammer"
              :key="item.id"
            >
              <list-programmer :nama="item.nama" />
              <!-- <div class="input-group-text" id="list1">
                <input
                  type="checkbox"
                  aria-label="Checkbox for following text input"
                />
                <input
                  type="text"
                  class="form-control disabled"
                  aria-label="Text input with checkbox"
                  :value="item.nama"
                />
              </div> -->
            </div>
          </div>
        </div>
        <div class="col-md-2 mt-5">
          <button class="btn btn-primary btn-block" @click="toAnalyst">
            Kanan
          </button>
          <button class="btn btn-primary btn-block" @click="toProgrammer">
            Kiri
          </button>
        </div>
        <div class="col-md-5">
          <div id="list-analyst">
            <h4>ANALYST</h4>
            <div
              class="input-group mb-3"
              v-for="item in listAnalyst"
              :key="item.id"
            >
              <list-analyst :nama="item.nama" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      semuaList: [
        { id: "1", nama: "Ghany Abdillah Ersa", posisi: "kiri" },
        { id: "2", nama: "Jihadul Akbar", posisi: "kanan" },
        { id: "3", nama: "Allyvio Yonim Mahardika", posisi: "kanan" },
        { id: "4", nama: "Fajri Rahman", posisi: "kanan" }
      ]
    };
  },
  methods: {
    // toAnalyst() {
    //   let list = $("#list-programmer:checkbox:checked").length > 0;
    //   if (list) {
    //     $("#list1").appendChild($("#list-analyst"));
    //   }
    // },
    // toProgrammer() {
    //   let list = $("#list-analyst:checkbox:checked").length > 0;
    //   if (list) {
    //     $("#list1").appendChild($("#list-programmer"));
    //   }
    // },
    toAnalyst() {
      this.semuaList = this.listAnalyst.filter(item => {
        if (item.checked) {
          item.posisi = "kanan";
          return item;
        }
      });
    },
    toProgrammer() {
      this.semuaList = this.listProgrammer.filter(item => {
        if (item.checked) {
          item.posisi = "kiri";
          return item;
        }
      });
    }
  },
  computed: {
    //filter list programmer
    listProgrammer() {
      return this.semuaList.filter(list => list.posisi === "kiri");
    },
    //filter list analyst
    listAnalyst() {
      return this.semuaList.filter(list => list.posisi === "kanan");
    }
  }
};
</script>
