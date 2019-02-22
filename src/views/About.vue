<template>
  <div class="about">
    <h1>About</h1>
    <p>
      This is a sample application for COSC 4351. It's purpose is to 
      demonstrate how a UML MVC Class Diagram Model can serve as a roadmap 
      when building out a DVD Application used to catalog DVDs.
    </p>

    <p>
      On Load the application will restore a preset Catalog. All DVDs belonging 
      to this collection will be displayed. Title, Category, Runtime, Year, and 
      Price are the attributes associated with each DVD. Users can also Add and 
      Delete DVDs.
    </p>

    <p>
      The UML to Class Diagram Model assignment did not ask for other methods, 
      so at the moment that is all a user can do. If needed, this application 
      can easily be extended to include:
    </p>
    <ul>
      <li>editDVD</li>
      <li>listDVDsForCategory</li>
      <li>listDVDsByYear</li>
    </ul>

    <p>
      Another addition would be to add an actual database. At the moment 
      the data exist as part of the application and will reset on reload. All 
      that is needed to connect a database is to include a URL endpoint for
      the Catalog Methods to target when changes are to be made.
    </p>

    <p>
      This application was generated with the help of Vue.js
      The source code is located on my github account <a href="https://github.com/lelopez-io/dvd-catalog" target="_blank">here.</a> 
    </p>
  </div>
</template>


<style>
.about h1 {
  text-align: center;
}

.about p {
  max-width: 80%;
  margin: 1em 10%;
}

.about ul {
  margin-left: 1em;
}
</style>
