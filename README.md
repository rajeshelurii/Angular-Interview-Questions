**Angular Interview Quetions**
1. ### What is Angular?

   **Angular** is a platform and framework for building client-side applications using HTML, CSS, and JavaScript/TypeScript. Angular is developed and maintained by Google and is widely used for building single-page applications 
   (SPAs). It is built entirely using typescript.

   **Key Features:**
   - **Component-Based Architecture**: Everything in Angular is a component.
   - **Data Binding**: Synchronizes data between the model and the view.
   - **Dependency Injection**: Efficiently manages service dependencies.
   - **Directives**: Extend HTML with custom attributes and functionality.
   - **Routing**: Manages navigation between views.
   - **RxJS**: Reactive Extensions for JavaScript for asynchronous programming using observables.
 

2. ### What is the difference between AngularJS and Angular?
    Angular is a completely re-written version of angular js using type script. It follows component based architecture.

    Some of the major differences are:-

	| AngularJS | Angular |
	|-----------|---------|
	| It is based on the MVC architecture. | It is based on a component-based architecture. |
	| It uses JavaScript to build applications. | It uses TypeScript to build applications. |
	| It is based on the controllers concept. | It uses a component-based UI approach. |
	| It has limited support for mobile platforms. | It fully supports mobile platforms. |
	| It is difficult to build SEO-friendly applications. | It is easier to build SEO-friendly applications. |


3. ### Write a pictorial diagram of Angular architecture?

	The main building blocks of an Angular application are shown in the diagram below:
	
	1. **Angular App**: The root of the application.
	2. **App Module (NgModule)**: The main module that bootstraps the application. It includes:
	   - **Components**: Building blocks of the UI.
	   - **Directives**: Custom attributes that enhance the functionality of HTML elements.
	   - **Pipes**: Transform data in templates.
	   - **Services**: Provide reusable logic, such as data retrieval.
	3. **Root Component**: The main entry component serving as the starting point.
	4. **Templates and Style Files**: HTML and CSS files associated with components.
	5. **Component Logic**: TypeScript classes containing data and behavior for the component.
	6. **Services & Dependency Injection**: 
	   - **Services**: Injectable classes for business logic and data management.
	   - **Dependency Injection**: Mechanism to inject services into components and other services.
	7. **Component Tree**: Structure of components within the application:
	   - **Parent Component**
	   - **Child Components**
	8. **Routing**: 
	   - **Router Module**: Manages navigation and routing within the application.
	   - **Routes**: Define the paths and components associated with each route.
	9. **HTTP Client Module**: Handles HTTP requests and communication with backend services.
	10. **Forms and Reactive Forms Module**: Manages forms, form controls, and form validation.
	11. **Data Flow**: Mechanisms for data binding in Angular:
	    - **Interpolation**: Binding data from the component to the template.
	    - **Property Binding**: Binding component properties to HTML elements.
	    - **Event Binding**: Binding events from the template to the component.
	    - **Two-way Binding**: Binding data in both directions (component to template and template to component).
	12. **State Management (e.g., NgRx)**: Manages application state in a predictable and scalable way, especially for complex applications.


4. ### Define angular Project Structure

	When you create a new Angular project, the following structure is generated:

	```
	my-angular-app/
	├── e2e/                     // End-to-end tests
	├── node_modules/            // Project dependencies
	├── src/                     // Source code
	│   ├── app/                 // App components, modules, and services
	│   ├── assets/              // Static assets
	│   ├── environments/        // Environment-specific configurations
	│   ├── index.html           // Main HTML file
	│   ├── main.ts              // Main entry point for the application
	│   ├── polyfills.ts         // Polyfills for browser compatibility
	│   ├── styles.css           // Global styles
	│   └── test.ts              // Test configuration
	├── .editorconfig            // Editor configuration
	├── .gitignore               // Git ignore file
	├── angular.json             // Angular CLI configuration
	├── package.json             // NPM dependencies and scripts
	├── README.md                // Project documentation
	├── tsconfig.app.json        // TypeScript configuration for the app
	├── tsconfig.json            // TypeScript configuration
	└── tsconfig.spec.json       // TypeScript configuration for tests
	```
 
5. ### What are the key components of Angular?
    Angular has the key components below,
    1. **Component:** These are the basic building blocks of an Angular application to control HTML views.
    2. **Modules:** An Angular module is a set of angular basic building blocks like components, directives, services etc. An application is divided into logical pieces and each piece of code is called as "module" which perform a single task.
    3. **Templates:** These represent the views of an Angular application.
    4. **Services:** Are used to create components which can be shared across the entire application.
  
6. ### What are directives?
    Directives are special markers on a DOM element that tell Angular to do something with that element and its children.

	**Types of Directives**
	
	1. **Component Directives**: Component directive is meta data that is defined using the @Component decorator.
	2. **Structural Directives**: Change the DOM layout by adding or removing elements (`*ngIf`, `*ngFor`).
	3. **Attribute Directives**: Change the appearance or behavior of an element (e.g., `ngClass`, `ngStyle`).
	
	**Example: Structural Directive**
	
	Using `*ngIf`:
	```html
	<p *ngIf="isVisible">This text is conditionally visible.</p>
	```
	
	Using `*ngFor`:
	```html
	<ul>
	  <li *ngFor="let item of items">{{ item }}</li>
	</ul>
	```
	
	**Example: Attribute Directive**
	
	Using `ngClass`:
	```html
	<div [ngClass]="{ 'active': isActive }">Toggle class based on condition</div>
	```
	---
  
7. ### What are components?
    Components are the building blocks of Angular applications. Each component consists of:
	- **A TypeScript class** that handles data and logic.
	- **An HTML template** that defines the view.
	- **CSS styles** that define the look and feel.
	
	**Creating a Component**
	
	Use the Angular CLI to generate a new component:
	```bash
	ng generate component my-component
	```
	
	This command will create four files:
	- `my-component.component.ts`: The component class.
	- `my-component.component.html`: The component template.
	- `my-component.component.css`: The component styles.
	- `my-component.component.spec.ts`: The component test file.
	
	**Example: Simple Component**
	
	`src/app/my-component/my-component.component.ts`:
	```typescript
	import { Component } from '@angular/core';
	
	@Component({
	  selector: 'app-my-component',
	  templateUrl: './my-component.component.html',
	  styleUrls: ['./my-component.component.css']
	})
	export class MyComponent {
	  title = 'Hello Angular!';
	}
	```
	
	`src/app/my-component/my-component.component.html`:
	```html
	<h1>{{ title }}</h1>
	```
	
	Add the component to the main app template:
	`src/app/app.component.html`:
	```html
	<app-my-component></app-my-component>
	```
	
	---  

8. ### What are the differences between Component and Directive?

	In short, a component (`@Component`) is essentially a directive with a template.
	
	Some of the major differences are mentioned in the table below:
	
	| **Component** | **Directive** |
	|---------------|---------------|
	| To register a component, we use the `@Component` decorator. | To register a directive, we use the `@Directive` decorator. |
	| Components are typically used to create UI widgets. | Directives are used to add behavior to an existing DOM element. |
	| Components are used to break down the application into smaller, reusable pieces. | Directives are used to design reusable behaviors that can be applied to DOM 	elements. |
	| Only one component can be present per DOM element. | Many directives can be used per DOM element. |
	| Components require a `@View` decorator or template/templateUrl. | Directives do not use a view or template. |


  

9. ### What is a template?
    A template is a HTML view where you can display data by binding controls to properties of an Angular component. You can store your component's template in one of two places. You can define it inline using the template property, or you can define the template in a separate HTML file and link to it in the component metadata using the @Component decorator's templateUrl property.

    **Using inline template with template syntax,**
    ```typescript
    import { Component } from '@angular/core';

    @Component ({
       selector: 'my-app',
       template: '
          <div>
             <h1>{{title}}</h1>
             <div>Learn Angular</div>
          </div>
       '
    })

    export class AppComponent {
       title: string = 'Hello World';
    }
    ```
    **Using separate template file such as app.component.html**
    ```typescript
    import { Component } from '@angular/core';

    @Component ({
       selector: 'my-app',
       templateUrl: 'app/app.component.html'
    })

    export class AppComponent {
       title: string = 'Hello World';
    }
    ```

  

10. ### What is a module?

    Modules are used to group related components, directives, services, etc., into functional units. Every Angular app has at least one module, the root module, which is defined in `app.module.ts`.

	**Example: App Module**
	
	`src/app/app.module.ts`:
	```typescript
	import { NgModule } from '@angular/core';
	import { BrowserModule } from '@angular/platform-browser';
	import { AppComponent } from './app.component';
	import { MyComponent } from './my-component/my-component.component';
	
	@NgModule({
	  declarations: [
	    AppComponent,
	    MyComponent
	  ],
	  imports: [
	    BrowserModule
	  ],
	  providers: [],
	  bootstrap: [AppComponent]
	})
	export class AppModule { }
	```
    The NgModule decorator has five important (among all) options:
    1. The imports option is used to import other dependent modules. The BrowserModule is required by default for any web based angular application.
    2. The declarations option is used to define components in the respective module.
    3. The bootstrap option tells Angular which Component to bootstrap in the application.
    4. The providers option is used to configure a set of injectable objects that are available in the injector of this module.
    5. The entryComponents option is a set of components dynamically loaded into the view.

  

11. ### :warning: What are lifecycle hooks available?
    Angular application goes through an entire set of processes or has a lifecycle right from its initiation to the end of the application.
    Constructor is the first method triggered when component is started and ngOnChanges is the first lifecycle hook.

    ![ScreenShot](images/lifecycle.png)

    1. **`ngOnChanges`**: Called when an input property (data-bound property) changes. It lets you react to changes in the input data.
	   **When to use**: You want to respond to changes in input properties.
	2. **`ngOnInit`**: Called once after the component/directive is initialized. This is where you set up initial data or perform setup tasks.
	   **When to use**: You need to initialize properties or make API calls after the component has been set up.
	3. **`ngDoCheck`**: Called during every change detection cycle. This is where you can check for changes Angular doesn’t detect automatically.
	   **When to use**: You need to manually check for changes that Angular might miss.
	4. **`ngAfterContentInit`**: Called after Angular projects content into the component (e.g., content inside `<ng-content>`). 
	   **When to use**: You need to perform actions after the content is projected into the component.
	5. **`ngAfterContentChecked`**: Called after Angular checks the projected content for changes.
	   **When to use**: You need to act on changes or perform tasks after Angular checks the projected content.
	6. **`ngAfterViewInit`**: Called after Angular initializes the component’s view and child views (e.g., `<app-child>` components).
	   **When to use**: You need to perform tasks that require the component’s view and child views to be fully initialized.
	7. **`ngAfterViewChecked`**: Called after Angular checks the component’s view and child views for changes.
	   **When to use**: You need to perform actions after Angular checks the views for changes.
	8. **`ngOnDestroy`**: Called just before Angular destroys the component/directive. This is where you clean up resources like subscriptions or timers.
	   **When to use**: You need to clean up resources to avoid memory leaks before the component is destroyed.


  

12. ### What is a data binding?
    Data binding is a core concept in Angular and allows to define communication between a component and the DOM, making it very easy to define interactive applications without worrying about pushing and pulling data.
    Angular supports four types of data binding:

	1. **Interpolation**: Binding data from the component to the template.
	    ```html
	    <p>{{ title }}</p>
	    ```
	
	2. **Property Binding**: Binding a property of a DOM element to a field in the component.
	    ```html
	    <img [src]="imageUrl">
	    ```
	
	3. **Event Binding**: Binding an event (like a click) to a method in the component.
	    ```html
	    <button (click)="handleClick()">Click me</button>
	    ```
	
	4. **Two-Way Binding**: Binding a property to a form element and updating the property when the form element's value changes.
	    ```html
	    <input [(ngModel)]="name">
	    <p>Hello, {{ name }}!</p>
	    ```  

