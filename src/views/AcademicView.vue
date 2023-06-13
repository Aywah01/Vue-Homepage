<template>
  <div class="academic-page">
    <div class="academic-container">
      <h1>Academic</h1>
      <div class="section animated-section">
        <h2>About Me</h2>
        <p>My name is Rujhan, I am a passionate and dedicated academic with expertise in Full-Stack Developer.</p>
        <a href="Vue Project/Other/Rujhan_Resume.pdf" download="Rujhan_Resume.pdf">Download My Resume</a>
      </div>
      <div class="section animated-section">
        <h2>Education</h2>
        <p>
          <strong>Bachelor Degree in Computer Software</strong><br>
          Dongyang Mirae University, 2022-2025
        </p>
        <a href="https://www.dongyang.ac.kr/dongyang/index.do" target="_blank">Dongyang Mirae University</a>
        <p>
          <strong>Foundation Level in Science and Technology</strong><br>
          University of Kuala Lumpur MIIT, 2020-2021
        </p>
        <a href="https://miit.unikl.edu.my/" target="_blank">Univeristy of Kuala Lumpur MIIT</a>
        <p>
          <strong>Science Stream (High School)</strong><br>
          Brainy Bunch International Islamic School, 2016-2020
        </p>
        <a href="https://www.brainybunch.com/" target="_blank">Brainy Bunch</a>
      </div>
      <div class="section animated-section">
        <div class="research-interest">
          <h2>Research Interests</h2>
          <li><strong>Software Engineering:
          </strong> Studying and improving the process of software development, including methodologies, tools, and practices.</li><br>
          <li><strong>Software Testing and Quality Assurance:
          </strong> Investigating techniques for ensuring software quality, such as test automation, code coverage analysis, and defect detection.</li><br>
          <li><strong>Software Security and Privacy:
          </strong> Exploring methods for identifying and mitigating software vulnerabilities, ensuring data privacy, and securing software systems against threats.</li><br>
        </div>
      </div>
      <div class="section animated-section">
        <div class="publications">
          <h2>Publications</h2>
          <li><strong>Agile Software Development</strong></li><br>
          <li><strong>Software Testing and Quality Assurance</strong></li><br>
          <li><strong>Software Security</strong></li>
        </div>
      </div>
      <div class="section animated-section">
        <div class="goals">
          <h2>Goals</h2>
          <li><strong>Work in South Korea for a couple years</strong></li><br>
          <li><strong>Master in Front-end Devoloping</strong></li><br>
          <li><strong>To have a financially stable life</strong></li>
        </div>
      </div>
      <div class="section animated-section">
        <div class="goals">
          <h2>Technology and Design</h2>
          <li><strong>Technology:</strong> My aim to have a homepage that can be access to everyone, either at a young age or later. Other than that it can be my portfolio.
          I am using HTML, CSS, and Javascript(Vue).</li><br>
          <li><strong>Design and Layout:</strong> My design is a minimalist design. I used neutral colour as the main color, as it will make the homepage more welcoming.</li><br>
        </div>
      </div>
      <!-- Add more sections as needed -->
    </div>
  </div>
</template>

<style>
  body {
    font-family: Arial, sans-serif;
    margin: 0;
  }

  header {
    text-align: center;
    margin-bottom: 20px;
  }

  h1 {
    font-size: 40px;
    margin: 10px 0;
  }

  h2 {
    font-size: 24px;
    margin: 10px 0;
  }

  p {
    margin-bottom: 10px;
  }

  .section {
    margin-bottom: 30px;
    padding: 10px;
  }

  .animated-section {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.5s, transform 0.5s;
  }

  .animated-section.animate {
    opacity: 1;
    transform: translateY(0);
  }
</style>

<script>
export default {
  name: 'AcademicPage',
  mounted () {
    this.animateSections()
  },
  methods: {
    animateSections () {
      const sections = document.querySelectorAll('.animated-section')
      sections.forEach((section, index) => {
        setTimeout(() => {
          section.classList.add('animate')
        }, 200 * index)
      })
    }
  }
}
</script>
