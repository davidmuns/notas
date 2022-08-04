# Install Angular CLI (source: https://angular.io/guide/setup-local)
npm install -g @angular/cli
# Create workspace and initial application
ng new name-application
# run the application on server
 1) Go first to name-application folder => cd name-application
 2) ng serve --open || ng serve -o || ng s

# Install bootstrap in Angular (source (min 9): https://www.youtube.com/watch?v=tAzKlk3dpI8&list=PLU8oAlHdN5BnNAe8zXnuBNzKID39DUwcO&index=13):

    1) npm install bootstrap --save
    2) open file angular.json
    3) add path to styles and scripts properties:
    
        "styles": [
                "src/styles.css",
                "node_modules/bootstrap/dist/css/bootstrap.min.css"
                ],
        "scripts": [
                "node_modules/bootstrap/dist/js/bootstrap.min.js"
                ],
# Install fontawesome ():

    1) npm install --save @fortawesome/fontawesome-free
    2) open file angular.json
    3) add path to styles and scripts properties:
    
        "styles": [
                "src/styles.css",
                "node_modules/@fortawesome/fontawesome-free/css/all.css"
                ],
        "scripts": [
                "node_modules/@fortawesome/fontawesome-free/js/all.js"
                ],
    4) use it in your template:
        e.g: <i class="fa-solid fa-square-plus fa-2x"></i>

# Adding sgv image to button (source: https://iconscout.com/)
    e.g:
     <button>
        <img class="minus-img" src="../../../assets/minus.svg" alt="btn-minus" />
    </button>

# Components (source: https://angular.io/guide/component-overview)
- create component automatically using CLI:
    ng generate component name-component || ng g c name-component
- create component inline (only typscript file, neither css file nor html file):
    ng generate component -s -t name-component || ng g c -s -t name-component
- component interaction:
    https://www.youtube.com/watch?v=BGy8DdGw_WE

# Import json file (source: https://fjmduran.com/blog/leer-json-angular)
    1) open file tsconfig.json
    2) add in "compilerOptions" the following two properties:
        -  "compilerOptions": {
                "resolveJsonModule": true,
                "allowSyntheticDefaultImports": true,
                ...
                }
    3) import json file in order to use it as follows: 
        import <name of your choice> from 'json file path' 

# Structural directive ngFor (source: https://www.youtube.com/watch?v=Pds_3UZPmuQ ) 
const weekendDaysArr: string[] = ['Saturday', 'Sunday'];
const weekendDayJsonArray: {}[] = [
                                    {"dayName": "Saturday"}, 
                                    {"dayName": "Sunday"}
                                  ]
- syntax: <p *ngFor="let day of weekendDaysArr">{{day}}</p> 
          <p *ngFor="let day of weekendDayJsonArray">{{day.dayName}}</p> 
          Note that index can be obtained and stored in a variable for later use:
          <p *ngFor="let day of weekendDayJsonArray; let i = index">{{ i }} {{day.dayName}}</p>

# Attribute directive ngClass (source: https://www.youtube.com/watch?v=ed6JaTbbZ7c)

# Attribute directive ngModel-two way binding (source: https://www.youtube.com/watch?v=kMmaz-OLCeg):
    - It allows us to send data from template to component and vice versa. [(ngModel)] (banana box :-))
     1) import Fomrsmodule:
            @NgModule({
                declarations: [
                    AppComponent
                ],
                imports: [
                    BrowserModule,
                    FormsModule
                    ],
    

# Class Binding (source: https://www.youtube.com/watch?time_continue=142&v=Vonu67tnPJc&feature=emb_logo):
    - eg:
        Add class bg-green if condition is true: <button [class.bg-green] = "condition">

# Style Binding (source: https://www.youtube.com/watch?v=vzkSp4HSL3s&t=95s):
    - eg:
        Apply color pink to background-color style if condition is true otherwise apply color white: <button [style.backgroundColor] = "condition == true ? 'pink' : 'white'">

# Property Binding [src] to insert images (source: https://www.youtube.com/watch?time_continue=60&v=O6RceGqH7MA&feature=emb_logo):
    
    - Note: local images must be located inside the assets folder.

    - eg:
        export class AppComponent {
            imgPath: string = 'assets/img/img1.jpg';
        } 

        - Using string interpolation: 
            <img src = "{{ imgPath }}">
        - Using property binding:
            <img [src] = "imgPath">

# Event Binding (source: https://www.youtube.com/watch?v=APMJU3E6h58):
    -eg:
        export class AppComponent {
            public save = (e: Event) => console.log(e); 
        }      
        <button (mouseover) = "save($event)">
        
# Event filtering (source: https://www.youtube.com/watch?v=rrEVq7gY6uI&t=174s)

# Template variable (source: https://www.youtube.com/watch?v=tdKg-lpiMvA&t=25s)

# Components interaction (source: https://angular.io/guide/inputs-outputs)

# Services ()
- create service automatically using CLI:
    1) ng generate service name-service || ng g s name-service
    2) include service in app.module.ts file:
      ],
         providers: [name-service],
         bootstrap: [AppComponent]
      })
      export class AppModule { }

# Pipe (source: https://www.youtube.com/watch?v=pAkG9KLrAxI):
- create pipe automatically using CLI:
    ng generate pipe name-pipe || ng g p name-pipe

# Routing module, passing parameters and more (source: https://www.youtube.com/watch?v=HtRZDWaAgRw&list=PL_WGMLcL4jzVY1y-SutA3N_PCNCAG7Y46&index=8):

    - generate routing mdoule using CLI:
     1) ng generate module app-routing --flat --module=app
     2) create routes, imports and exports in app-routing.module.ts file:
        
        const routes: Routes = [
        {
            path: '',
            component: HomeComponent
        }
        ]      
        @NgModule({
            declarations: [],
            imports: [RouterModule.forRoot(routes)]
            exports: [RouterModule]
        })
        export class AppRoutingModule { }
     3) create home componente and copy the code from app template and app component
     3) add selector in app template: <router-outlet></router-outlet>

# Tutorials
- components:
    - https://www.youtube.com/watch?v=CitMo3hip6Y&list=PLU8oAlHdN5BnNAe8zXnuBNzKID39DUwcO&index=5 

- interpolation: 
    - https://angular.io/guide/interpolation
    - https://www.youtube.com/watch?v=KfYyWNqJaVc&list=PLU8oAlHdN5BnNAe8zXnuBNzKID39DUwcO&index=7
    


