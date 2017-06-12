# Mocha Snapshots
Snapshot/regression testing for using with Mocha, specially for React+Enzyme users.

\* _Jest is cool but too slow!_

## Install it
`npm i mocha-snapshots --save`

## Use it
```es6
import { expect } from 'chai';
import { shallow } from 'enzyme';
import MyComponent from './path/to/MyComponent';

describe('<MyComponent />', () => {
  it('should match snapshot', () => {
    const wrapper = shallow(<MyComponent />)
    expect(wrapper).to.matchSnapshot();
    expect('you can match strings').to.matchSnapshot();
    expect({ a: 1, b: { c: 1 } }).to.matchSnapshot(); // or any object
    expect(123).to.matchSnapshot(); // and numbers too
  });
});
```

## Run your tests
Add a require argument to your test script/command 

`mocha --require mocha-snapshots`

## Update snapshots
Set an environment variable `UPDATE` and run your test script:

ex: `UPDATE=1 npm test`