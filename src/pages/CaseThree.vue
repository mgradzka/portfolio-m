<template>
 <ul class="breadcrumb flex">
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/case">Case studies</router-link></li>
      <li><router-link to="/case/case1">Task portal</router-link></li>
    </ul>
  <case-description>
    <template v-slot:info>
      <h2>{{ aboutCase.name }}</h2>
      <h4>Role</h4>
      <p>{{ aboutCase.role }}</p>

      <h4>Tools and technologies</h4>
      <p>{{ aboutCase.tools }}</p>

      <h4>Description</h4>
      <p>
        {{ aboutCase.description }}
      </p>

      <base-container id="here">
        <base-button
          ><a
            href="https://workout-app1.netlify.app/"
            target="_blank"
            class="btn btn--cases uppercase"
            >Demo</a
          ></base-button
        >

        <base-button
          ><a
            href="https://github.com/mgradzka/Workout-app"
            target="_blank"
            class="btn btn--cases uppercase"
            >Source code</a
          ></base-button
        >
      </base-container>
    </template>
    <template v-slot:img>
      <img
        src="../assets/workout-design.png"
        class="cases--img"
        alt="case study Martyna Grądzka"
      />
    </template>
  </case-description>

  <div v-if="scrollpx > 600" class="circle-scroll" @click="topFunction">
    <svg
      xmlns="http://www.w3.org/2000/svg"
      width="20"
      height="50"
      viewBox="0 0 17.119 29.65"
    >
      <g
        id="Group_157"
        data-name="Group 157"
        transform="translate(-1494.293 -1626.293)"
      >
        <g
          id="Group_156"
          data-name="Group 156"
          transform="translate(1195.917 1333.375)"
        >
          <line
            id="Line_99"
            data-name="Line 99"
            y2="28.524"
            transform="translate(306.913 294.043)"
            fill="none"
            stroke="#cf678d"
            stroke-miterlimit="10"
            stroke-width="2"
          />
          <line
            id="Line_100"
            data-name="Line 100"
            x2="8.176"
            y2="8.176"
            transform="translate(306.611 293.625)"
            fill="none"
            stroke="#cf678d"
            stroke-miterlimit="10"
            stroke-width="2"
          />
          <line
            id="Line_101"
            data-name="Line 101"
            x1="8.176"
            y2="8.176"
            transform="translate(299.083 293.625)"
            fill="none"
            stroke="#cf678d"
            stroke-miterlimit="10"
            stroke-width="2"
          />
        </g>
      </g>
    </svg>
  </div>

  <div class="tab-container flex">
    <button
      v-for="cat in category"
      :key="cat"
      :title="cat.title"
      :class="['tab', { tabActive: selectedTab === cat.name }]"
      @click="selectedTab = cat.name"
    >
      {{ cat.title }}
    </button>
    <!-- <button
      @click="setSelectedTab('caseone-diagram')"
      :class="tabSelected"
      class="uppercase tab"
      data-tab="1"
    >
      ER Diagram
    </button>
    <button
      @click="setSelectedTab('caseone-database')"
      class="uppercase tab"
      :class="tabSelected"
      data-tab="2"
    >
      Database
    </button>
    <button class="uppercase tab" data-tab="3">Backend</button>
    <button class="uppercase tab" data-tab="4">Frontend</button> -->
  </div>
  <!-- <caseone-diagram v-if="selectedTab === 'caseone-diagram'"></caseone-diagram>
  <caseone-database
    v-if="selectedTab === 'caseone-database'"
  ></caseone-database> -->
  <component :is="selectedTab" @scroll="scrolling"></component>
</template>

<script>
import CaseDescription from "../components/Case-studies/CaseDescription.vue";
import CaseAdd from "../components/Case-studies/Case-three/CaseAdd.vue";
import CaseDelete from "../components/Case-studies/Case-three/CaseDelete.vue";
import CaseStructure from "../components/Case-studies/Case-three/CaseStructure.vue";

