# Something
对于项目的一些建议
1、项目的log太少，上层基本上没有log，全是JNI的log，这样后面维护或者查找问题的人，很难办，我建议增加一些log，
拟规则如下：
1）在关键的状态中增加log，以指示到了什么状态
2）在一个业务流程的开始和结束增加log，这样可以清楚地知道流程中做了什么事情
3）打印的log，使用每个类中自己的TAG。如果随便定义的一些字符，过滤的时候根本不好过滤。
	log的信息建议，先写上方法名，然后再写其他的信息，这样看log时，可以清晰的知道在哪个类，哪个方法中执行
	比如：PUCApplication这个类的TAG就是类名，在OnCreate方法中的log这样写：
		Log.i(TAG, "OnCreate, do something");
4) 为了更好的过滤log，TAG可以这样定义：
	比如我们的应用叫PUCAPP，那AtvMain这个类的TAG就定义为PUCAPP/AtvMain，其他类类似
	这样一来，如果既可以过滤某个类的log，也可以过滤这个app的log
2、项目中用到了很多handle来处理消息，而message ID直接用数字，而且handle对象传来传去，不知道handler不会再什么地方被调用
	我建议message ID采用整形常量来表示其意义
	另外在message处理的地方加上注释，说明可能会被什么地方调用
Anto
http://www.tuicool.com/articles/VVRfQjU
