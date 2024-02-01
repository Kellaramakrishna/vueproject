<template>
  <div class="app-container">
    <Header />
    <h1 class="title">Projects</h1>
    <p class="description">
      Your skills and achievements showcase your strengths and abilities. Speak
      about any new skills or software you learnt to perform the project
      responsibilities.
    </p>

    <ul class="tabs-container">
      <TabItem
        v-for="tabDetails in tabsList"
        :key="tabDetails.tabId"
        :tabDetails="tabDetails"
        :clickTabItem="clickTabItem"
        :isActive="activeTabId === tabDetails.tabId"
      />
    </ul>

    <ul class="project-list-container">
      <ProjectItem
        v-for="projectDetails in filteredProjects"
        :key="projectDetails.projectId"
        :projectDetails="projectDetails"
      />
    </ul>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import TabItem from "./components/TabItem.vue";
import ProjectItem from "./components/ProjectItem.vue";

export default {
  data() {
    return {
      tabsList: [
        { tabId: "STATIC", displayText: "Static" },
        { tabId: "RESPONSIVE", displayText: "Responsive" },
        { tabId: "DYNAMIC", displayText: "Dynamic" },
      ],
      activeTabId: "",
      projectsList: [
        {
          projectId: 0,
          category: "STATIC",
          imageURL:
            "https://assets.ccbp.in/frontend/react-js/projects-s3-img.png",
          title: "Music Page",
          description:
            "The music page enables the users to browse through the images of all-time favorite music albums.",
        },
        {
          projectId: 1,
          category: "STATIC",
          imageURL:
            "https://assets.ccbp.in/frontend/react-js/projects-s4-img.png",
          title: "Tourism Website",
          description:
            "A tourism website enables the user to browse through the images of popular destinations.",
        },
        {
          projectId: 2,
          category: "STATIC",
          imageURL:
            "https://assets.ccbp.in/frontend/react-js/projects-s1-img.png",
          title: "Advanced Technologies",
          description:
            "A website that gives you a basic understanding of Advanced Technologies.",
        },
        {
          projectId: 3,
          category: "STATIC",
          imageURL:
            "https://assets.ccbp.in/frontend/react-js/projects-s2-img.png",
          title: "Happy Meals",
          description: "Discover the best foods in over 1,000 restaurants.",
        },
        {
          projectId: 4,
          category: "RESPONSIVE",
          imageURL:
            "https://assets.ccbp.in/frontend/react-js/projects-r4-img.png",
          title: "VR Website",
          description:
            "VR Website enables users to explore AR and VR Products and Industry happenings.",
        },
        {
          projectId: 5,
          category: "RESPONSIVE",
          imageURL:
            "https://assets.ccbp.in/frontend/react-js/projects-r2-img.png",
          title: "Food Munch",
          description: "Food Much Website is a user-centric food tech website.",
        },
        {
          projectId: 6,
          category: "RESPONSIVE",
          imageURL:
            "https://assets.ccbp.in/frontend/react-js/projects-r3-img.png",
          title: "Portfolio",
          description:
            "A portfolio is the best alternative for a resume to showcase your skills to the digital world.",
        },
        {
          projectId: 7,
          category: "RESPONSIVE",
          imageURL:
            "https://assets.ccbp.in/frontend/react-js/projects-r1-img.png",
          title: "Design",
          description:
            "A website to showcase the best features and give more information about the Design tool.",
        },
        {
          projectId: 8,
          category: "DYNAMIC",
          imageURL:
            "https://assets.ccbp.in/frontend/react-js/projects-d3-img.png",
          title: "Speed Typing Test",
          description:
            "Speed Typing Test Application is capable of calculating the time to type the randomly generated quote.",
        },
        {
          projectId: 9,
          category: "DYNAMIC",
          imageURL:
            "https://assets.ccbp.in/frontend/react-js/projects-d1-img.png",
          title: "Random Joke Page",
          description:
            "Random Joke Page is an API-based dynamic Web Application that generates a new joke.",
        },
        {
          projectId: 10,
          category: "DYNAMIC",
          imageURL:
            "https://assets.ccbp.in/frontend/react-js/projects-d2-img.png",
          title: "Sizing An Image",
          description:
            "This is a dynamic web application capable of adjusting the size of an element using DOM manipulations.",
        },
      ],
    };
  },
  methods: {
    clickTabItem(tabValue) {
      this.activeTabId = tabValue;
    },
    getFilteredProjects() {
      return this.projectsList.filter(
        (projectDetails) => projectDetails.category === this.activeTabId
      );
    },
  },
  computed: {
    // It automatically updates when the dependent properties change.
    filteredProjects() {
      return this.getFilteredProjects();
    },
  },
  components: {
    Header,
    TabItem,
    ProjectItem,
  },
  created() {
    // Set the initial value of activeTabId here
    // it is similar to componentDidMount method and called when instance is created
    this.activeTabId = this.tabsList[0].tabId;
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
html {
  overflow-x: hidden;
}

.app-container {
  max-width: 1110px;
  margin: auto;
}

.title {
  font-family: "Roboto";
  font-weight: 500;
  font-size: 24px;
  line-height: 56px;
  color: #3e4c59;
  text-align: center;
  margin-top: 12px;
  margin-bottom: 0;
}

@media screen and (min-width: 992px) {
  .title {
    font-size: 48px;
    margin-top: 48px;
    margin-bottom: 24px;
  }
}

.description {
  max-width: 300px;
  font-family: "Roboto";
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  color: #616e7c;
  margin: auto;
  margin-bottom: 40px;
}

@media screen and (min-width: 992px) {
  .description {
    max-width: 730px;
    font-size: 18px;
    line-height: 28px;
  }
}

.tabs-container {
  max-width: 300px;
  margin: auto;
  list-style-type: none;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  padding: 0;
}

@media screen and (min-width: 992px) {
  .tabs-container {
    max-width: 455px;
  }
}

.project-list-container {
  padding: 0;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin-top: 12px;
  margin-bottom: 50px;
}

@media screen and (min-width: 992px) {
  .project-list-container {
    margin-bottom: 150px;
  }
}
</style>
