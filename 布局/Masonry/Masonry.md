> Masonry本质上就是对系统AutoLayout进行的封装，包括里面很多的API，都是对系统API进行了一次二次包装。

* mas_makeConstraints()    添加约束
* mas_remakeConstraints()  移除之前的约束，重新添加新的约束
* mas_updateConstraints()  更新约束，写哪条更新哪条，其他约束不变

* equalTo()  参数是对象类型，一般是视图对象或者mas_width这样的坐标系对象
* mas_equalTo()   和上面功能相同，参数可以传递基础数据类型对象，可以理解为比上面的API更强大

* width() 用来表示宽度，例如代表view的宽度
* mas_width()     用来获取宽度的值。和上面的区别在于，一个代表某个坐标系对象，一个用来获取坐标系对象的值

* height() 用来表示宽度，例如代表view的宽度
* mas_height()     用来获取宽度的值。和上面的区别在于，一个代表某个坐标系对象，一个用来获取坐标系对象的值