 'use strict';

 var mongoose=require('mongoose');
 var User=require('../models/user');

 mongoose.connect('mongodb://localhost/bookStore');

 // Exports all the functions to perform on the db
 module.exports = {getAllUser:getAllUser, addUser, getUserById, updateUser, deleteUser};

 //GET /user operationId 
 function getAllUser(req, res, next) {
  User.find({}, function(err, users) {
    if (err) throw err;
    res.header("Access-Control-Allow-Origin", "*");
    res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
    res.json(users);
  }); 
}

 //POST /user operationId
 function addUser(req, res, next) {
  var newUser=req.body;
  User.create(newUser,function(err){
  if(err) throw err;
  console.log("insertion valide");
  res.header("Access-Control-Allow-Origin", "*");
  res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
  res.json(newUser);
});
}

 //GET /user/{id} operationId
 function getUserById(req, res) {

  var id = req.swagger.params.id.value; //req.swagger contains the path parameters
  var user = User.find(id);
  if(user) {
    res.header("Access-Control-Allow-Origin", "*");
    res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
    res.json(user); 
  }else {
    res.status(204).send();
  }       */
  res.json("hello");
}

 //PUT /user/{id} operationId
 function updateUser(req, res, next) {
 var id = req.swagger.params.id.value; //req.swagger contains the path parameters
 var user = req.body;
 if(db.update(id, user)){
  console.log("user updated");
  res.json({success: 1, description: "User updated!"});
 }else{
  res.status(204).send();
}}
    
 //DELETE /user/{id} operationId
 function deleteUser(req, res, next) {
 var id = req.swagger.params.id.value; //req.swagger contains the path parameters
 if(User.remove(id)){
  console.log("user deleted");
  res.json({success: 1, description: "User deleted!"});
}else{
  res.status(204).send();
}
}