13. ### What is metadata?
    Metadata is used to decorate a class so that it can configure the expected behavior of the class. The metadata is represented by decorators
    1. **Class decorators**, e.g. @Component and @NgModule
        ```typescript
        import { NgModule, Component } from '@angular/core';

        @Component({
          selector: 'my-component',
          template: '<div>Class decorator</div>',
        })
        export class MyComponent {
          constructor() {
            console.log('Hey I am a component!');
          }
        }

        @NgModule({
          imports: [],
          declarations: [],
        })
        export class MyModule {
          constructor() {
            console.log('Hey I am a module!');
          }
        }
        ```
    2. **Property decorators** Used for properties inside classes, e.g. @Input and @Output
        ```typescript
        import { Component, Input } from '@angular/core';

        @Component({
            selector: 'my-component',
            template: '<div>Property decorator</div>'
        })

        export class MyComponent {
            @Input()
            title: string;
        }
        ```
    3. **Method decorators** Used for methods inside classes, e.g. @HostListener
        ```typescript
        import { Component, HostListener } from '@angular/core';

        @Component({
            selector: 'my-component',
            template: '<div>Method decorator</div>'
        })
        export class MyComponent {
            @HostListener('click', ['$event'])
            onHostClick(event: Event) {
                // clicked, `event` available
            }
        }
        ```

        - **@HostListener**: This decorator is used to listen to events on the host element of the component. It allows you to handle specific events within the component without needing to add event listeners in the template. 	For example, it can be used to listen to click events directly on the host element.
    
    4. **Parameter decorators** Used for parameters inside class constructors, e.g. @Inject, @Optional
        ```typescript
        import { Component, Inject } from '@angular/core';
        import { MyService } from './my-service';

        @Component({
            selector: 'my-component',
            template: '<div>Parameter decorator</div>'
        })
        export class MyComponent {
            constructor(@Inject(MyService) myService) {
                console.log(myService); // MyService
            }
        }
        ```

	- **@Inject**: This decorator is used for injecting dependencies in Angular. It tells Angular which dependency to inject into the constructor of a class. This is particularly useful when you want to provide a custom token or when you need to inject something that isn't a class.

14. ### What is angular CLI?

	The Angular CLI (Command Line Interface) is a tool that helps developers create, manage, and build Angular applications efficiently.
	
	**Key Features:**
	
	1. **Project Setup and Initialization:**
	   - **Create New Projects:** Use `ng new project-name` to generate a new Angular project.
	   - **Generate Code:** Use commands like `ng generate component component-name` to create components, services, and more.
	
	2. **Development Server:**
	   - **Live Reload:** Use `ng serve` to start a development server with live reload for automatic updates when code changes.
	
	3. **Building and Bundling:**
	   - **Production Builds:** Use `ng build --prod` for optimized production builds with AOT compilation, minification, and tree shaking.
	
	4. **Testing:**
	   - **Unit Testing:** Use `ng test` for running unit tests.
	   - **E2E Testing:** Use `ng e2e` for end-to-end tests.
	
	5. **Updating Projects:**
	   - **Upgrade Dependencies:** Use `ng update` to update Angular and CLI dependencies.

  
15. ### What is the difference between constructor and ngOnInit?

	In Angular, both the constructor and the `ngOnInit` lifecycle hook are used to initialize a component, but they serve different purposes and are used in different contexts. Here's a concise comparison:
	
	**Constructor:**
	- **Purpose:** The constructor is a standard TypeScript feature used to initialize class members and inject dependencies.
	- **Timing:** Called when the class is instantiated, before Angular initializes the component's inputs and before any lifecycle hooks.
	- **Usage:** Avoid complex logic or interacting with Angular properties that rely on inputs or other lifecycle events.
	
	**ngOnInit:**
	- **Purpose:** `ngOnInit` is a lifecycle hook provided by Angular, specifically for component initialization tasks that require Angular's bindings to be set.
	- **Timing:** Called by Angular after the constructor and after Angular has initialized all data-bound properties of a directive.
	- **Usage:** Safe to interact with component inputs and properties that rely on bindings. Suitable for complex initialization tasks, such as fetching data or setting up the component's initial state.

	```typescript
	import { Component, OnInit } from '@angular/core';
	import { MyService } from './my-service';
	
	@Component({
	  selector: 'app-example',
	  template: '<p>Example component</p>',
	})
	export class AppComponent implements OnInit {
	  constructor(private myService: MyService) {
	    // Called first, before ngOnInit
	    // Initialize service or set default values
	  }
	
	  ngOnInit() {
	    // Called after the constructor and after data-bound properties are initialized
	    // Perform initialization that depends on Angular bindings, such as HTTP calls
	    this.myService.getData().subscribe(data => {
	      console.log('Data fetched:', data);
	    });
	  }
	}
	```

