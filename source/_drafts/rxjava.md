# compose
使用转入的transformer将原来的observable转换成新的observable

# first
发送第一个满足条件的数据,然后则结束订阅

# AsyncSubject
无论订阅的时候AsyncSubject是否completed,永远只收到最后一个值

# BehaviorSubject
订阅时会收到最近发送的一个值

# PublishSubject
从哪里订阅就从哪里收到数据

# ReplaySubject
无论何时订阅,所有历史数据都收到

# relay
