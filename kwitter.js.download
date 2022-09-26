function addUser() {
    user_name = document.getElementById("user_name").value;

    localStorage.setItem("Username",user_name);

    window.location = "kwitter_room.html";
}
const firebaseConfig = {
    apiKey: "AIzaSyCC4OWvdyqo97D36bTJXwPUHVtd0n8DNvI",
    authDomain: "classtest-97db2.firebaseapp.com",
    databaseURL: "https://classtest-97db2-default-rtdb.firebaseio.com",
    projectId: "classtest-97db2",
    storageBucket: "classtest-97db2.appspot.com",
    messagingSenderId: "129873944014",
    appId: "1:129873944014:web:9999743260f848758cdf9f",
    measurementId: "G-T9S4LBT1WG"
  };
  // Initialize Firebase
  firebase.initializeApp(firebaseConfig);

  user_name = localStorage.getItem("Username");
  document.getElementById("welcome_user_name").innerHTML = "Welcome "+user_name+"!";

  function addroom() {
         room_name = document.getElementById("room_name").value;

         firebase.database().ref("/").child(room_name).update({
              purpose: "Adding Room Name"
        });

        localStorage.setItem("Roomname",room_name);
    
        window.location = "kwitter_page.html";
  }

function getData() {firebase.database().ref("/").on('value', function(snapshot) {document.getElementById("output").innerHTML = "";snapshot.forEach(function(childSnapshot) {childKey  = childSnapshot.key;
   Room_names = childKey;
  //Start code
        console.log("room_name - " + Room_names);
        row = "<div class='room_name' id="+Room_names+" onclick='redirectToroomname(this.id)'>#"+Room_names+"</div><hr>";
        document.getElementById("output").innerHTML += row;
  //End code
  });});}
getData();
function redirectToroomname(name){
  console.log(name);
  localStorage.setItem("Roomname",name);
  window.location = "kwitter_page.html";
}
function logout() {
  localStorage.removeItem("Username");
  localStorage.removeItem("Roomname");
  window.location = "index.html";
}