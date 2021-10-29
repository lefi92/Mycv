<template>
  <div class="hello">
   <header>
    <div>
      <img src="../assets/photo.jpg" />
    </div>
    <h1>{{Nom}} - {{Prenom}}</h1>
    <section>
      <p>Bonjour bande de pute. Alors C'est 80k ou rien</p>
      <a href="https://github.com/lefi92" target="_blank">
            <img src="../assets/github.svg"/>
      </a>
      <a href="https://www.linkedin.com/in/denis-boudret/" target="_blank">
            <img src="../assets/lk.svg"/>
      </a>
    </section>
  </header>
  <main>
    <section>
      <h3>Formations</h3>
      <article v-for="item in ecoles" :key="item" >
        <div class='school'>
          <span>{{item.date}}</span> <strong>{{item.ecole}}</strong>
        </div>
        <div class="descrition">
          {{item.diplome}}
        </div>
      </article>
    </section>
    <section>
      <h3>Experience</h3>
      <article v-for="item in experience" :key="item">
        <div  class='job-title'>
          <span>{{item.datedebut}} - {{item.datefin}}</span> <strong>{{item.entreprise}}</strong><br> {{item.poste}}
        </div>
        <div>
          <p><strong>Techno: </strong><span v-for ="tec in item.technos" :key="tec" class="tech"> {{tec.techno }} </span></p>
          <ul class="job-description">
            <li v-for="task in item.taches" :key="task">{{task.tache}}</li>
          </ul>
        </div>
      </article>
    </section>
     <section>
      <h3>Compétences</h3>
      <div class='skills'>
        <div class='column'>
            <div class="skill-bars">
                <div class="bar" v-for="item in compétences.slice(0, 7)" :key="item">
                <div class="info">
                    <span>{{item.techno}}</span>
                </div>
                <div class="progress-line ">
                    <span v-bind:style="{width: item.level +'%'}"></span>
                </div>
                </div>
            </div>
        </div>
        <div class='column'>
            <div class="skill-bars">
                <div class="bar" v-for="item in compétences.slice(7, 13)" :key="item">
                <div class="info">
                    <span>{{item.techno}}</span>
                </div>
                <div class="progress-line ">
                    <span v-bind:style="{width: item.level +'%' }" v-bind:after="{conten:item.level}"></span>
                </div>
                </div>
            </div>
        </div>
        <div class='column'>
          <h4>Outils</h4>
          <ul>
               <li v-for="item in outils" :key="item">{{item.outil}}</li>
          </ul>
        </div>
        <div>
          <div class='column'>
          <h4>Langues</h4>
          <ul>
            <li v-for="item in langue" :key="item.message">
                {{ item.message }}
            </li>
         </ul>
         </div>
        </div>
      </div>
    </section>
  </main>
  <footer>
    <p>Created by: <a href="https://github.com/lefi92">Denis Boudret</a>  / <a href="https://www.linkedin.com/in/denis-boudret/">LinkedIn</a> / 2021 </p>
  </footer>
  </div>
</template>

