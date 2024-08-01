# Angular Cheatsheet

This cheatsheet should help you to work with angular, when you have experience with `react` or `vue`.

# Table of content


# CLI
With the anguar cli you can quickly create a new angular projekt, components or services.

## Install the CLI

``` shell
npm install -g @angular/cli
```

## Create a new angular project

``` shell
ng new <app-name>
```

## Create a new component

``` shell
ng generate component <component-name>
```

or as shortcut

``` shell
ng g c <component-name>
```

**Info**
> Angular creates new components direct into the `app` folder. Most of the time it's better to create components within a component directory. Therefore you can add a path before the component name like: `ng g c /components/<component-name>`

# Component files
Angular splits its logic into 4 different files.

1. .css
2. .html
3. .spec.ts
4. .ts

**CSS file**

The css file contains all css styles for your component.

> Information: This depens on the css syntax you choose while project creation

**HTML file**

The html file contains the html of your component.

**Spec file**

The spec file contains your test cases for your component.

**TS file**

The ts file contains the logic of your component.

## HTML syntax

There is a special syntax for embedding variables and functions into your html.

### Printing variables

For adding variables you defined into the .ts file you use the following syntax:

``` html
<h1>Hello, {{ myVariable }}</h1>
```

### Passing variables as properties

When you want to pass a variable into another component as property use the following syntax:

``` html
<child-component [myProperty]="myVariable"></child-component>
```

### Passing functions as properties

``` html
<child-component (click)="myFunction()"></child-component>
```

### Looping over iterables

When you want to iterate over an array use the following syntax:

``` html
<div *ngFor="let myItem of myArray">
  <span>{{ myItem }}</span>
</div>
```

### Conditions

When you want to render elements only on certain conditions use the following syntax:

``` html
<div *ngIf="myNumber === 1">
  When myNumber equals 1 the div element will be rendered
</div>
```

## Angular Components

A generic angular component looks like this:

``` typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-my-component',
  standalone: true,
  imports: [],
  templateUrl: './my-component.component.html',
  styleUrl: './my-component.component.css'
})
export class MyComponent {

}

```

> The value of the selector is the name you need to use
