# polymer-tinymce

A tinymce HTML Editor as an Polymer Element.

# Fork notes

The fork makes it easier to work with events (change), and supports multiple
instances of the editor on the same page.

## Supported events:

* init
* focus
* change

( fixed events 'this' scope )

## change event:

change event receives the new html content ( see demo page for example )

## Support for multiple instances

Each text area will have a unique id, to avoid conflicts with other instances

```
<polymer-tinymce id="editor"
	  	tinytoolbar="insertfile undo redo | styleselect | bold italic | alignleft aligncenter alignright alignjustify | bullist numlist outdent indent | link image" 
	  	tinyplugins='["advlist autolink lists link image charmap print preview anchor","searchreplace visualblocks code fullscreen","insertdatetime media table contextmenu paste"]'
></polymer-tinymce>
```

Get and set content:

```
<script>
    Polymer({

        is: "demo-element",

        getContent:function(){
        	this.$.contentInput.value = this.$.editor.getContent();
        },

        setContent:function(){
        	this.$.editor.setContent(this.$.contentInput.value);
        }

      });
</script>
```

![Demo Pic](http://www.synappses.com/wp-content/uploads/2015/06/tinymceDemo.png "Polymer-Tinymce")