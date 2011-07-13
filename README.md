# Agility.js
Agility.js is Javascript MVC for the *write less, do more* programmer. 

Main site: http://arturadib.github.com/agility

Agility lets you write **maintainable** browser code without compromising on **productivity**. Write fully functional apps in fewer lines, like this minimal To-Do app (17 lines):

    var item = $$({}, '<li><span data-bind="content"/> <button>x</button></li>', '& span { cursor:pointer; }', {
      'click span': function(){
        var input = prompt('Edit to-do item:', this.model.get('content'));
        if (!input) return;
        this.model.set({content:input});
      },
      'click button': function(){
        this.destroy();
      }
    });
    var list = $$({}, '<div> <button id="new">New item</button> <ul></ul> </div>', {
      'click #new': function(){
        var newItem = $$(item, {content:'Click to edit'});
        this.add(newItem, 'ul'); // add to container, appending at <ul>
      }
    })    
    $$.document.add(list);

Curious to learn more? Visit: http://arturadib.github.com/agility or fork ahead and contribute code!
