# compose
使用转入的transformer将原来的observable转换成新的observable

# first
发送第一个满足条件的数据,然后则结束订阅

# Subject
把一个数据比较容易的转换成rx来使用,被观察和观察者都是它
## AsyncSubject
无论订阅的时候AsyncSubject是否completed,永远只收到最后一个值.
注意发送数据调用`onNext()`之后,记得要`onComplete()`,不然observer不会监听到数据的.

## BehaviorSubject
订阅时会收到最近发送的一个值

## PublishSubject
从哪里订阅就从哪里收到数据

## ReplaySubject
无论何时订阅,所有历史数据都收到

# TakeUntil (Observable other)
当other发射数据时,本Observable就会取消再发送数据,解除订阅

# TakeUtil (Predicate) 
当检查到Predicate返回true时,本Observable就会取消再发送数据,解除订阅

# Relay
跟Subject相似的功能,不同处在于,Subject当观察者出现异常时(收到`onComplete`,`onError`,会导致被观察者也停止发送数据,Relay则不受影响.
Relay有BehaviorRelay/PublishRelay/ReplayRelay三种,跟Subject下名称相同的功能是一样的.


