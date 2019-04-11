# Description
Load po files for use with `ngx-translate`

## Installation:

 ```
npm i @ngx-translate/core --save
npm i @daniel-bikemap/ngx-translate-po-http-loader --save
 ```

## Usage:
```ts
import { HttpClient, HttpClientModule } from '@angular/common/http';

import { TranslateModule, TranslateLoader } from '@ngx-translate/core';
import { TranslatePoHttpLoader } from '@daniel-bikemap/ngx-translate-po-http-loader';

export function createTranslateLoader(http: HttpClient) {
	return new TranslatePoHttpLoader(http, 'assets/i18n', '.po');
}

@NgModule({
	imports: [
		BrowserModule,
		HttpClientModule,
		TranslateModule.forRoot({
			loader: {
				provide: TranslateLoader,
				useFactory: createTranslateLoader,
				deps: [HttpClient]
			}
		})
	],
	bootstrap: [AppComponent]
})
export class AppModule { }
```
## Contributions
Special thanks to the original author https://github.com/biesbjerg