export default {
  components: {
    CaseDescription,
    CaseAdd,
    CaseDelete,
    CaseStructure,
  },
  provide() {
    return {
      category: this.category,
    };
  },
  methods: {
    scrolling() {},

    topFunction() {
      const target = document.querySelector("#here");
      target.scrollIntoView(true);
    },

    handleScroll() {
      this.scrollpx = window.scrollY;
    },
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  unmounted() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  data() {
    return {
      scrollpx: 0,
      selectedTab: "case-structure",
      // tabs: ["caseone-diagram", "caseone-database"],
      category: [
        {
          name: "case-structure",
          title: "Structure",
          headings: ["Setup and style Guide", "Folder Structure", "Components & Data"],
          description: {
            one: "The project starts with setting up the environment for the project.  The goal is to build an application where users can switch between two tabs – one with existing workouts, and another one where there's an option to add new ones. For that, there is a need to create components. Throughout developing this app I am trying to use Vue style guide, by for example using naming convention for base- or single-instance components.",
            two: "In the components folder the files are moved into subfolders to make it easier to work and keep it organized.  Single instance components are kept in the UI folder, components which are used more than once are kept in a layout folder. The rest of components, which are directly connected with adding/viewing workouts, are in the workouts folder.",
            three: "The components that are being used more than once are registered globally in the main.js file. Other ones are registered locally in for example parent components.",
            four: "PanelWorkout is the core component which includes the switching tabs – “Your workouts” and “Add workouts”, and components corresponding with them.",
            five: "To switch between tabs, a default active template is set in the data property. Each of the tabs has an event listener method handler that changes the active template to the one we clicked at.  A component tag is used to render the right template dynamically."
        },


          images: { one: "vuesetup.png", two: "vuesetup2.png" },
        },
        {
          name: "case-add",
          title: "Add workout",
          headings: ["Submitting the form & Adding a workout", "Displaying the data"],
          description: {
            one: "AddWorkout is a component where the form is created. In order to fetch a user input, ref attributes are used. When the form is submitted, the entered values are acquired through refs.",
            two: "Also, in the parent component, PanelWorkout, the submitData method is created to add a new workout object to the array. The function is passed to the child component by using provide and inject, where entered values are set as parameters.",
            three: "To display existing workouts, a v-for loop is put in action. The props are declared in order to pass the data to the child component and render it with a help of interpolation"
          },

          images: {
            one: "vueform.png",

            two: "vueform2.png",

          },
        },
        {
          name: "case-delete",
          title: "Delete",
          headings: [
            "Deleting the workout",
            "Class and style binging",
            "What could be further improved?"
          ],
          description: {
            one: "To delete a workout, a function deleteWorkout is created in the PanelWorkout component. The function takes workout i'd as a parameter. To find the workout that should be deleted from the array, findIndex method is used. Then, using the splice method removes the desired object from the workouts array and simultaneously deletes the workout from the UI.",

            two: "The function is passed to the child object, and used as an event listener while clicking the delete button.",
            three:
              "To distinguish between delete button and other buttons, Vue’s style bindings are put in action. Switching buttons as well as submit button has a lime background color, but I decided to use a transparent  class for the delete button, as the user has to be rather more cautious with its function. In a BaseButton component, a dynamic class “mode” is set and used as props. Then, in the parent component which has a delete button, “mode” is displayed and the transparent class is used.",
           four: "The project could be of course further developed and polished. Right now, a user can delete workouts or add new ones, but once the app is reloaded or the web-app is closed, the changes aren’t saved – the app goes back to the default stage. It could be improved by connecting to the database, for instance Firebase. In this case, when a user submits the data through form, a http POST request should be sent to the server. To display or delete the data, a GET and DELETE methods should be used respectively. Thanks to that, the data would not be lost after closing or refreshing the page."
          },

          images: {
            one: "vuedelete.png",

            two: "vueclass.png",
          },
        },
   
      ],
      aboutCase: {
        name: "Workout Noter",
        role: "Frontend Stack Developer",
        tools: "Vue.js",
        description:
          "A project created in order to practice working with Vue CLI and dynamic components. It is a workout noter that helps to keep track of the trainings users have had so far. Also, with an option for adding new ones as well as deleting  the existing ones.",
        
      },
    };
  },
  // methods: {
  //   setSelectedTab(tab) {
  //     this.selectedTab = tab;
  //   },
  // },
  computed: {
    tabSelected() {
      return { tabActive: this.selectedTab };
    },
    // beVisible() {
    //   if (
    //     document.body.scrollTop > 700 ||
    //     document.documentElement.scrollTop > 700
    //   ) {
    //     return tabActive: selectedTab === tab.name
    //   } else {
    //     return (btnUp.style.display = "none");
    //   }
    // },
  },
};
</script>

<style scoped>
button {
  background-color: var(--bluedark);
}

button:hover {
  background-color: rgb(37, 115, 160);
}

.btn--cases {
  color: white;
}

p,
h2 {
  margin-bottom: 3rem;
}

div {
  justify-content: left
}
</style>
