# fix-meteor-rel

If you've got multiple Meteor projects implemented with different versions of meteor, you may have encountered problems when changing between them, especially if some are using pre 1.3.3 and others are using post 1.3.3 versions of Meteor.

A good example would occur when you create a new project using Meteor 1.3.4.1, then download meteor/todos and go run 'meteor npm install' in the meteor/todos app. You'll find that your NPM modules were installed with NPM 3.9.6, the Meteor 1.3.4.1 version of NPM. However, the meteor/todos app is a Meteor 1.3 app at this time and uses NPM 2.14.22. This can cause subtle and not so subtle development problems.

If you use fix-meteor-rel to run the commands instead of meteor, it will make sure that the ~/.meteor/meteor symlink points to the correct release bundle for your project's current Meteor release version before invoking meteor. Meteor will then be invoked with the parameters that you've passed in.

A big weakness of this script at the moment is that **it requires sqlite3 and jq to be installed**. 

I'd advise placing fix-meteor-rel in /usr/local/bin beside the existing meteor script. Don't forget to make it executable (chmod +x).
