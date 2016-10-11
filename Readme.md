# ng2-simple-global

A simple global variable service for Angular 2.

## Index

- [Install](#install)
- [Usage](#usage)
- [Repository](#Repository)
- [Example](#example)
- [Contributors](#contributors)
- [Changelog](#changelog)
- [License](#license)

## Install

```
npm install ng2-simple-global
```

## Usage

### Import into Angular 2 application (typescript)

`ng2-simple-global` is implemented as Angular 2 injectable service name __SimpleGlobal__.

__For module using SimpleGlobal__

Add `SimpleGlobal` into module providers.

```javascript
import { SimpleGlobal } from 'ng2-simple-global';

@NgModule({
	providers: [SimpleGlobal]
})
```

__For each child component using SimpleGlobal__

```javascript
import {SimpleGlobal} from 'ng2-simple-global';

export class ChildComponent {

	constructor(private sg: SimpleGlobal) { }

}
```

### API

```javascript
import {SimpleGlobal} from 'ng2-simple-global';

@Component({
	selector: 'child-com',
	template: `
		<p>This is a global variable: {{sg.gv}}</p>
		<input type="text" [(ngModel)]="sg.gv">
	`
})
export class ChildComponent {

	localVar;

	constructor(private sg: SimpleGlobal) {
		if (this.sg['gv']) {
			this.localVar = this.sg['gv'];
		}
	}

}
```

Treat `SimpleGlobal` instance as a global object and create/assign additional attributes freely,
and it will be accessible to all component using the service.

## Repository

[ng2-simple-global](https://github.com/J-Siu/ng2-simple-global)

## Example

[ng2-simple-global-example](https://github.com/J-Siu/ng2-simple-global-example)

[plunker](http://plnkr.co/J4GvVp)

## Contributors

* [John Sing Dao Siu](https://github.com/J-Siu)


## Changelog

* 1.2.0
	- Support Angular 2.0.0
	- Clean up package
* 1.2.1
	- Add license file
	- Add punker example
* 1.2.2
	- Update package.json
	- Update Readme.md

## License

The MIT License

Copyright (c) 2016

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
