### How the Model View Controller Works

Over the last 20 years, websistes have changed from simple pages with a little CSS to become much more complex and powerfull application.

to make these applications aeasier to develop, programmers use some partherns of architecture to make the code less complicated.

### ![](C:\Users\oscar\AppData\Roaming\marktext\images\2022-08-12-22-25-52-image.png)

### ¿what is software architecture?

An architecture is a systematic way in which software is describe, It also refers to how they interact with other software.

Software architecture also uncludes other factors such as businnes strategy, quality attributes, human dynamics, desgn, and IT environment.

Overview an architecture serves as a **blueprint for a system**-ante proyecto de un sistema.

### Model View Controller (MVC) Architecture

The most popular software architecture, by far, is the Model-View-Controller or MVC.

MVC divides any large application into three parts:

1.-The Model

2.-The View

3.-The Controller

Each of thes components is built to handle a specific aspect of an application and has diferent purposes.

-cada uno maneja aspectos especificos de una aplicacion y tiene diferentes propositos.

#### The Model

The model contains all the data-related logic that the user works with, like the schemas and interfaces of a project, the databases, and their fields.

For example, a customer object. will retrieve-recuperar the customer information 
from the database, manipulate or update their record-registro in the database, or
use it to render-representar data.

#### The View

The view contains the UI and the presentation of an application.

For example, the customer view will include all the UI components such as text boxes, dropdowns-listas_desplegables, and other things that the user interacts with.

#### The controller

And finally, the controller contains all the business-related logic and handles-maneja incoming-llegantes requests-solicitudes. It is the interface between the Model and the View.

For example, the customer controller will handle all the intercations and inputs from the customer view and update the databases using customer model. The same controller will be used to view the customer data.

### How MVC Architecture works

Firts, the browser sends a request to the controller. Then, the controller interacts with the model to send and recevie data.

-El navegador envía solicitudes al controlador., el controlador interactuará con el modelo para enviar y recibir datos.

The controller then interacts with the View to render-presentar the data. The view is only concerned about how to present the information and no the final presentation.

it will be a dynamic HTML file that renders data based on what the controller sends it-sera un archivo html dinamico que representa datos en funcion de lo que le envia el controlador.

Finally, the view will send its final presentation to the controller and the controller will send that final data to the user output.

The important thing is that the view and the model never interact with each other. The only interaction that takes place between them is trough the controller.

EXAMPLE:

![](C:\Users\oscar\AppData\Roaming\marktext\images\2022-08-13-19-46-14-image.png)

First, a user inputs that they want a list of movies through a web browser or a mobile application.

The browser will send the request to the controller to get the list of movies.

Next, the controller to get the list of movies from model it will ask to find the list of movies.

```javascript
 router.get('/',ensureAuth, async (req,res)=>{ 
	try{ 
		const movies = await Movies.find() (*) 
		res.render('movies/index',{ movies }) 
    } 
    
	catch(err){ console.error(err) 
		res.render('error/500') } })
 
 /*The Controller sending request to ask for Movie List(Line number *)‌*/
 
```

/** Then the model searches the database and returns the list of movies
     to the controller*/

this way the database(model) responsive the search requets

```scheme
const mongoose  require('mongoose') 
const MovieSchema = new mongoose.Schema
({ 
	name:{ 
        type:String, 
        required:true 
    }, 
	description:{ 
    	type:String 
    } 
}) 

module.exports = mongoose.model('Movies',MovieSchema)

//**Movies Model Schema.


```

                                                    

If the Controller gets the list of movies from the Model, the Controller will ask the View to present the list of movies.

```js
router.get('/',ensureAuth, async (req,res)=>{ 
	try{ const movies = await Movies.find() 
		res.render('movies/index', { movies (*) }) } 

	catch(err){ 
    console.error(err) res.render('error/500') }
})


/*The Controller sending the Movie list to View to Render
 the list of movies(Line number *)*/
```

Then the View will receive the request and returns the rendered list of movies to the Controller in HTML.

```html
<div class="col" style="<margin-top:20px;padding-bottom:20px">
    <div class="ui fluid card"> 
        <div class="content"> 
        <div class="header">{{movie.title}}</div> 
        	</div> <div class="extra content"> 
            <a href="/movies/{{movie._id}}" class="ui blue button"> More from {{movie.description}} </a> 
        </div> 
    </div>
</div>
//The View Returning List of Movies in form of HTML.


```



Lastly, the Controller will take that HTML and return it back to the user, thus getting the list of Movies as the output.

## Wrapping Up-Terminando

There are a lot of software architectures out there, but 
Model-View-Controller is the most popular and widely used. It reduces 
the code complexity and makes the software easily understandable.

That’s all folks! Happy Learning
