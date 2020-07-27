# JSON

<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>JSON Sandbox</title>
</head>
<body>
<ul id="people"></ul>
<script>
/*
var person = {
name: "Balde",
age: 30,
address:{
street:"5 main st",
city: "Boston"
},
children:["Briana", "Nicholas"]
}

//person = JSON.stringify(person);
//person = JSON.parse(person),

var people = [
{
name:"balde",
age:30
},
{
name:"John",
age:40
},
{
name:"Sara",
age:25
}
];


//console.log(people[1].age);
var output = '';

for(var i = 0;i < people.length;i++){
//console.log(people[i].age);
output += '<li>'+people[i].name+'</li>'
}
document.getElementById('people').innerHTML = output;
*/

var xhttp = new XMLHttpRequest();
xhttp.onreadystatechange = function() {
   if (this.readyState == 4 && this.status == 200) {
      // Typical action to be performed when the document is ready:
      //document.getElementById("demo").innerHTML = xhttp.responseText;

      var response = JSON.parse(xhttp.responseText);
      var people = response.people;

      var output = '';

for(var i = 0;i < people.length;i++){
output += '<li>'+people[i].name+'</li>'
}
document.getElementById('people').innerHTML = output;
   }
};
xhttp.open("GET", "people.json", true);
xhttp.send();


</script>
</body>
</html>
