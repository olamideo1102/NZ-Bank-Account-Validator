# NZ Bank Account Validator

v0.0.4 - A small, zero dependency Javascript NZ bank account validation library that runs everywhere.

It is based on the [documentation](https://web.archive.org/web/20181009211542/https://www.ird.govt.nz/resources/9/d/9d739cde-ad76-4c49-ae08-522c62d94dd6/rwt-nrwt-spec-2016.pdf) provided by the Inland Revenue Department.
This library is not however affiliated with or endorsed by the IRD.


## Getting Started

Using npm:

```shell
$ npm i --save nz-bank-account-validator
```

Using yarn:

```shell
$ yarn add nz-bank-account-validator
```

### Installation

In a browser:
_(See examples/browser.html for code example)_

```html
<script type="text/javascript" src="NZ-Bank-Account-Validator.min.js"></script>
<script type="text/javascript">
  var bankAccountValidator = window['NZ-Bank-Account-Validator'];

  bankAccountValidator.validate('01-902-0068389-00');
</script>
```

In Node.js (require):

```js
const bankValidator = require('nz-bank-account-validator/lib/NZ-Bank-Account-Validator');

bankValidator.validate('01-902-0068389-00');
// => true
```

ES6 Modules:

```js
import bankValidator from 'nz-bank-account-validator/lib/NZ-Bank-Account-Validator';

bankValidator.validate('01-902-0068389-00');
// => true
```

## Usage

```js
const bankValidator = require('nz-bank-account-validator/lib/NZ-Bank-Account-Validator');

bankValidator.getId('01-902-0068389-00'); // '01'
bankValidator.getBranch('01-902-0068389-00'); // '02'
bankValidator.getBase('01-902-0068389-00'); // '0068389'
bankValidator.getSuffix('01-902-0068389-00'); // '00'

bankValidator.getPartsObject('01-902-0068389-00'); // { id: '01', branch: '902', base: '0068389', suffix: '00' }

bankValidator.validate('01-902-0068389-00') // true
bankValidator.validate({ id: '01', branch: '902', base: '0068389', suffix: '00' }) // true

bankValidator.validate('01-902-XXXXX-00') // false
bankValidator.validate('01-902--00') // false
bankValidator.validate('01-902-123456-00') // false
```


## Running the tests

To run the tests locally:

```shell
npm i
npm run tests
```

## Authors

* **Josh Hollinshead** - *Initial work* - [wytlytningNZ](https://github.com/wytlytningNZ)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## References

* [IRD - Validating Bank Account Numbers](https://web.archive.org/web/20181009211542/https://www.ird.govt.nz/resources/9/d/9d739cde-ad76-4c49-ae08-522c62d94dd6/rwt-nrwt-spec-2016.pdf)

## Security advisory after snyk test

It has been determined that there are no vulnerabilities in any of the dependencies of this application after running the Synk test, and the application has been placed under Synk monitor for ongoing security. This proactive approach to security will ensure that any potential threats are identified and addressed promptly, and the application remains secure and stable for our users.
