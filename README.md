# Ng-Bootstrap Bazel

1. Init new project
```bash
ng new ng-bootstrap-bazel
# select routing and scss for styles
```

2. Add ng-bootstrap
```bash
yarn add @ng-bootstrap/ng-bootstrap
```

Verify node_modules/@ng-boostrap/ng-bootstrap
```
LICENSE
README.md
accordion
alert
bundles
buttons
carousel
collapse
datepicker
dropdown
esm2015
esm5
fesm2015
fesm5
index.d.ts
modal
ng-bootstrap.d.ts
ng-bootstrap.metadata.json
package.json
pagination
popover
progressbar
rating
tabset
test
timepicker
toast
tooltip
typeahead
util
```

Add ng-alert to app.component.html
```html
<ngb-alert [dismissible]="false">
  <strong>Warning!</strong> Better check yourself, you're not looking too good.
</ngb-alert>
```

Add NgbModule to app.module
```typescript
import {NgbAlertModule} from '@ng-bootstrap/ng-bootstrap';
// ...
imports: [
  //...
  NgbAlertModule,
  //...
]
```

Build and run
```bash
ng build
ng serve
```
