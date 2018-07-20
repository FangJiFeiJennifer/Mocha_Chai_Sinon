## expect
```javascript

// 相等或不相等
expect(4 + 5).to.be.equal(9);
expect(4 + 5).to.be.not.equal(10);
expect(foo).to.be.deep.equal({ bar: 'baz' });

// 布尔值为true
expect('everthing').to.be.ok;
expect(false).to.not.be.ok;

// typeof
expect('test').to.be.a('string');
expect({ foo: 'bar' }).to.be.an('object');
expect(foo).to.be.an.instanceof(Foo);

// include
expect([1,2,3]).to.include(2);
expect('foobar').to.contain('foo');
expect({ foo: 'bar', hello: 'universe' }).to.include.keys('foo');
expect('bar').to.have.lengthOf(3);
expect({
    tea: [ 'chai', 'matcha', 'oolong' ]
}).to.have.property('tea').with.lengthOf(3);

// empty
expect([]).to.be.empty;
expect('').to.be.empty;
expect({}).to.be.empty;

// match
expect('foobar').to.match(/^foo/);

```
基本上，expect断言的写法都是一样的。头部是expect方法，尾部是断言方法，比如equal、a/an、ok、match等。两者之间使用to或to.be连接。

如果expect断言不成立，就会抛出一个错误。事实上，只要不抛出错误，测试用例就算通过。

``` javascript
it('1 + 1 should be equal 2', () => {});
```
上面的这个测试用例，内部没有任何代码，由于没有抛出了错误，所以还是会通过。