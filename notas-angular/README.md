# Install Angular CLI (source: https://angular.io/guide/setup-local)
npm install -g @angular/cli
# Create workspace and initial application
ng new <name application>
# run the application on server
Go first to <name application> folder => cd <name appliction>
ng serve --open || ng serve -o || ng s

# COMPONENTS (source: https://angular.io/guide/component-overview)
- create component automatically using CLI:
    ng generate component <name component> || ng g c <name component>
- create component inline (only typscript file, neither css file nor html file):
    ng generate component -s -t <name component> || ng g c -s -t <name component>
- component interaction:
    https://www.youtube.com/watch?v=BGy8DdGw_WE

# IMPORT JSON file (source: https://fjmduran.com/blog/leer-json-angular)
    1) open file tsconfig.json
    2) add in "compilerOptions" the following two properties:
        -  "compilerOptions": {
                "resolveJsonModule": true,
                "allowSyntheticDefaultImports": true,
                ...
                }
    3) import json file in order to use it as follows: 
        import <name of your choice> from 'json file path' 

# ngFor (source: https://www.youtube.com/watch?v=Pds_3UZPmuQ ) 
const weekendDaysArr: string[] = ['Saturday', 'Sunday'];
const weekendDayJsonArray: {}[] = [
                                    {"dayName": "Saturday"}, 
                                    {"dayName": "Sunday"}
                                  ]
- syntax: <p *ngFor="let day of weekendDaysArr">{{day}}</p> 
          <p *ngFor="let day of weekendDayJsonArray">{{day.dayName}}</p> 

# ngClass (source: https://www.youtube.com/watch?v=ed6JaTbbZ7c)

# Property Binding [src] to insert images (source: https://www.youtube.com/watch?time_continue=60&v=O6RceGqH7MA&feature=emb_logo):
    
    @Note: local images must be located inside the assets folder.

    Eg:
    export class AppComponent {
        imgPath: string = 'assets/img/img1.jpg';
    } 

    - Usin string interpolation: 
        <img src = "{{ imgPath }}">
    - Using property binding:
        <img [src] = "imgPath">
     
# Tutorials
- components:
    - https://www.youtube.com/watch?v=CitMo3hip6Y&list=PLU8oAlHdN5BnNAe8zXnuBNzKID39DUwcO&index=5 

- interpolation: 
    - https://angular.io/guide/interpolation
    - https://www.youtube.com/watch?v=KfYyWNqJaVc&list=PLU8oAlHdN5BnNAe8zXnuBNzKID39DUwcO&index=7
    


