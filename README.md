# ngx-datatable(Add drag and drop feature)

this project is fork from @swimlane/ngx-datatable because of Add drag and drop feature


--------------
`ngx-datatable` is an Angular component for presenting large and complex data. It has all the features you would expect from any other table but in a light package with _no external dependencies_. The table was designed to be extremely flexible and light; it doesn't make any assumptions about your data or how you: filter, sort or page it.
--------------

## Features

- Handle HTML5 drag and drop event.
- Handle large data sets ( Virtual DOM )
- Expressive Header and Cell Templates
- Horizontal & Vertical Scrolling
- Column Reordering & Resizing
- Client/Server side Pagination & Sorting
- Intelligent Column Width Algorithms ( Force-fill & Flex-grow )
- Integrated Pager
- Cell & Row Selection ( Single, Multi, Keyboard, Checkbox )
- Fixed AND Fluid height
- Left and Right Column Pinning
- Row Detail View
- Decoupled theme'ing with included Google Material theme
- Light codebase / No external dependencies
- AoT Compilation Support
- Universal Support

## Add bug fix from @serive
- Fix for not correct height and width when use mat dialog.
- Fix for not redraw when call recalculate method.

## Installation

To use ngx-datatable in your project install it via [npm](https://www.npmjs.com/package/@serive
/ngx-datatable):

```
npm i @serive/ngx-datatable --save
```

## How to use it.
1. Set isDrag flag in ngx-datatable tag.
```HTML
<ngx-datatable
  class="material"
  [rows]="rows"
  headerHeight="50"
  footerHeight="50"
  [scrollbarV]="true"
  [isDrag]="true"
></ngx-datatable>
```

2. Add "drop" event and "dragover" event as followings.

Drop target.
```HTML
<h3 (drop)="ondrop($event)" (dragover)="allowDrop($event)" ></h3>
```

Add Component.ts
```ts
  // Allow drop event for cancel dragover event.
  allowDrop(event): void {
    event.preventDefault();
  }
  // Allow drop event and get data for target row.
  ondrop(event): void {
    event.preventDefault();
    const text = event.dataTransfer.getData("text");
    alert(text); // Please replace for your code.
  }
```

## Credits

the followings is refer from original site
-------------------
`ngx-datatable` is a [Swimlane](http://swimlane.com) open-source project; we believe in giving back to the open-source community by sharing some of the projects we build for our application. Swimlane is an automated cyber security operations and incident response platform that enables cyber security teams to leverage threat intelligence, speed up incident response and automate security operations.

[SecOps Hub](http://secopshub.com) is an open, product-agnostic, online community for security professionals to share ideas, use cases, best practices, and incident response strategies.
