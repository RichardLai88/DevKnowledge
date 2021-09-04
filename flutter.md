# Flutter 知识小积累
#### onError 和catchError的区别
 * Future中有个then操作符，then里有两个参数，一个是callBack，另一个是个Fuction，这个Fuction有2个参数，一个是Object，一个是方法调用栈，当Future发生error的时候，如果在Then里实现了onError方法，这会调用该方法，如果没有实现onError,则该error会继续往外抛，直到预见CatchError。
 * catchError则会catch这个Future内所发生的的所有没被处理过的error。
