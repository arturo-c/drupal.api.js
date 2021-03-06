The Drupal JavaScript API

This library acts as an object oriented JavaScript wrapper around the
Drupal services module ( http://drupal.org/project/services ).
This makes is extremely simple to work with Drupal services from within a web
application that uses JavaScript (JSON) for communication to the Drupal RESTful
server.

Examples:

  1.)  To create a new node.

      new drupal.node({title:"My new Node"}).save();

  2.)  To update an existing node.

      new drupal.node({nid:10}, function(node) {

        // Change title then save.
        node.title = "Change the Title";
        node.save();
      });

   3.) To get a list of nodes of type='page'

      new drupal.node({type:'page'}, function(nodes) {

        // This is a list of nodes of type 'page'.
        console.log(nodes);
      });

   4.) To delete a node on the server.

      new drupal.node({nid:10}).remove();

   5.) To connect to the drupal server.

      new drupal.system(function(system) {

        // The currently logged in user.
        console.log(system.user);
      });

   6.) To create a new user.

      new drupal.user({
        name:"travist":
        pass:"testing":
        mail:"travis@allplayers.com"
      }).save();

   7.) To load an existing user.

      new drupal.user({uid:10}, function(user) {

        // The logged in user.
        console.log(user);
      });

   8.) To delete a user.

      new drupal.user({uid:10}).remove();


   9.) To get a variable on Drupal.

      new drupal.system().get_variable("variable", "default", function(value) {

        // The value of the variable.
        console.log(value);
      });

  10.) To set a variable on Drupal.

      new drupal.system().set_variable("variable", "value", function() {

        console.log("done");
      });

  11.) To delete a variable on Drupal.

      new drupal.system().del_variable("variable", function() {

        console.log("done");
      });