<script>
export default {
  name: 'Cv',
  props: {
    msg: String
  },
  data() {
      return {
          Prenom: "Denis",
          Nom: "Boudret",
          
          langue : [
            {message:  "Français"},
            {message:  "Anglais"},
            {message:  "Espagnol"},
        ],
        experience : [
            {entreprise: "C'est Nettement Mieux", datedebut: "Janvier 2018", datefin: "Novembre 2020", poste: "Développeur web", taches:[
                {tache:"Refonte Template de site e-commerce"},
                {tache:"Développement de sites vitrines pour clients"},
                {tache:"Développement de nouvelles fonctionnalités application zend"},
                {tache:"Développement plateforme de gestion de comptes fidélité connecté aux caisses magasin et site e-commerce"},
                {tache:"Développement module Wordpress et Prestashop"},
            ],technos: [
                {techno:"Php"},
                {techno:"HTML"},
                {techno:"Css "},
                {techno:"Sass"},
                {techno:"JavaScript"},
                {techno:"Jquery"},
                {techno:"Zend-Framwork"},
                {techno:"Wordpress"},
                {techno:"Prestashop"},
                {techno:"Boostrap"},

            ]},
            {entreprise: "Ekyss", datedebut: "Avri 2017", datefin: "Juillet 2017", poste:"Stage développeur Web", taches:[
                {tache:"Développement d'un CRM en interne."},
                {tache:"Developpement d'application web"},
            ],technos: [
                {techno:"Php"},
                {techno:"HTML"},
                {techno:"Css"},
                {techno:"JavaScript"},
                {techno:"Jquery"},
                {techno:"Laravel"},
                {techno:"Boostrap"}
            ]}
        ],
        ecoles : [ 
            {ecole:"Etna", diplome:"Master 2 - CYCLE D'INGENIERIE ARCHITECTE LOGICIEL DEVELOPPEUR D'APPLICATIONS", date:"2020"},
            {ecole:"Etna", diplome:"Bachelor Informatique", date:"2018"}, 
            {ecole:"IUT Orsay", diplome:"DUT Informatique", date:"2017"},
            {ecole:"Lycée Georges Brassens", diplome:"Baccalauréat Scientifique Science de L'ingénieur", date:"2015"},
        ],
        compétences: [
                {techno:"Php", level:"80"},
                {techno:"HTML", level:"75"},
                {techno:"Css", level:"75"},
                {techno:"Sass", level:"70"},
                {techno:"Boostrap", level:"75"},
                {techno:"JavaScript", level:"70"},
                {techno:"Jquery", level:"70"},
                {techno:"Zend-Framwork", level:"80"},
                {techno:"Wordpress", level:"80"},
                {techno:"Prestashop", level:"75"},
                {techno:"Laravel", level:"65"},
                {techno:"Nodejs", level:"70"},
                {techno:"Vuejs", level:"60"},
        ],
        outils: [
            {outil:"GIT"},
            {outil:"SVN"},
            {outil:"REDMINE"},
            {outil:"Trello"},
            {outil:"PHPSTORM"},
            {outil:"VS CODE"},
            {outil:"LINUX"},
            {outil:"Windows"},
            {outil:"Postman"}
        ],
        skillcolor : '#f44336'


      }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://fonts.googleapis.com/css?family=Raleway');

body {
  margin: 0;
  font-family: 'Raleway';
  font-size: 16px;
  line-height: 1.8em;
}

a {
  color: #1C9C94;
  text-decoration: none;
}

a:hover {
  opacity: 0.5;
}

article {
  padding:0 1em;
}

section{
  margin: 1em;
  padding: 1em;
}

header, main, footer {
  margin: 0 auto;
}

header {
  padding: 2em;
  text-align: center;
  background-image: url('../assets/bg.jpg');
  background-size: cover;
  background-position: fixed;
  color: white;
}

header section {
  margin: 0 auto;
  max-width: 640px;
}

header img {
  border-radius: 50%;
  max-width: 150px;
}
span.tech{margin-right:10px}
h1 {
  text-transform: uppercase;
  margin: 1em 0;
}

h3 {
  text-transform: uppercase;
}

h3, h4 {
  font-weight: bold;
}

main {
  max-width: 1200px;
}

main section:not(:last-child) {
  border-bottom: 1px solid #ccc;
}

.fab {
  border: 1px solid white;
  border-radius: 50%;
  font-size: 1.5em;
  width: 1.5em;
  height: 1.5em;
  line-height: 1.5em;
  margin: 5px;
  text-align: center;
}

a .fab {
  color: white;
}

.course, .skills {
  display: -ms-flexbox;
  display: flex;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
}

.course .title {
  color: #509e98;
  -ms-flex: 0 0 33.3%;
  flex: 0 0 33.3%;
  max-width: 33%;
}

.course .descrition {
  -ms-flex: 0 0 66.6%;
  flex: 0 0 66.6%;
  max-width: 66.6%;
}

.course .descrition p {
  padding-left: 1em;
}

.skills .column {
  -ms-flex: 0 0 50%;
  flex: 0 0 50%;
  max-width: 50%;
}

.skills .column ul, ul.job-description {
  list-style-type: none;
}

.skills .column ul > li:before {
  content: "►";
  padding-right: 0.5em;
  color: #509e98;
}

.school, .job-title {
  text-transform: capitalize;
}

.school span, .job-title span {
  color: #889499;
  text-decoration: underline;
}

ul.job-description li:before{
  content: "✔";
  padding-right: 0.5em;
  color: #509e98;
}

footer {
 padding: 1em 1.5em;
 background: #A7B8BF;
 color: white;
 text-align: right;
}

@media only screen and (max-width: 768px) {
  .course {
    display: block;
  }

  .course .title, .course .descrition {
    max-width: 100%;
  }
}

@media only screen and (max-width: 576px) {
  .skills {
    display: block;
  }

  .skills .column {
    max-width: 100%;
  }

  footer {
    text-align: center;
  }
}
* {box-sizing:border-box}

/* Container for skill bars */
.container {
  width: 100%; /* Full width */
  background-color: red; /* Grey background */
}

.toto {
  text-align: right; /* Right-align text */
  padding-top: 10px; /* Add top padding */
  padding-bottom: 10px; /* Add bottom padding */
  color: red; /* White text color */
}
::selection{
  color: #fff;
  background: #6665ee;
}
.skill-bars{
  padding: 25px 30px;
  background: #fff;
  box-shadow: 5px 5px 20px rgba(0,0,0,0.2);
  border-radius: 10px;
  text-align: left;
  margin: 2%;
}
.skill-bars .bar{
  margin: 20px 0;
}
.skill-bars .bar:first-child{
  margin-top: 0px;
}
.skill-bars .bar .info{
  margin-bottom: 5px;
}
.skill-bars .bar .info span{
  font-weight: 500;
  font-size: 17px;
  opacity: 0;
  animation: showText 0.5s 1s linear forwards;
}
@keyframes showText {
  100%{
    opacity: 1;
  }
}
.skill-bars .bar .progress-line{
  height: 10px;
  width: 100%;
  background: #f0f0f0;
  position: relative;
  transform: scaleX(0);
  transform-origin: left;
  border-radius: 10px;
  box-shadow: inset 0 1px 1px rgba(0,0,0,0.05),
              0 1px rgba(255,255,255,0.8);
  animation: animate 1s cubic-bezier(1,0,0.5,1) forwards;
}
@keyframes animate {
  100%{
    transform: scaleX(1);
  }
}
.bar .progress-line span{
  height: 100%;
  position: absolute;
  border-radius: 10px;
  transform: scaleX(0);
  transform-origin: left;
  background: #6665ee;
  animation: animate 1s 1s cubic-bezier(1,0,0.5,1) forwards;
}
.bar .progress-line.html span{
  width: 90%;
}
.bar .progress-line.css span{
  width: 60%;
}
.bar .progress-line.jquery span{
  width: 85%;
}
.bar .progress-line.python span{
  width: 50%;
}
.bar .progress-line.mysql span{
  width: 75%;
}
.progress-line span::before{
  position: absolute;
  content: "";
  top: -10px;
  right: 0;
  height: 0;
  width: 0;
  border: 7px solid transparent;
  border-bottom-width: 0px;
  border-right-width: 0px;
  border-top-color: #000;
  opacity: 0;
  animation: showText2 0.5s 1.5s linear forwards;
}
.progress-line span::after{
  position: absolute;
  top: -28px;
  right: 0;
  font-weight: 500;
  background: #000;
  color: #fff;
  padding: 1px 8px;
  font-size: 12px;
  border-radius: 3px;
  opacity: 0;
  animation: showText2 0.5s 1.5s linear forwards;
}
@keyframes showText2 {
  100%{
    opacity: 1;
  }
}

.progress-line.css span::after{
  content: "60%";
}
.progress-line.jquery span::after{
  content: "85%";
}
.progress-line.python span::after{
  content: "50%";
}
.progress-line.mysql span::after{
  content: "75%";
}
</style>
