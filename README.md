# ngx-dynamic-outlet

An implementation of dynamic template wrapper at Angular > 5.1.0. AoT mode support, but the parameter --build-optimizer should be false in prod (since the decorators will be remove if --build-optimizer=true).

## Installation

To install this library, run:

```bash
$ npm install ngx-dynamic-outlet --save
```

## Consuming your library

Once you have published your library to npm, you can import your library in any Angular application by running:

```bash
$ npm install ngx-dynamic-outlet
```

and then from your Angular `AppModule`:

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';

// Import your library
import { NgxDynamicOutletModule } from 'ngx-dynamic-outlet';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,

    // Specify your library as an import
    NgxDynamicOutletModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Once your library is imported, you can use its components, directives and pipes in your Angular application:

```xml
<!-- You can now use your library component in app.component.html -->
<h1>
  {{title}}
</h1>
<html-outlet [html]="content" [context]="context" ></html-outlet>
```

## Development

To generate all `*.js`, `*.d.ts` and `*.metadata.json` files:

```bash
$ npm run build
```

To lint all `*.ts` files:

```bash
$ npm run lint
```

## License

MIT © [Jackclarify](mailto:jack.chen@clarifyhealth.com)