16. ### What is a service?
    In Angular, a service is a class that provides reusable functionalities that can be shared across different components of an application. Services are typically used to encapsulate business logic, interact with external APIs, perform data manipulation, or handle any other operations that need to be centralized and reused.

	**Key Characteristics of a Service:**
	
	1. **Encapsulation of Logic:**
	   - Services encapsulate business logic, making it easier to maintain and test.
	   - They help keep components focused on presentation logic.
	
	2. **Reusability:**
	   - Services can be reused across multiple components, promoting DRY (Don't Repeat Yourself) principles.
	
	3. **Dependency Injection:**
	   - Angular uses dependency injection (DI) to provide instances of services to components or other services.
	   - This makes it easy to manage dependencies and improves testability.
	
	4. **Separation of Concerns:**
	   - Services help in separating concerns by moving logic that doesn't belong in the component into a separate class.
	
	**Using Angular CLI:**
	```bash
	ng generate service my-service
	```
	
	```typescript
	import { Injectable } from '@angular/core';
	
	@Injectable({
	  providedIn: 'root'
	})
	export class MyService {
	  constructor() { }
	
	  getData() {
	    return 'Some data';
	  }
	}
	```
	
	- The `@Injectable` decorator marks the class as a service that can be injected.
	- `providedIn: 'root'` registers the service at the root level, making it a singleton and available throughout the application.
  

17. ### What is dependency injection in Angular?
    Dependency injection (DI), is an important application design pattern in which a class asks for dependencies from external sources rather than creating them itself. Angular comes with its own dependency injection framework for resolving dependencies( services or objects that a class needs to perform its function).So you can have your services depend on other services throughout your application.

  

18. ### How is Dependency Hierarchy formed?
	In Angular, the dependency hierarchy defines how services and dependencies are provided and injected within the application. Angular's dependency injection (DI) system allows you to define providers at different levels of the application. These levels form a hierarchy that determines how and where instances of services are shared and reused.

	1. **Root Level (Application-wide) Providers:**
	   - **@Injectable({ providedIn: 'root' })**: When you configure a service to be provided in the root, Angular creates a single instance of the service that is shared across the entire application.
	   - **providers array in AppModule**: You can also register services in the providers array of the `AppModule`. This method also creates a singleton service available application-wide.
	
	   ```typescript
	   @Injectable({
	     providedIn: 'root'
	   })
	   export class MyService {
	     constructor() { }
	   }
	   ```
	
	   ```typescript
	   @NgModule({
	     providers: [MyService]
	   })
	   export class AppModule { }
	   ```
	
	2. **Feature Module Level Providers:**
	   - **providers array in a Feature Module**: When you register a service in the providers array of a feature module, Angular creates a new instance of the service that is shared among all the components, directives, and other services in that module.
   
	```typescript
	@Injectable()
	export class MyService {
	  constructor() { }
	}
	```
		   
	```typescript
	@NgModule({
	providers: [MyService]
	})
	export class FeatureModule { }
	```
	
	3. **Component Level Providers:**
	   - **providers array in a Component**: When you register a service in the providers array of a component, Angular creates a new instance of the service for that component and its children.

	```typescript
	@Injectable()
	export class MyService {
	    constructor() { }
	}
	```
	
	```typescript
	@Component({
	selector: 'app-my-component',
	providers: [MyService],
	templateUrl: './my-component.component.html'
	})
	export class MyComponent {
	constructor(private myService: MyService) { }
	}
	```
 
	Angular has two injector hierarchies: the **Module Injector** and the **Element Injector**. These two hierarchies play distinct roles in dependency injection and contribute to the flexibility and modularity of Angular applications.
	
	**Module Injector**
	The Module Injector is responsible for providing services at the module level. It is created when an Angular module is bootstrapped and can provide services to all components, directives, and other services that are declared within that module.
	
	**Element Injector**
	The Element Injector is responsible for providing services at the component and directive level. Each Angular component and directive has its own Element Injector, allowing for a more granular and localized provision of services.

19. ### :warning: What is the purpose of async pipe?
    The AsyncPipe subscribes to an observable or promise and returns the latest value it has emitted. When a new value is emitted, the pipe marks the component to be checked for changes.

    Let's take a time observable which continuously updates the view for every 2 seconds with the current time.
    ```typescript
    @Component({
      selector: 'async-observable-pipe',
      template: `<div><code>observable|async</code>:
           Time: {{ time | async }}</div>`
    })
    export class AsyncObservablePipeComponent {
      time: Observable<string>;
      constructor() {
        this.time = new Observable((observer) => {
          setInterval(() => {
            observer.next(new Date().toString());
          }, 2000);
        });
      }
    }
    ```

  

20. ### What is the option to choose between inline and external template file?
    You can store your component's template in one of two places. You can define it inline using the **template** property, or you can define the template in a separate HTML file and link to it in the component metadata using the **@Component** decorator's **templateUrl** property.

    The choice between inline and separate HTML is a matter of taste, circumstances, and organization policy. But normally we use inline template for small portion of code and external template file for bigger views. By default, the Angular CLI generates components with a template file. But you can override that with the below command,
    ```
    ng generate component hero -it
    ```

  

21. ### What is the purpose of `*ngFor` directive?
    We use Angular `*ngFor` directive in the template to display each item in the list. For example, here we can iterate over a list of users:
    ```html
    <li *ngFor="let user of users">
      {{ user }}
    </li>
    ```
    The user variable in the `*ngFor` double-quoted instruction is a **template input variable**.

  

22. ### What is the purpose of `*ngIf` directive?
    Sometimes an app needs to display a view or a portion of a view only under specific circumstances. The Angular `*ngIf` directive inserts or removes an element based on a truthy/falsy condition. Let's take an example to display a message if the user age is more than 18:
    ```html
    <p *ngIf="user.age > 18">You are not eligible for student pass!</p>
    ```
    **Note:** Angular isn't showing and hiding the message. It is adding and removing the paragraph element from the DOM. That improves performance, especially in the larger projects with many data bindings.

  

23. ### What happens if you use script tag inside template?

    Angular recognizes the value as unsafe and automatically sanitizes it, which removes the `script` tag but keeps safe content such as the text content of the `script` tag. This way it eliminates the risk of script injection attacks. If you still use it then it will be ignored and a warning appears in the browser console.

    Let's take an example of innerHtml property binding which causes XSS vulnerability,
    ```typescript
    export class InnerHtmlBindingComponent {
      // For example, a user/attacker-controlled value from a URL.
      htmlSnippet = 'Template <script>alert("0wned")</script> <b>Syntax</b>';
    }
    ```

  

24. ### What is interpolation?

    Interpolation is a special syntax that Angular converts into property binding. It’s a convenient alternative to property binding. It is represented by double curly braces({{}}). The text between the braces is often the name of a component property. Angular replaces that name with the string value of the corresponding component property.

    Let's take an example,
    ```html
    <h3>
      {{title}}
      <img src="{{url}}" style="height:30px">
    </h3>
    ```
    In the example above, Angular evaluates the title and url properties and fills in the blanks, first displaying a bold application title and then a URL.

  

25. ### What are template expressions?
    A template expression produces a value similar to any Javascript expression. Angular executes the expression and assigns it to a property of a binding target; the target might be an HTML element, a component, or a directive. In the property binding, a template expression appears in quotes to the right of the = symbol as in `[property]="expression"`.
    In interpolation syntax, the template expression is surrounded by double curly braces. For example, in the below interpolation, the template expression is `{{username}}`,

    ```html
    <h3>{{username}}, welcome to Angular</h3>
    ```

    The below javascript expressions are prohibited in template expression
    1. assignments (=, +=, -=, ...)
    2. new
    3. chaining expressions with ; or ,
    4. increment and decrement operators (++ and --)
    ----------------------------------

  

26. ### What are template statements?
    A template statement responds to an event raised by a binding target such as an element, component, or directive. The template statements appear in quotes to the right of the = symbol like `(event)="statement"`.

    Let's take an example of button click event's statement

    ```html
    <button (click)="editProfile()">Edit Profile</button>
    ```
    In the above expression, editProfile is a template statement. The below JavaScript syntax expressions are not allowed.
    1. new
    2. increment and decrement operators, ++ and --
    3. operator assignment, such as += and -=
    4. the bitwise operators | and &
    5. the template expression operators
    --------------------------------------

  

27. ### How do you categorize data binding types?

     Binding types can be grouped into three categories distinguished by the direction of data flow. They are listed as below,
     1. From the source-to-view
     2. From view-to-source
     3. View-to-source-to-view

     The possible binding syntax can be tabularized as below,

      | Data direction | Syntax | Type |
      |---- | --------- | ---- |
      | From the source-to-view(One-way)  | 1. {{expression}} 2. [target]="expression" 3. bind-target="expression" | Interpolation, Property, Attribute, Class, Style|
      | From view-to-source(One-way) | 1. (target)="statement" 2. on-target="statement" | Event |
      | View-to-source-to-view(Two-way)| 1. [(target)]="expression" 2. bindon-target="expression"| Two-way |

  

28. ### What are pipes?
    Pipes in Angular are a powerful feature that allow you to transform data in your templates. They can be used to format strings, dates, currencies, and more. Angular provides several built-in pipes, and you can also create your own custom pipes.

    **Using Built-in Pipes**

	Angular includes a set of built-in pipes that cover common data transformations. Here are a few examples:
	
	1. **DatePipe**: Formats a date value according to locale rules.
	   ```html
	   {{ today | date }} <!-- Default date format -->
	   {{ today | date:'shortDate' }} <!-- Short date format -->
	   ```
	
	2. **UpperCasePipe**: Transforms text to uppercase.
	   ```html
	   {{ 'hello' | uppercase }} <!-- Outputs: HELLO -->
	   ```
	
	3. **LowerCasePipe**: Transforms text to lowercase.
	   ```html
	   {{ 'HELLO' | lowercase }} <!-- Outputs: hello -->
	   ```

  

29. ### What is a parameterized pipe?
    parameterized pipe is a type of pipe that can accept one or more parameters to customize its behavior. Pipes are a way to transform data in templates, and parameterized pipes provide additional flexibility by allowing you to pass arguments to the pipe.
    A parameterized pipe is used by adding a colon (:) followed by the parameter value(s) after the pipe name. Multiple parameters can be separated by colons.

	```html
	{{ 'Hello, world!' | slice:7:12 }} <!-- Outputs: world -->
	```
	
	```typescript
	import { Component } from '@angular/core';

	@Component({
	  selector: 'app-date-example',
	  template: `<p>{{ today | date:'fullDate' }}</p>`
	})
	export class DateExampleComponent {
	  today: number = Date.now();
	}
	```
	In this example, the date pipe is used with the parameter 'fullDate', which tells Angular to format the date as a full date string.
	
	 You can also add parameters to custom pipes:
	
	```typescript
	import { Pipe, PipeTransform } from '@angular/core';
	
	@Pipe({
	  name: 'exclaim'
	})
	export class ExclaimPipe implements PipeTransform {
	  transform(value: string, times: number): string {
	    return value + '!'.repeat(times);
	  }
	}
	```
	
	```html
	{{ 'hello' | exclaim:3 }} <!-- Outputs: hello!!! -->
	```
  

30. ### How do you chain pipes?
    You can chain pipes together in potentially useful combinations as per the needs. Let's take a birthday property which uses date pipe(along with parameter) and uppercase pipes as below

    ```typescript
    import { Component } from '@angular/core';

            @Component({
              selector: 'app-birthday',
              template: `<p>Birthday is {{  birthday | date:'fullDate' | uppercase}} </p>` // THURSDAY, JUNE 18, 1987
            })
            export class BirthdayComponent {
              birthday = new Date(1987, 6, 18);
            }

    ```

  

31. ### What is a custom pipe?
    You can create your own custom pipes when the built-in ones do not meet your needs. Here’s how you can create a custom pipe in Angular.

	1. **Generate a Custom Pipe**:
	   You can generate a pipe using the Angular CLI:
	   ```bash
	   ng generate pipe custom
	   ```
	
	   This command will create a new pipe file with the necessary boilerplate code.
	
	2. **Implement the Pipe Logic**:
	   Open the generated pipe file and implement the transformation logic. For example, let's create a custom pipe that reverses a string.
	
	   ```typescript
	   import { Pipe, PipeTransform } from '@angular/core';
	
	   @Pipe({
	     name: 'reverse'
	   })
	   export class ReversePipe implements PipeTransform {
	     transform(value: string): string {
	       return value.split('').reverse().join('');
	     }
	   }
	   ```
	
	3. **Register the Pipe**:
	   Ensure the pipe is declared in the appropriate module.
	
	   ```typescript
	   import { NgModule } from '@angular/core';
	   import { BrowserModule } from '@angular/platform-browser';
	   import { AppComponent } from './app.component';
	   import { ReversePipe } from './reverse.pipe';
	
	   @NgModule({
	     declarations: [
	       AppComponent,
	       ReversePipe
	     ],
	     imports: [
	       BrowserModule
	     ],
	     providers: [],
	     bootstrap: [AppComponent]
	   })
	   export class AppModule { }
	   ```
	
	4. **Use the Custom Pipe in a Template**:
	   Use your custom pipe in the template just like any other pipe.
	
	   ```html
	   {{ 'hello' | reverse }} <!-- Outputs: olleh -->
	   ```
  
  

32. ### What is the difference between pure and impure pipe?
    In Angular, pipes can be classified as either **pure** or **impure** based on their behavior and how often Angular executes them during change detection. Understanding the difference between these two types of pipes is crucial for optimizing performance and ensuring correct behavior in your applications.

	**Pure pipes** are the default type of pipes in Angular. They are executed only when Angular detects a pure change to the input value. Pure changes include:
	
	- Changes to primitive data types (e.g., string, number, boolean).
	- Changes to object references (e.g., a new array or object).
	
	Pure pipes do not check for changes in the contents of objects or arrays; they only check if the reference to the object or array has changed.
	
	**Impure pipes** are executed on every change detection cycle, regardless of whether the input value changes. This means they will always be recalculated when any change happens in the application.
	
	**Example of an Impure Pipe**
	
	To create an impure pipe, you set the `pure` property to `false` in the `@Pipe` decorator.
	
	```typescript
	import { Pipe, PipeTransform } from '@angular/core';
	
	@Pipe({
	  name: 'impureExclaim',
	  pure: false
	})
	export class ImpureExclaimPipe implements PipeTransform {
	  transform(value: string, times: number): string {
	    return value + '!'.repeat(times);
	  }
	}
	```  

33. ### What is a bootstrapping module?
    Every application has at least one Angular module, the root module that you bootstrap to launch the application is called as bootstrapping module. It is commonly known as `AppModule`. The default structure of `AppModule` generated by AngularCLI would be as follows:
	
	```javascript
        import { BrowserModule } from '@angular/platform-browser';
        import { NgModule } from '@angular/core';
        import { FormsModule } from '@angular/forms';
        import { HttpClientModule } from '@angular/common/http';

        import { AppComponent } from './app.component';

        /* the AppModule class with the @NgModule decorator */
        @NgModule({
          declarations: [
            AppComponent
          ],
          imports: [
            BrowserModule,
            FormsModule,
            HttpClientModule
          ],
          providers: [],
          bootstrap: [AppComponent]
        })
        export class AppModule { }
	```

  

34. ### What are observables?
    Observables are declarative which provide support for passing messages between publishers and subscribers in the application. They are mainly used for event handling, asynchronous programming, and handling multiple values. In this case, you define a function for publishing values, but it is not executed until a consumer subscribes to it. The subscribed consumer then receives notifications until the function completes, or until they unsubscribe.

  

35. ### What is HttpClient and its benefits?
    Most of the Front-end applications communicate with backend services over `HTTP` protocol using either `XMLHttpRequest` interface or the `fetch()` API. Angular provides a simplified client HTTP API known as `HttpClient` which is based on top of `XMLHttpRequest` interface. This client is available from `@angular/common/http` package.
    You can import in your root module as below:

    ```javascript
    import { HttpClientModule } from '@angular/common/http';
    ```

    The major advantages of HttpClient can be listed as below,
    1. Contains testability features
    2. Provides typed request and response objects
    3. Intercept request and response
    4. Supports Observable APIs
    5. Supports streamlined error handling

  

36. ### Explain on how to use `HttpClient` with an example?
    Below are the steps need to be followed for the usage of `HttpClient`.
    1. Import `HttpClient` into root module:
        ```javascript
        import { HttpClientModule } from '@angular/common/http';
        @NgModule({
          imports: [
            BrowserModule,
            // import HttpClientModule after BrowserModule.
            HttpClientModule,
          ],
          ......
          })
         export class AppModule {}
        ```
    2. Inject the `HttpClient` into the application:
        Let's create a userProfileService(`userprofile.service.ts`) as an example. It also defines get method of `HttpClient`:
        ```javascript
        import { Injectable } from '@angular/core';
        import { HttpClient } from '@angular/common/http';

        const userProfileUrl: string = 'assets/data/profile.json';

        @Injectable()
        export class UserProfileService {
          constructor(private http: HttpClient) { }

          getUserProfile() {
            return this.http.get(this.userProfileUrl);
          }
        }
        ```
    3. Create a component for subscribing service:
        Let's create a component called UserProfileComponent(`userprofile.component.ts`), which injects `UserProfileService` and invokes the service method:
        ```javascript
        fetchUserProfile() {
          this.userProfileService.getUserProfile()
            .subscribe((data: User) => this.user = {
                id: data['userId'],
                name: data['firstName'],
                city:  data['city']
            });
        }
        ```
    Since the above service method returns an Observable which needs to be subscribed in the component.

  

37. ### How can you read full response?
    The response body doesn't or may not return full response data because sometimes servers also return special headers or status code, which are important for the application workflow. In order to get the full response, you should use `observe` option from `HttpClient`:

    ```javascript
    getUserResponse(): Observable<HttpResponse<User>> {
      return this.http.get<User>(
        this.userUrl, { observe: 'response' });
    }
    ```
    Now `HttpClient.get()` method returns an Observable of typed `HttpResponse` rather than just the `JSON` data.

  

38. ### How do you perform Error handling?
    If the request fails on the server or fails to reach the server due to network issues, then `HttpClient` will return an error object instead of a successful reponse. In this case, you need to handle in the component by passing `error` object as a second callback to `subscribe()` method.

    Let's see how it can be handled in the component with an example,
    ```javascript
    fetchUser() {
      this.userService.getProfile()
        .subscribe(
          (data: User) => this.userProfile = { ...data }, // success path
          error => this.error = error // error path
        );
    }
    ```
    It is always a good idea to give the user some meaningful feedback instead of displaying the raw error object returned from `HttpClient`.

  

39. ### :warning: What is RxJS?
    RxJS is a library for composing asynchronous and callback-based code in a functional, reactive style using Observables. Many APIs such as  HttpClient produce and consume RxJS Observables and also uses operators for processing observables.

    For example, you can import observables and operators for using HttpClient as below,
    ```typescript
    import { Observable, throwError } from 'rxjs';
    import { catchError, retry } from 'rxjs/operators';
    ```

  

40. ### What is subscribing?
    An Observable instance begins publishing values only when someone subscribes to it. So you need to subscribe by calling the `subscribe()` method of the instance, passing an observer object to receive the notifications.

    Let's take an example of creating and subscribing to a simple observable, with an observer that logs the received message to the console.
    ```javascript
    // Creates an observable sequence of 5 integers, starting from 1
    const source = range(1, 5);

    // Create observer object
    const myObserver = {
      next: x => console.log('Observer got a next value: ' + x),
      error: err => console.error('Observer got an error: ' + err),
      complete: () => console.log('Observer got a complete notification'),
    };

    // Execute with the observer object and Prints out each item
    source.subscribe(myObserver);
    // => Observer got a next value: 1
    // => Observer got a next value: 2
    // => Observer got a next value: 3
    // => Observer got a next value: 4
    // => Observer got a next value: 5
    // => Observer got a complete notification
    ```  

41. ### What is the difference between promise and observable?
    Both **Promises** and **Observables** are used for handling asynchronous operations in JavaScript and TypeScript, but they have different characteristics and use cases. Here’s a comparison to help you understand their differences:

	**Promises**
	
	1. **Single Value**: A Promise represents a single value that may be available now or in the future. Once a Promise is resolved or rejected, it cannot emit any more values.
	2. **Eager Execution**: Promises start executing as soon as they are created, regardless of whether you have subscribed to them or not.
	3. **Immutable**: A Promise is a one-time event. Once resolved or rejected, it cannot change or emit new values.
	4. **Chaining**: Promises allow chaining of `.then()`, `.catch()`, and `.finally()` methods to handle success, error, and finalization.
	5. **Error Handling**: Errors can be caught using `.catch()` in the promise chain.
	6. **Cancellation**: Promises do not provide built-in cancellation. Once a Promise is initiated, it will run to completion.
	
	**Example:**
	```javascript
	const promise = new Promise((resolve, reject) => {
	  setTimeout(() => {
	    resolve('Data fetched successfully!');
	  }, 1000);
	});
	
	promise.then(data => {
	  console.log(data); // Outputs: Data fetched successfully!
	}).catch(error => {
	  console.error('Error:', error);
	});
	```
	
	**Observables**
	
	1. **Multiple Values**: Observables can emit multiple values over time. They are suitable for handling streams of data.
	2. **Lazy Execution**: Observables are lazy; they do not execute until you subscribe to them. Execution only starts when there is an active subscription.
	3. **Mutable**: Observables can emit multiple values and can be used to handle complex asynchronous workflows, including streams and events.
	4. **Operators**: Observables provide a wide range of operators (like `map`, `filter`, `merge`, etc.) for transforming and combining streams of data.
	5. **Error Handling**: Errors are handled through the observer's `error` method and can be managed using operators like `catchError`.
	6. **Cancellation**: Observables support cancellation. Subscriptions can be unsubscribed to stop receiving updates and clean up resources.
	
	**Example:**
	```typescript
	import { Observable } from 'rxjs';
	
	const observable = new Observable(subscriber => {
	  setTimeout(() => {
	    subscriber.next('First value');
	    subscriber.next('Second value');
	    subscriber.complete();
	  }, 1000);
	});
	
	const subscription = observable.subscribe({
	  next(value) { console.log(value); },
	  error(err) { console.error('Error:', err); },
	  complete() { console.log('Complete'); }
	});
	
	// Unsubscribe if needed
	subscription.unsubscribe();
	```

42. ### What is multicasting?
    Multicasting in RxJS is a technique where a single Observable execution is shared among multiple subscribers, allowing all subscribers to receive the same emitted values without triggering separate executions. This is useful for efficient resource management, especially for expensive operations like HTTP requests.

43. ### How do you perform error handling in observables?
    You can handle errors by specifying an **error callback** on the observer instead of relying on `try`/`catch`, which are ineffective in asynchronous environment.

    For example, you can define error callback as below,
    ```javascript
    myObservable.subscribe({
      next(num) { console.log('Next num: ' + num)},
      error(err) { console.log('Received an errror: ' + err)}
    });
    ```

44. ### :warning: What is Angular Universal?
    Angular Universal is a technology for Angular that allows you to render Angular applications on the server side rather than in the browser. This server-side rendering (SSR) approach has several benefits, including improved performance, better SEO, and faster initial load times.


45. ### :warning: What are different types of compilation in Angular?
    Angular offers two ways to compile your application,
    1. Just-in-Time (JIT)
    2. Ahead-of-Time (AOT)


46. ### :warning: What is JIT?
    Just-in-Time (JIT) is a type of compilation that compiles your app in the browser at runtime. JIT compilation was the default until Angular 8, now default is AOT. When you run the ng build (build only) or ng serve (build and serve locally) CLI commands, the type of compilation (JIT or AOT) depends on the value of the aot property in your build configuration specified in angular.json. By default, aot is set to true.


47. ### :warning: What is AOT?
    Ahead-of-Time (AOT) is a type of compilation that compiles your app at build time. This is the default starting in Angular 9. When you run the ng build (build only) or ng serve (build and serve locally) CLI commands, the type of compilation (JIT or AOT) depends on the value of the aot property in your build configuration specified in angular.json. By default, aot is set to true.
    
    ```cmd
    ng build
    ng serve
    ```

48. ### :warning: What are the advantages with AOT?
    Below are the list of AOT benefits,

    - **Faster initial load time:** Since the application is already compiled, the browser can execute the code directly, resulting in a quicker startup.
    - **Smaller application size:** The Angular compiler is not included in the final bundle, reducing the application's size.
    - **Better security:** Templates and metadata are not included in the client-side code, reducing the risk of injection attacks.
    - **Improved performance:** Pre-compiled templates and metadata result in faster rendering and change detection.

49. ### What is the purpose of metadata json files?
    The metadata.json files in Angular serve a crucial role in the Ahead-of-Time (AOT) compilation process. The metadata.json files are used to store metadata about Angular decorators. These files can be thought of as representations of the overall structure of a decorator's metadata, and they are structured in a way similar to an abstract syntax tree (AST).

50. ### What is Angular Ivy?

	Angular Ivy is the default rendering engine for Angular starting from version 9. Ivy is designed to improve build times, enable smaller bundle sizes, and provide enhanced debugging capabilities.
	
	**Enabling Ivy in a Project**
	
	- **For New Projects**: Ivy is enabled by default in new Angular projects starting from version 9. However, if you need to specify Ivy explicitly, you could do so in earlier versions.
	  
	  Example command to create a new project with Ivy (though this is not necessary for Angular 9 and later):
	  ```sh
	  ng new ivy-demo-app --enable-ivy
	  ```
	
	- **For Existing Projects**: If you have an existing project and you want to ensure Ivy is enabled, you need to set the `enableIvy` option in the `angularCompilerOptions` section of your `tsconfig.app.json` (or `tsconfig.json` for the entire project).
	
	  Example configuration in `tsconfig.app.json`:
	  ```json
	  {
	    "compilerOptions": {
	      // Other compiler options
	    },
	    "angularCompilerOptions": {
	      "enableIvy": true
	    }
	  }
	  ```

 51. ### What are the features included in ivy?
		1. **Faster Compilation**:
		   - **Improved Build Times**: Faster initial and incremental builds, improving development speed.
		
		2. **Smaller Bundle Sizes**:
		   - **Efficient Code Generation**: Reduces the size of the JavaScript bundles, resulting in faster load times.
		
		3. **Enhanced Debugging**:
		   - **Readable Error Messages**: More readable and helpful error messages for easier debugging.
		   - **Better Runtime Debugging Tools**: Provides tools for improved runtime debugging and more human-readable output.
		
		4. **Better Type Checking**:
		   - **Improved Template Type Checking**: More accurate and detailed type checking in templates, leading to more reliable code.
		
		5. **Backward Compatibility**:
		   - **Smooth Migration**: Designed to be compatible with existing Angular applications and libraries, allowing for smooth migration.

 52. ### Can I use AOT compilation with Ivy?
      Yes, it is a recommended configuration. Also, AOT compilation with Ivy is faster. So you need set the default build options(with in angular.json) for your project to always use AOT compilation.

      ```javascript
      {
        "projects": {
          "my-project": {
            "architect": {
              "build": {
                "options": {
                  ...
                  "aot": true,
                }
              }
            }
          }
        }
      }
      ```

   

 53. ### What is Angular Language Service?
      The Angular Language Service is a tool that provides helpful features for Angular development within your editor or Integrated Development Environment (IDE). It enhances the development experience by offering intelligent code completions, type checking, and error detection in Angular templates and TypeScript files.

		**Key Features of Angular Language Service**
		
		1. Intelligent Code Completions.
		2. Error Detection and Highlighting.
		3. Type Checking.
		4. Hover Information.
		5. Go to Definition.  

 54. ### How do you install angular language service in the project?
      You can install Angular Language Service in your project with the following npm command,

      ```javascript
      npm install --save-dev @angular/language-service
      ```
      After that add the following to the "compilerOptions" section of your project's tsconfig.json

      ```javascript
      "plugins": [
          {"name": "@angular/language-service"}
      ]
      ```
      **Note:** The completion and diagnostic services works for .ts files only. You need to use custom plugins for supporting HTML files.

   

 55. ### Is there any editor support for Angular Language Service?
      Yes, Angular Language Service is currently available for Visual Studio Code and WebStorm IDEs. You need to install angular language service using an extension and devDependency respectively. In sublime editor, you need to install typescript which has has a language service plugin model.

 56. ### What are web workers in angular?
     A web worker in Angular is a mechanism that allows you to run scripts in background threads. This can be particularly useful for performing computationally intensive tasks without blocking the main thread, thereby maintaining a smooth user interface experience. you can add a Web Worker using `ng generate web-worker app` command which will create `src/app/app.worker.ts` web worker file. This command will perform below actions,

 58. ### What are the limitations with web workers?
      You need to remember two important things when using Web Workers in Angular projects,

      1. Some environments or platforms(like @angular/platform-server) used in Server-side Rendering, don't support Web Workers. In this case you need to provide a fallback mechanism to perform the computations to work in this environments.
      2. Running Angular in web worker using `@angular/platform-webworker` is not yet supported in Angular CLI.


 59. ### What is Angular CLI Builder?
		Angular CLI Builder is a feature introduced in Angular 8 that allows developers to customize the Angular CLI by adding or modifying commands. With CLI Builders, you can:
		
		- Create new commands to perform custom tasks.
		- Modify existing commands to use different tools or perform additional actions.
		
		This provides flexibility to tailor the Angular CLI to better suit the specific needs of your project.

 60. ### What is a Builder?

      A builder is a function that uses the Architect API to perform tasks like "build" or "test". The builder code is defined in an npm package. For example:

   - **BrowserBuilder**: Runs a webpack build for a browser target.
   - **KarmaBuilder**: Starts the Karma server and runs a webpack build for unit tests.

   

 61. ### How do you invoke a builder?
      The Angular CLI command `ng run` is used to invoke a builder with a specific target configuration. The workspace configuration file, `angular.json`, contains default configurations for built-in builders.

   

 62. ### How do you create app shell in Angular?
      An app shell is a way to render a portion of your application at build time, providing a fast initial loading experience. It allows the browser to display static HTML and CSS quickly, without waiting for JavaScript to initialize.

      ```bash
      ng generate appShell [options]
      ```
   

 63. ### What are the Case Types in Angular?

		Angular uses different capitalization conventions to distinguish various types of names:
		
		1. **camelCase**:
		   - Used for symbols, properties, methods, pipe names, non-component directive selectors, and constants.
		   - Example: `selectedUser`
		
		2. **UpperCamelCase (PascalCase)**:
		   - Used for class names, including components, interfaces, NgModules, directives, and pipes.
		   - Example: `UserListComponent`
		
		3. **dash-case (kebab-case)**:
		   - Used for file names and component selectors.
		   - Example: `app-user-list`
		
		4. **UPPER_UNDERSCORE_CASE**:
		   - Used for constants.
		   - Example: `NUMBER_OF_USERS`
   

 64. ### What are the class decorators in Angular?
      A class decorator is a decorator that appears immediately before a class definition, which declares the class to be of the given type, and provides metadata suitable to the type

      The following list of decorators comes under class decorators,

      1. @Component()
      2. @Directive()
      3. @Pipe()
      4. @Injectable()
      5. @NgModule()

 65. ### What is Declarable in Angular?

		A declarable is a class type that you can add to the `declarations` list of an NgModule. The class types that can be declared in a module are components, directives, and pipes. The structure of the `declarations` array in an NgModule would look like this:
		
		```typescript
		declarations: [
		  YourComponent,
		  YourPipe,
		  YourDirective
		]
		```

   

 66. ### What are the restrictions on declarable classes?
      Below classes shouldn't be declared,

      1. A class that's already declared in another NgModule
      2. Ngmodule classes
      3. Service classes
      4. Helper classes

   

 67. ### What is a DI token?
      A DI (Dependency Injection) token is a key used to identify and retrieve a dependency in Angular's dependency injection system. It's like a label that helps the injector find the right provider for the requested dependency.   


 68. ### What is Angular DSL?

		Angular DSL (Domain-Specific Language) refers to the specific syntax Angular uses to extend standard HTML with Angular features. This syntax allows you to write HTML-like code that Angular understands and processes to create dynamic, interactive web applications.
		
		**Key Parts of Angular DSL:**
		
		1. **`()`**: For handling output and DOM events.
		   - Example: `(click)="handleClick()"`
		
		2. **`[]`**: For binding input values and setting attributes.
		   - Example: `[src]="imageUrl"`
		
		3. **`*`**: For structural directives that alter the DOM layout.
		   - Example: `*ngIf="isVisible"`
		
		This syntax helps Angular understand how to render and manage dynamic content in your web application.


69. ### What is an RxJS Subject in Angular?

	An RxJS Subject is a special type of Observable that can send data to multiple subscribers at once. Unlike regular Observables, which send data to each subscriber independently, a Subject allows multiple subscribers to receive the same data.
	
	**Key Points:**
	
	- **Multicast:** A Subject can send data to many subscribers simultaneously.
	- **Like EventEmitters:** Subjects are similar to event emitters because they manage multiple listeners.
	
	**Example:**
	
	```typescript
	import { Subject } from 'rxjs';
	
	// Create a new Subject
	const subject = new Subject<number>();
	
	// Subscribe to the Subject
	subject.subscribe(value => console.log(`observerA: ${value}`));
	subject.subscribe(value => console.log(`observerB: ${value}`));
	
	// Send data to all subscribers
	subject.next(1);
	subject.next(2);
	```
	
	In this example, both `observerA` and `observerB` will receive the values `1` and `2`.

   

70.  ### What is Bazel?

		Bazel is a build tool developed by Google that helps manage and build complex software projects. It tracks dependencies between packages and builds only what’s needed. 
		
		In Angular 8, you can use Bazel to build your Angular application. Note that Angular itself is built using Bazel.

71.  ### What are the advantages of Bazel tool?
      **Advantages of Bazel**

		1. **Fast Builds**: Bazel builds only what has changed, which speeds up the build process.
		2. **Scalability**: It handles large codebases efficiently.
		3. **Incremental Builds**: Rebuilds only the parts of the project that are affected by changes.
		4. **Parallel Execution**: Runs tasks in parallel to improve build speed.
		5. **Dependency Tracking**: Keeps track of dependencies to avoid redundant work.

   

72. ### How do you use Bazel with Angular CLI?
     The @angular/bazel package provides a builder that allows Angular CLI to use Bazel as the build tool.
     1. **Use in an existing applciation:** Add @angular/bazel using CLI
         ```bash
         ng add @angular/bazel
         ```
     2. **Use in a new application:** Install the package and create the application with collection option
         ```bash
         npm install -g @angular/bazel
         ng new --collection=@angular/bazel
         ```
     When you use ng build and ng serve commands, Bazel is used behind the scenes and outputs the results in dist/bin folder.

   

73. ### How do you run Bazel directly?
     Sometimes you may want to bypass the Angular CLI builder and run Bazel directly using Bazel CLI. You can install it globally using @bazel/bazel npm package. i.e, Bazel CLI is available under @bazel/bazel package. After you can apply the below common commands,

     ```bash
     bazel build [targets] // Compile the default output artifacts of the given targets.
     bazel test [targets] // Run the tests with *_test targets found in the pattern.
     bazel run [target]: Compile the program represented by target and then run it.
     ```

   

74. ### What is platform in Angular?
     In Angular, a "platform" is the context in which an application runs. The most common platform is a web browser, but it can also be a mobile device's operating system or a web server.

Angular uses different packages to support these environments:

- For running in a web browser, it uses the `@angular/platform-browser` package.
- For server-side rendering (SSR), it uses the `@angular/platform-server` package.

These packages allow Angular applications to run in various environments, making Angular a platform-independent framework.
   

75. ### What happens if I import the same module twice?
     If multiple modules imports the same module then angular evaluates it only once (When it encounters the module first time). It follows this condition even the module appears at any level in a hierarchy of imported NgModules.

   

76. ### How do you select an element with in a component template?
     You can use `@ViewChild` directive to access elements in the view directly. Let's take input element with a reference,

     ```html
     <input #uname>
     ```
     and define view child directive and access it in ngAfterViewInit lifecycle hook

     ```javascript
     @ViewChild('uname') input;

     ngAfterViewInit() {
       console.log(this.input.nativeElement.value);
     }
     ```

   

77. ### How do you detect route change in Angular?
     In Angular7, you can subscribe to router to detect the changes. The subscription for router events would be as below,

     ```javascript
     this.router.events.subscribe((event: Event) => {})
     ```
     Let's take a simple component to detect router changes

     ```javascript
     import { Component } from '@angular/core';
     import { Router, Event, NavigationStart, NavigationEnd, NavigationError } from '@angular/router';

     @Component({
         selector: 'app-root',
         template: `<router-outlet></router-outlet>`
     })
     export class AppComponent {

         constructor(private router: Router) {

             this.router.events.subscribe((event: Event) => {
                 if (event instanceof NavigationStart) {
                     // Show loading indicator and perform an action
                 }

                 if (event instanceof NavigationEnd) {
                     // Hide loading indicator and perform an action
                 }

                 if (event instanceof NavigationError) {
                     // Hide loading indicator and perform an action
                     console.log(event.error); // It logs an error for debugging
                 }
             });
        }
     }
     ```


78. ### How do you pass headers for HTTP client?
     You can directly pass object map for http client or create HttpHeaders class to supply the headers.

     ```javascript
     constructor(private _http: HttpClient) {}
     this._http.get('someUrl',{
        headers: {'header1':'value1','header2':'value2'}
     });

     (or)
     let headers = new HttpHeaders().set('header1', headerValue1); // create header object
     headers = headers.append('header2', headerValue2); // add a new header, creating a new object
     headers = headers.append('header3', headerValue3); // add another header

     let params = new HttpParams().set('param1', value1); // create params object
     params = params.append('param2', value2); // add a new param, creating a new object
     params = params.append('param3', value3); // add another param

     return this._http.get<any[]>('someUrl', { headers: headers, params: params })
     ```

     

79. ### What is the purpose of differential loading in CLI?
     From Angular8 release onwards, the applications are built using differential loading strategy from CLI to build two separate bundles as part of your deployed application.

     1. The first build contains ES2015 syntax which takes the advantage of built-in support in modern browsers, ships less polyfills, and results in a smaller bundle size.
     2. The second build contains old ES5 syntax to support older browsers with all necessary polyfills. But this results in a larger bundle size.

     **Note:** This strategy is used to support multiple browsers but it only load the code that the browser needs.

     

80. ### Is Angular supports dynamic imports?
     Yes, Angular 8 supports dynamic imports in router configuration. i.e, You can use the import statement for lazy loading the module using `loadChildren` method and it will be understood by the IDEs(VSCode and WebStorm), webpack, etc.
     Previously, you have been written as below to lazily load the feature module. By mistake, if you have typo in the module name it still accepts the string and throws an error during build time.
     ```javascript
     {path: ‘user’, loadChildren: ‘./users/user.module#UserModulee’},
     ```
     This problem is resolved by using dynamic imports and IDEs are able to find it during compile time itself.
     ```javascript
     {path: ‘user’, loadChildren: () => import(‘./users/user.module’).then(m => m.UserModule)};
     ```

     

81. ### :warning: What is lazy loading?
     Lazy loading is one of the most useful concepts of Angular Routing. It helps us to download the web pages in chunks instead of downloading everything in a big bundle. It is used for lazy loading by asynchronously loading the feature module for routing whenever required using the property `loadChildren`. Let's load both `Customer` and `Order` feature modules lazily as below,
     ```javascript
     const routes: Routes = [
       {
         path: 'customers',
         loadChildren: () => import('./customers/customers.module').then(module => module.CustomersModule)
       },
       {
         path: 'orders',
         loadChildren: () => import('./orders/orders.module').then(module => module.OrdersModule)
       },
       {
         path: '',
         redirectTo: '',
         pathMatch: 'full'
       }
     ];
     ``` 

82. ### :warning: What is Angular Material?
     Angular Material is a collection of Material Design components for the Angular framework. It makes it easy to apply Material Design principles to your Angular applications.
     ```bash
     npm install --save @angular/material @angular/cdk @angular/animations
     (OR)
     yarn add @angular/material @angular/cdk @angular/animations
     ```
     It supports the most recent two versions of all major browsers. The latest version of Angular material is 18.1.0

83. ### What is NgUpgrade?
     NgUpgrade is a library created by the Angular team that allows you to run AngularJS and Angular components together in the same application. It helps bridge the dependency injection systems of both frameworks, making it easier to migrate from AngularJS to Angular gradually.

     

84. ### How do you test Angular application using CLI?
     Angular CLI downloads and install everything needed with the Jasmine Test framework. You just need to run `ng test` to see the test results. By default this command builds the app in watch mode, and launches the `Karma test runner`. The output of test results would be as below,
     ```bash
     10% building modules 1/1 modules 0 active
     ...INFO [karma]: Karma v1.7.1 server started at http://0.0.0.0:9876/
     ...INFO [launcher]: Launching browser Chrome ...
     ...INFO [launcher]: Starting browser Chrome
     ...INFO [Chrome ...]: Connected on socket ...
     Chrome ...: Executed 3 of 3 SUCCESS (0.135 secs / 0.205 secs)
     ```
     **Note:** A chrome browser also opens and displays the test output in the "Jasmine HTML Reporter".

85. ### What is the difference between ngIf and hidden property?
     The main difference is that *ngIf will remove the element from the DOM, while [hidden] actually plays with the CSS style by setting `display:none`. Generally it is expensive to add and remove stuff from the DOM for frequent actions.

     

86. ### What is slice pipe?
     The slice pipe is used to create a new Array or String containing a subset (slice) of the elements. The syntax looks like as below,
     ```javascript
     {{ value_expression | slice : start [ : end ] }}
     ```
     For example, you can provide 'hello' list based on a greeting array,
     ```javascript
     @Component({
       selector: 'list-pipe',
       template: `<ul>
         <li *ngFor="let i of greeting | slice:0:5">{{i}}</li>
       </ul>`
     })
     export class PipeListComponent {
       greeting: string[] = ['h', 'e', 'l', 'l', 'o', 'm','o', 'r', 'n', 'i', 'n', 'g'];
     }
     ```     

87. ### :warning: What is the purpose of ngFor trackBy?
     The main purpose of using *ngFor with trackBy option is performance optimization. Normally if you use NgFor with large data sets, a small change to one item by removing or adding an item, can trigger a cascade of DOM manipulations. In this case, Angular sees only a fresh list of new object references and to replace the old DOM elements with all new DOM elements. You can help Angular to track which items added or removed by providing a `trackBy` function which takes the index and the current item as arguments and needs to return the unique identifier for this item.

     For example, lets set trackBy to the trackByTodos() method
     ```javascript
     <div *ngFor="let todo of todos; trackBy: trackByTodos">
       ({{todo.id}}) {{todo.name}}
     </div>
     ```
     and define the trackByTodos method,
     ```javascript
     trackByTodos(index: number, item: Todo): number { return todo.id; }
     ```

     

88. ### What is the purpose of ngSwitch directive?
     **NgSwitch** directive is similar to JavaScript switch statement which displays one element from among several possible elements, based on a switch condition. In this case only the selected element placed into the DOM. It has been used along with `NgSwitch`, `NgSwitchCase` and `NgSwitchDefault` directives.

     For example, let's display the browser details based on selected browser using ngSwitch directive.
     ```javascript
     <div [ngSwitch]="currentBrowser.name">
       <chrome-browser    *ngSwitchCase="'chrome'"    [item]="currentBrowser"></chrome-browser>
       <firefox-browser   *ngSwitchCase="'firefox'"     [item]="currentBrowser"></firefox-browser>
       <opera-browser     *ngSwitchCase="'opera'"  [item]="currentBrowser"></opera-browser>
       <safari-browser     *ngSwitchCase="'safari'"   [item]="currentBrowser"></safari-browser>
       <ie-browser  *ngSwitchDefault           [item]="currentItem"></ie-browser>
     </div>
     ```

89. ### What is safe navigation operator?
     The safe navigation operator(?)(or known as Elvis Operator) is used to guard against `null` and `undefined` values in property paths when you are not aware whether a path exists or not. i.e. It returns value of the object path if it exists, else it returns the null value.

     For example, you can access nested properties of a user profile easily without null reference errors as below,
     ```javascript
     <p>The user firstName is: {{user?.fullName.firstName}}</p>
     ```
     Using this safe navigation operator, Angular framework stops evaluating the expression when it hits the first null value and renders the view without any errors.

90. ### What is Angular compiler?
     The Angular compiler is used to convert the application code into JavaScript code. It reads the template markup, combines it with the corresponding component class code, and emits component factories which creates JavaScript representation of the component along with elements of @Component metadata.

     

91. ### What is the role of ngModule metadata in compilation process?
     The `@NgModule` metadata is used to tell the Angular compiler what components to be compiled for this module and how to link this module with other modules.

     

92. ### How does angular finds components, directives and pipes?
     The Angular compiler finds a component or directive in a template when it can match the selector of that component or directive in that template. Whereas it finds a pipe if the pipe's name appears within the pipe syntax of the template HTML.

93. ### What are feature modules?
     Feature modules are NgModules, which are used for the purpose of organizing code. The feature module can be created with Angular CLI using the below command in the root directory,
     ```javascript
     ng generate module MyCustomFeature //
     ```
     Angular CLI creates a folder called `my-custom-feature` with a file inside called `my-custom-feature.module.ts` with the following contents
     ```javascript
     import { NgModule } from '@angular/core';
     import { CommonModule } from '@angular/common';

     @NgModule({
       imports: [
         CommonModule
       ],
       declarations: []
     })
     export class MyCustomFeature { }
     ```

     **Note:**  The "Module" suffix shouldn't present in the name because the CLI appends it.

     

94. ### What are the imported modules in CLI generated feature modules?
     In the CLI generated feature module, there are two JavaScript import statements at the top of the file
     1. **NgModule:** InOrder to use the `@NgModule` decorator
     2. **CommonModule:** It provides many common directives such as `ngIf` and `ngFor`.

     

95. ### What are the differences between ngmodule and javascript module?
     Below are the main differences between Angular NgModule and javascript module,

     | NgModule | JavaScript module |
     |---- | --------- |
     | NgModule bounds declarable classes only | There is no restriction classes |
     | List the module's classes in declarations array only | Can define all member classes in one giant file |
     | It only export the declarable classes it owns or imports from other modules| It can export any classes |
     | Extend the entire application with services by adding providers to provides array | Can't extend the application with services |

96. ### :warning: What is a shared module?
     The Shared Module is the module in which you put commonly used directives, pipes, and components into one module that is shared(import it) throughout the application. It is shared by importing the shared module in the feature module imports array.

     ```typescript
     import { CommonModule } from '@angular/common';
     import { NgModule } from '@angular/core';
     import { FormsModule } from '@angular/forms';
     import { UserComponent } from './user.component';
     import { NewUserDirective } from './new-user.directive';
     import { OrdersPipe } from './orders.pipe';

     @NgModule({
      imports:      [ CommonModule ],
      declarations: [ UserComponent, NewUserDirective, OrdersPipe ],
      exports:      [ UserComponent, NewUserDirective, OrdersPipe,
                      CommonModule, FormsModule ]
     })
     export class SharedModule { }
     ```

     

97. ### Can I share services using modules?
     No, it is not recommended to share services by importing module. i.e Import modules when you want to use directives, pipes, and components only. The best approach to get a hold of shared services is through 'Angular dependency injection' because importing a module will result in a new service instance.

Certainly! Here are detailed answers to your questions:

97. ### How do you provide configuration inheritance?
In Angular, configuration inheritance isn't directly supported in a hierarchical manner like some other frameworks. However, you can manage configuration inheritance through services. For example, you can create a base service with shared configuration and then extend or override that configuration in derived services.

**Example:**
```typescript
// Base service
@Injectable({
  providedIn: 'root'
})
export class BaseService {
  config = { apiUrl: 'https://api.example.com' };
}

// Derived service
@Injectable({
  providedIn: 'root'
})
export class DerivedService extends BaseService {
  constructor() {
    super();
    this.config.apiUrl = 'https://api.derived.com';
  }
}
```

98. ### What is Angular's security model for preventing XSS attacks?
Angular's security model includes multiple layers of protection to prevent Cross-Site Scripting (XSS) attacks:
- **Sanitization**: Angular automatically sanitizes potentially dangerous content. It removes unsafe HTML, styles, and URLs.
- **Template Security**: Angular's template compiler ensures that expressions used in templates are safe. It disallows dangerous content and provides context-aware escaping.
- **DomSanitizer**: Angular provides `DomSanitizer` for explicitly marking content as safe.

99. ### What is the role of the template compiler in the prevention of XSS attacks?
The Angular template compiler performs several tasks to prevent XSS:
- **Context-Sensitive Encoding**: It ensures that data bindings in templates are contextually safe (HTML, URL, etc.).
- **Sanitization**: It automatically escapes potentially dangerous content to prevent XSS.

100. ### What is sanitization? Does Angular support it?
Sanitization is the process of cleaning and filtering data to remove potentially harmful content. Angular supports sanitization through its `DomSanitizer` service, which cleans and verifies content based on its context (HTML, style, URL, etc.).

**Example:**
```typescript
import { DomSanitizer, SafeHtml } from '@angular/platform-browser';

constructor(private sanitizer: DomSanitizer) {}

sanitizeHtml(html: string): SafeHtml {
  return this.sanitizer.bypassSecurityTrustHtml(html);
}
```

101. ### How do you support server-side XSS protection in Angular applications?
Server-side XSS protection should be implemented in conjunction with Angular's client-side protection. This includes:
- **Input Validation**: Ensure all user inputs are validated and sanitized on the server-side.
- **Output Encoding**: Encode output data to prevent injection attacks.
- **Security Headers**: Use HTTP security headers like Content Security Policy (CSP) to mitigate XSS risks.

102. ### :warning: What are HTTP Interceptors?
HTTP Interceptors are a mechanism in Angular to intercept and modify HTTP requests and responses. They allow you to:
- Add headers to requests.
- Handle or transform responses.
- Implement logging, authentication, and error handling.

**Example:**
```typescript
@Injectable()
export class AuthInterceptor implements HttpInterceptor {
  intercept(req: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>> {
    const authReq = req.clone({ headers: req.headers.set('Authorization', 'Bearer token') });
    return next.handle(authReq);
  }
}
```

103. ### What are the applications of HTTP interceptors?
- **Authentication**: Add authentication tokens to HTTP requests.
- **Logging**: Log request and response details.
- **Error Handling**: Handle and transform HTTP errors.
- **Caching**: Implement request caching.

104. ### Is multiple interceptors supported in Angular?
Yes, Angular supports multiple HTTP interceptors. They are executed in the order they are provided in the `providers` array.

**Example:**
```typescript
providers: [
  AuthInterceptor,
  LoggingInterceptor
]
```

105. ### How can I use an interceptor for an entire application?
You register interceptors in the root module’s `providers` array to apply them globally across the application.

**Example:**
```typescript
@NgModule({
  providers: [
    { provide: HTTP_INTERCEPTORS, useClass: AuthInterceptor, multi: true },
    { provide: HTTP_INTERCEPTORS, useClass: LoggingInterceptor, multi: true }
  ]
})
export class AppModule {}
```

106. ### How does Angular simplify Internationalization (i18n)?
Angular simplifies internationalization by providing built-in support for:
- **Translation of text** using i18n attributes.
- **Date, number, and currency formatting** based on locale.
- **Dynamic localization** using Angular’s `@angular/localize` package.

107. ### What is the purpose of the `i18n` attribute?
The `i18n` attribute in Angular is used to mark text that should be translated in templates. It helps in identifying and extracting translatable strings.

**Example:**
```html
<p i18n="@@welcomeMessage">Welcome to Angular!</p>
```

108. ### What is the purpose of a custom ID in translation?
A custom ID is used to uniquely identify translatable text, making it easier to manage and translate content, especially in large applications. It ensures consistency across translations.

109. ### What happens if the custom ID is not unique?
If a custom ID is not unique, it can lead to translation conflicts or incorrect translations. Multiple elements with the same ID might be translated incorrectly or inconsistently.

110. ### Can I translate text without creating an element?
Yes, you can translate text without creating a new HTML element by using Angular’s i18n API to handle translations programmatically.

**Example:**
```typescript
import { getLocaleDateFormat } from '@angular/common';

const translatedText = this.translate.instant('Hello World');
```

111. ### How can I translate attributes?
You can translate attributes similarly to text content by using the `i18n` attribute on the element.

**Example:**
```html
<img [attr.alt]="'image.alt' | translate">
```

112. ### What is an Angular library?
An Angular library is a reusable package of code that can be used across multiple Angular applications. It can include components, services, and other Angular artifacts.

113. ### :warning: What is the purpose of `ngcc`?
The Angular Compatibility Compiler (ngcc) converts Angular libraries compiled with the View Engine to Ivy-compatible format. It ensures compatibility with the Ivy rendering engine.

114. ### :warning: What is NgZone?
`NgZone` is a service in Angular that helps manage and optimize how your application detects changes and handles asynchronous tasks (like HTTP requests or timers).

115. ### What is NoopZone?
`NoopZone` is a placeholder implementation of `NgZone` that disables Angular’s change detection. It can be used for performance testing or to avoid Angular’s automatic change detection.

116. ### How do you create displayBlock components?
To create a component that displays as a block element, set the component's CSS `display` property to `block`.

**Example:**
```css
:host {
  display: block;
}
```

117. ### What are the possible data update scenarios for change detection?
- **User Actions**: Events like clicks and input changes.
- **HTTP Responses**: Data returned from HTTP requests.
- **Timer-based Updates**: Intervals or timeouts.
- **Observable Data**: Data changes from RxJS observables.

118. ### What is the purpose of any type cast function?
Type casting functions (e.g., `as` keyword) are used to assert or convert a value to a specific type. This is useful when you need to override TypeScript’s type inference.

**Example:**
```typescript
const someValue = someFunction() as SomeType;
```

119. ### What is the non-null type assertion operator?
The non-null type assertion operator (`!`) asserts that a value is not `null` or `undefined`. It tells TypeScript to treat the value as if it’s guaranteed to be present.

**Example:**
```typescript
const element = document.getElementById('myElement')!;
```

120. ### What is type narrowing?
Type narrowing is the process of refining a variable’s type within a conditional block. It helps TypeScript understand more specific types based on runtime checks.

**Example:**
```typescript
function example(value: string | number) {
  if (typeof value === 'string') {
    // TypeScript knows value is a string here
  } else {
    // TypeScript knows value is a number here
  }
}
```

### 121. :warning: Ts cosole trick question
```typescript
console.log(1 + "2" + "2"); //122
console.log(1 + +"2" + "2"); //32
console.log(1 + - "1" + "2"); // 02
console.log(+"1" + "1" + "2"); //112
console.log("A" - "B" + "2"); //Nan2
console.log("A" - "B" + 2); // Nan
```

Sure, here are more detailed answers for each question:

### 122. :warning: What is the difference between Subject and Observable in Angular?

**Answer:**
- **Observable:** Observables are declarative which provide support for passing messages between publishers and subscribers in the application. They are mainly used for event handling, asynchronous programming, and handling multiple values. In this case, you define a function for publishing values, but it is not executed until a consumer subscribes to it. The subscribed consumer then receives notifications until the function completes, or until they unsubscribe.

- **Subject:** A `Subject` in Angular is like a special kind of data stream that can both send and receive data. Think of it as a bridge between a data producer and multiple data consumers.



### 123. :warning: What is the difference between `for...in` and `for...of` in JavaScript?

**`for...in` Loop**

- **What it does**: Iterates over the keys (property names) of an object.
- **When to use**: When you need to get the keys of an object.

```javascript
const obj = {a: 1, b: 2, c: 3};
for (let key in obj) {
  console.log(key); // logs 'a', 'b', 'c'
}
```

**`for...of` Loop**

- **What it does**: Iterates over the values of an iterable object (like arrays, strings, or Maps).
- **When to use**: When you need to get the values of an array or other iterable objects.

```javascript
const arr = [1, 2, 3];
for (let value of arr) {
  console.log(value); // logs 1, 2, 3
}
```
`Note` that if you try to use for...in loop on array it will use the indices as keys. which is not recomended.


### 124. :warning: What are generic types in Angular?

**Answer:**
Generic types in Angular are a way to create reusable and type-safe components, services, and classes that can work with different data types. By using generics, you can define a template that can accept various types of data without losing type safety.

Example of a generic service:

```typescript
class DataService<T> {
  private data: T[] = [];

  add(item: T) {
    this.data.push(item);
  }

  getAll(): T[] {
    return this.data;
  }
}

const numberService = new DataService<number>();
numberService.add(123);
const numbers = numberService.getAll(); // numbers: number[]

const stringService = new DataService<string>();
stringService.add('Hello');
const strings = stringService.getAll(); // strings: string[]
```

### 125. :warning: What is the difference between FormBuilder and FormGroup in Angular?

**Answer:**
- **FormBuilder:** FormBuilder is a service provided by Angular that helps in the creation of FormGroup, FormControl, and FormArray. It reduces the amount of boilerplate code required to create forms and allows for more readable and maintainable form creation.

  ```typescript
  constructor(private fb: FormBuilder) {}
  
  this.form = this.fb.group({
    name: ['', Validators.required],
    email: ['', [Validators.required, Validators.email]]
  });
  ```

- **FormGroup:** A FormGroup is a way to manage a collection of form controls in Angular. It keeps track of the values and validation state of the form as a whole.

  ```typescript
  this.form = new FormGroup({
    name: new FormControl('', Validators.required),
    email: new FormControl('', [Validators.required, Validators.email])
  });
  ```

### 126. :warning: How do you add dynamic validation in a form in Angular?

**Answer:**
To add dynamic validation to a form in Angular, you can use the `setValidators` method on a FormControl or FormGroup and then call `updateValueAndValidity` to apply the new validators. Here’s an example:

```typescript
// Assuming we have a form control
const emailControl = this.form.get('email');

// Set new validators dynamically
emailControl.setValidators([Validators.required, Validators.email]);

// Update the validity state
emailControl.updateValueAndValidity();
```

### 127. :warning: What is a nested reactive form in Angular?

**Answer:**
A nested reactive form in Angular is a form structure where a FormGroup contains other FormGroups or FormArrays, allowing for complex forms with hierarchical structures. This is useful for forms that require multiple levels of grouping, such as a form for entering information about a user and their addresses.

Example:

```typescript
this.userForm = this.fb.group({
  name: ['', Validators.required],
  addresses: this.fb.array([
    this.fb.group({
      street: ['', Validators.required],
      city: ['', Validators.required]
    })
  ])
});

// Accessing nested FormGroup
const addresses = this.userForm.get('addresses') as FormArray;
```

### 128. :warning: What is the use of FormArray in Angular?

**Answer:**
FormArray is used to manage an array of FormControls, FormGroups, or other FormArrays in Angular forms. It is useful for creating dynamic forms where the number of form controls can change, such as adding or removing items in a list.

Example:

```typescript
this.form = this.fb.group({
  items: this.fb.array([
    this.fb.control('Item 1'),
    this.fb.control('Item 2')
  ])
});

// Adding a new control to the FormArray
const items = this.form.get('items') as FormArray;
items.push(this.fb.control('Item 3'));
```

### 129. :warning: What is the ChangeDetector class in Angular?

**Answer:**
The ChangeDetector class in Angular is used to control the change detection mechanism, which is responsible for keeping the view in sync with the model. It provides methods to manually trigger change detection and check the component's view for changes.

Methods include:
- `detectChanges()`: Manually triggers change detection.
- `markForCheck()`: Marks the component for checking in the next change detection cycle.
- `detach()`: Detaches the component from the change detection tree.
- `reattach()`: Reattaches the component to the change detection tree.

Example:

```typescript
import { ChangeDetectorRef } from '@angular/core';

constructor(private cd: ChangeDetectorRef) {}

// Manually triggering change detection
this.cd.detectChanges();
```

### 130. :warning: Name 10 RxJS operators.

**Answer:**
1. **map:** Transforms items emitted by an observable by applying a function to each item.
   ```typescript
   import { map } from 'rxjs/operators';

   observable.pipe(map(value => value * 2));
   ```

2. **filter:** Emits only those items from an observable that pass a predicate test.
   ```typescript
   import { filter } from 'rxjs/operators';

   observable.pipe(filter(value => value > 10));
   ```

3. **mergeMap:** Projects each source value to an Observable, which is merged in the output Observable.
   ```typescript
   import { mergeMap } from 'rxjs/operators';

   observable.pipe(mergeMap(value => otherObservable));
   ```

4. **switchMap:** Projects each source value to an Observable, which is merged in the output Observable, but unsubscribes from previous inner observables.
   ```typescript
   import { switchMap } from 'rxjs/operators';

   observable.pipe(switchMap(value => otherObservable));
   ```

5. **catchError:** Catches errors on the observable to be handled by returning a new observable or throwing an error.
   ```typescript
   import { catchError } from 'rxjs/operators';

   observable.pipe(catchError(error => of('Error handled')));
   ```

6. **debounceTime:** Emits a value from the source Observable only after a particular time span has passed without another source emission.
   ```typescript
   import { debounceTime } from 'rxjs/operators';

   observable.pipe(debounceTime(300));
   ```

7. **distinctUntilChanged:** Emits all items emitted by the source Observable that are distinct by comparison from the previous item.
   ```typescript
   import { distinctUntilChanged } from 'rxjs/operators';

   observable.pipe(distinctUntilChanged());
   ```

8. **take:** Emits only the first N values emitted by the source Observable.
   ```typescript
   import { take } from 'rxjs/operators';

   observable.pipe(take(5));
   ```

9. **combineLatest:** Combines the latest values from all input observables and emits them as an array.
   ```typescript
   import { combineLatest } from 'rxjs';

   combineLatest([observable1, observable2]).subscribe(values => {
     // values is an array of the latest values from each input observable
   });
   ```

10. **startWith:** Emits a specified value before the source observable starts emitting values.
    ```typescript
    import { startWith } from 'rxjs/operators';

    observable.pipe(startWith('Initial value'));
    ```

### 131. :warning: What are the types of encapsulation in Angular?
In Angular, encapsulation refers to the concept of restricting access to the internal details of a component, allowing for a well-defined interface for interaction. It's a fundamental aspect of component design in Angular and is closely related to the component’s styling and view encapsulation.

Here's a breakdown of encapsulation in Angular:

1. **Component Encapsulation**: Angular components encapsulate their logic, template, and styles. This means that the internal workings of a component are hidden from the outside, and only the defined public API (input/output properties and methods) is exposed. This promotes modularity and reusability.

2. **View Encapsulation**: Angular provides three strategies for view encapsulation:

   - **Emulated** (default): Angular emulates native scoping of styles by adding unique attributes to elements and styles. This ensures that styles defined in a component are scoped to that component and do not affect other components.

   - **Native**: This uses the native Shadow DOM to encapsulate styles. Styles defined in the component only apply to the component’s template, not affecting the global styles or other components.

   - **None**: No encapsulation is applied. Styles are global and affect the entire application. This can lead to style conflicts if not managed carefully.

```typescript
@Component({
selector: 'app-component',
templateUrl: './component.html',
styleUrls: ['./component.css'],
encapsulation: ViewEncapsulation."typename"
})
```

### 132. :warning: What is `ViewChild` in Angular?

**Answer:**
`ViewChild` is a decorator that allows you to access a child component, directive, or DOM element from within the parent component. It provides a reference to the child, enabling you to interact with it directly.

Example:

```typescript
import { Component, ViewChild, ElementRef } from '@angular/core';

@Component({
  selector: 'app-parent',
  template: `
    <input #myInput type="text" />
    <button (click)="focusInput()">Focus Input</button>
  `
})
export class ParentComponent {
  @ViewChild('myInput') inputElement: ElementRef;

  focusInput() {
    this.inputElement.nativeElement.focus();
  }
}
```

### 133. :warning: What is the use of an interface in Angular?

**Answer:**
Interfaces in Angular are used to define the structure of objects, ensuring type safety and consistency. They help in defining the shape of data that components, services, or other parts of the application are expected to handle.

Example:

```typescript
interface User {
  id: number;
  name: string;
  email: string;
}

const user: User = {
  id: 1,
  name: 'John Doe',
  email: 'john.doe@example.com'
};
```

### 134. :warning: What is an entry component in Angular?

**Answer:**
An entry component is any component that is loaded imperatively, meaning it is not referenced in a template but rather loaded dynamically at runtime. Entry components are often used in scenarios such as modals, dialogs, or other dynamic content.

To specify entry components in an Angular module:

```typescript
@NgModule({
  declarations: [AppComponent, ModalComponent],
  entryComponents: [ModalComponent],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

### 135. :warning: What are the ways to pass data to multiple components in Angular?

**Answer:**
1. **Input/Output Properties:** Use `@Input` to pass data from a parent component to a child component and `@Output` to emit events from child to parent.
   ```typescript
   @Component({
     selector: 'app-child',
     template: '<p>{{data}}</p>'
   })
   export class ChildComponent {
     @Input() data: string;
   }
   ```

2. **Service with a Shared State:** Create a service to hold and manage the shared state. Use observables to notify components about changes.
   ```typescript
   @Injectable({ providedIn: 'root' })
   export class DataService {
     private dataSubject = new BehaviorSubject<string>('Initial data');
     data$ = this.dataSubject.asObservable();

     updateData(newData: string) {
       this.dataSubject.next(newData);
     }
   }
   ```

3. **Route Parameters:** Pass data through route parameters.
   ```typescript
   this.router.navigate(['/route', { id: 1 }]);
   ```

4. **Observable Data Streams:** Use subjects or other observable streams to pass data between components.
   ```typescript
   this.dataService.data$.subscribe(data => {
     this.data = data;
   });
   ```

### 136. :warning: What is a resolver in Angular?

**Answer:**
A resolver in Angular is a class that implements the `Resolve` interface and is used to pre-fetch data before a route is activated. It ensures that the necessary data is available when the route and its component are initialized.

Example:

```typescript
@Injectable({ providedIn: 'root' })
export class DataResolver implements Resolve<DataType> {
  constructor(private dataService: DataService) {}

  resolve(route: ActivatedRouteSnapshot, state: RouterStateSnapshot): Observable<DataType> {
    return this.dataService.getData(route.params['id']);
  }
}
```

In the routing module:

```typescript
const routes: Routes = [
  {
    path: 'path',
    component: MyComponent,
    resolve: {
      data: DataResolver
    }
  }
];
```

### 137. :warning: What is the use of `trackBy` in `*ngFor`?

**Answer:**
`trackBy` is a function used with `*ngFor` to improve performance by providing a unique identifier for each item in the list. This helps Angular track which items have changed, been added, or removed, and only update the necessary parts of the DOM.

Example:

```typescript
@Component({
  selector: 'app-list',
  template: `
    <div *ngFor="let item of items; trackBy: trackById">
      {{item.name}}
    </div>
  `
})
export class ListComponent {
  items = [{id: 1, name: 'Item 1'}, {id: 2, name: 'Item 2'}];

  trackById(index: number, item: any): number {
    return item.id;
  }
}
```

### 138. :warning: What is the difference between Observables and Promises?

**Answer:**
- **Observables:**
  - Can emit multiple values over time (stream of values).
  - Lazy evaluation: They do not start emitting values until subscribed to.
  - Supports various operators for complex data transformations (map, filter, mergeMap, etc.).
  - Can be cancelled: You can unsubscribe from an observable to stop receiving data.
  - Can handle multiple types of asynchronous operations, such as events and HTTP requests.

  ```typescript
  const observable = new Observable(observer => {
    observer.next('Hello');
    observer.next('World');
    observer.complete();
  });

  observable.subscribe(value => console.log(value));
  ```

- **Promises:**
  - Emit a single value (or an error) and complete.
  - Eager evaluation: They start executing as soon as they are created.
  - Do not support cancellation.
  - Used for handling a single asynchronous operation, such as an HTTP request.

  ```typescript
  const promise = new Promise((resolve, reject) => {
    resolve('Hello, World');
  });

  promise.then(value => console.log(value));
  ```

Here’s how you can address each of the Angular-related questions:

### 139. :warning: Making Multiple API Calls and Handling Responses

To make multiple API calls and then use the combined response to make another API call, you can use RxJS operators like `forkJoin` and `switchMap`. Here’s an example:

```typescript
import { Component } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { forkJoin } from 'rxjs';
import { switchMap } from 'rxjs/operators';

@Component({
  selector: 'app-example',
  templateUrl: './example.component.html'
})
export class ExampleComponent {
  constructor(private http: HttpClient) {}

  makeApiCalls() {
    const apiUrls = [
      'https://api.example.com/data1',
      'https://api.example.com/data2',
      // add more URLs here
    ];

    // Make multiple API calls
    forkJoin(apiUrls.map(url => this.http.get(url)))
      .pipe(
        switchMap(responses => {
          // Combine responses and transform data
          const combinedData = responses.flat();
          const transformedData = combinedData.map(({ name, id }) => ({ name, id }));
          
          // Make another API call based on the combined response
          return this.http.post('https://api.example.com/another-endpoint', transformedData);
        })
      )
      .subscribe(result => {
        console.log('Final API result:', result);
      });
  }
}
```

### 140. :warning: Converting API Response

Assuming you receive the response as `[{name, address, id, phoneno}, ...]`, and you want to convert it to `[{name, id}, ...]`, you can use the `map` function:

```typescript
this.http.get<any[]>('https://api.example.com/data')
  .subscribe(data => {
    const transformedData = data.map(({ name, id }) => ({ name, id }));
    console.log('Transformed Data:', transformedData);
  });
```

### 141. :warning: Handling Performance Issues

To address performance issues in an Angular application, you might look into:

1. **Change Detection**: Ensure that change detection is optimized (e.g., use `OnPush` strategy where possible).
2. **Lazy Loading**: Implement lazy loading for modules to reduce initial load time.
3. **Code Splitting**: Split large bundles to improve load times.
4. **Memory Leaks**: Check for and fix memory leaks, particularly with observables and subscriptions.
5. **Optimizing Angular Builds**: Use tools like Angular CLI's production build (`ng build --prod`).

### 142. :warning: Security and Authentication While Routing

For maintaining security and authentication, you can use route guards:

1. **AuthGuard**: Implement an `AuthGuard` to protect routes.
2. **CanActivate**: Use the `canActivate` method in the guard to check if the user is authenticated.

Example of `AuthGuard`:

```typescript
import { Injectable } from '@angular/core';
import { CanActivate, Router } from '@angular/router';
import { AuthService } from './auth.service';

@Injectable({
  providedIn: 'root'
})
export class AuthGuard implements CanActivate {

  constructor(private authService: AuthService, private router: Router) {}

  canActivate(): boolean {
    if (this.authService.isAuthenticated()) {
      return true;
    } else {
      this.router.navigate(['/login']);
      return false;
    }
  }
}
```

### 143. :warning: Redirecting to Login Page

To redirect to the login page, you can use the Angular Router:

```typescript
this.router.navigate(['/login']);
```

### 144. :warning: Authentication vs Authorization

- **Authentication**: Verifies the identity of a user (e.g., logging in).
- **Authorization**: Determines what actions an authenticated user is allowed to perform (e.g., access to specific resources).

### 145. :warning: Interacting Between Components

If you want to change `Component B` from `Component A`, you can use:

- **Services**: Share data or state through a common service.
- **Event Emitters**: Use `@Output` and `EventEmitter` if components are related (e.g., parent-child).

Example using a service:

```typescript
@Injectable({
  providedIn: 'root'
})
export class SharedService {
  private dataSubject = new BehaviorSubject<any>(null);
  data$ = this.dataSubject.asObservable();

  updateData(data: any) {
    this.dataSubject.next(data);
  }
}
```

### 146. :warning: Login and Logout Authentication

- **Login**: Authenticate the user and store the token in localStorage or sessionStorage.
- **Logout**: Remove the token and redirect to the login page.

Example for login:

```typescript
login(userCredentials) {
  this.http.post('https://api.example.com/login', userCredentials)
    .subscribe(response => {
      localStorage.setItem('authToken', response.token);
      this.router.navigate(['/home']);
    });
}
```

### 147. :warning: Server-Side Rendering (SSR)

**Server-Side Rendering (SSR)** involves rendering Angular applications on the server rather than the client. This can improve the initial load time and SEO. Angular provides support for SSR through Angular Universal.

### 148. :warning: Handling Large Data Sets

For large data sets (e.g., 100,000 records), consider:

- **Pagination**: Load data in chunks or pages to improve performance.
- **Infinite Scroll**: Load data as the user scrolls.
- **Virtual Scrolling**: Render only the visible items in the viewport.

### 149. :warning: Localization in Angular

Angular provides localization support through the `@angular/localize` package. You can use `ngx-translate` or Angular's built-in localization features to manage multiple languages.

### 150. :warning: Interceptors in Angular

**Interceptors** are used to modify HTTP requests and responses globally. Common use cases include adding authentication tokens, handling errors, or modifying headers.

Example:

```typescript
@Injectable()
export class AuthInterceptor implements HttpInterceptor {
  intercept(req: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>> {
    const authReq = req.clone({
      headers: req.headers.set('Authorization', `Bearer ${localStorage.getItem('authToken')}`)
    });
    return next.handle(authReq);
  }
}
```

### 151. :warning: Types of Forms in Angular

1. **Template-Driven Forms**: Use Angular's directives in templates (e.g., `ngModel`).
2. **Reactive Forms**: Use `FormGroup` and `FormControl` in the component.

### 152. :warning: TrackBy vs Without TrackBy

- **Without `trackBy`**: Angular re-renders the entire list when changes occur.
- **With `trackBy`**: Angular tracks items by a unique identifier to optimize rendering performance.

Example with `trackBy`:

```html
<li *ngFor="let item of items; trackBy: trackById">{{ item.name }}</li>
```

```typescript
trackById(index: number, item: any): number {
  return item.id;
}
```

### 153. :warning: Standalone Components

**Standalone Components** are components that do not require the use of Angular modules. They can be used independently and declared with the `standalone: true` option in the `@Component` decorator.

### 154. :warning: Host Binding and Host Listener

- **Host Binding**: Binds properties of the host element to component properties.
  ```typescript
  @HostBinding('attr.class') className = 'my-class';
  ```
- **Host Listener**: Listens to events on the host element.
  ```typescript
  @HostListener('click', ['$event']) onClick(event: Event) {
    console.log('Host clicked', event);
  }
  ```

### 155. :warning: Dumb Components vs Smart Components

- **Dumb Components**: Focus on display logic and receive data via inputs; they don’t handle business logic.
- **Smart Components**: Manage data and state; often handle business logic and pass data to dumb components.

### 156. :warning: Changes in Angular Versions

To discuss changes in Angular versions, focus on significant updates and improvements:

1. **Major Releases**: Include breaking changes and new features (e.g., Angular 8 introduced Ivy).
2. **Minor and Patch Releases**: Include new features and bug fixes (e.g., performance improvements).

To remember specific version changes, refer to Angular's [release notes](https://github.com/angular/angular/releases).

