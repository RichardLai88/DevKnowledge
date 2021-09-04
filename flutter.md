# Flutter 知识小积累
#### onError 和catchError的区别
 * Future中有个then操作符，then里有两个参数，一个是callBack，另一个是个Fuction，这个Fuction有2个参数，一个是Object，一个是方法调用栈，当Future发生error的时候，如果在Then里实现了onError方法，这会调用该方法，如果没有实现onError,则该error会继续往外抛，直到预见CatchError。
 * catchError操作符和Then是同级别的，它会catch这个Future内所发生的所有没被处理过的error。

#### Future.wait
 * wait函数有三个参数，第一个参数是Future列表，也就是需要调用的方法列表，第二个参数是bool类型的eagerError, 默认值为false，该参数为ture时会立即返回错误（如果Future列表中有方法发生错误），如果该参数为false，会等所有的Future都执行完之后再执行onError，且只会返回第一个发生错误的error；第三个参数是cleanUp回调函数，如果方法列表中有发生error，则所有Future中成功的value，通过函数回调可以获取到。如果所有Future函数都成功，没有发生error，则不会调用cleanUp函数，换句话说，cleanUp函数和Then函数是互斥的。
