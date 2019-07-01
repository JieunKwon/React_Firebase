# React & Firebase

> What is Firebase?

https://firebase.google.com/products


Firebase is <b> a mobile and web application development platform</b> developed by Firebase, Inc. in 2011, then acquired by Google in 2014. 
 
Firebase provides

- Authentication

- Cloud Firestore (NoSQL)

- Realtime Database (Firebase's original database)

- Storage

- Hosting

- Funcions

- ML Kit 



> Add Firebase to JavaScript project

https://firebase.google.com/docs/web/setup


Step 1: Create a Firebase project

Step 2: Register your app

Step 3: Add Firebase SDKs and initialize Firebase

Step 4: (Optional) Install CLI and deploy to Firebase Hosting

Step 5: Access Firebase in your app

- Additional setup options

https://firebase.google.com/docs/web/setup#additional_setup_options


> Simple Firebase Test


- by using script source link into head tag

      <script src="https://www.gstatic.com/firebasejs/5.0.4/firebase.js"></script>

- After body tag, add script tag with firebase initialization information
 
      <script>
        // Initialize Firebase
        var config = {
          apiKey: "------------account api key firebase provided-----------",
          authDomain: "fbboard-753cc.firebaseapp.com",
          databaseURL: "https://fbboard-753cc.firebaseio.com",
          projectId: "fbboard-753cc",
          storageBucket: "",
          messagingSenderId: "453984329008",
          appId: "1:453984329008:web:467d53c1491d58e2"
        };
        firebase.initializeApp(config);

- To create new data, make a variance and use update method

        var newPostKey = firebase.database().ref().child('posts').push().key;

        var postData = {
        brdno: newPostKey,
        brdwriter: "Julia",
        brdtitle: "Test Data", 
        brdmemo: "Data created:" + newPostKey, 
        brddate: Date.now()
        };

        var updates = {};
        updates['/board/' + newPostKey] = postData;

        firebase.database().ref().update(updates);

      </script>
      
- View the result at the firebase database 

<img src="img/firebasetest.JPG" width="500px">
