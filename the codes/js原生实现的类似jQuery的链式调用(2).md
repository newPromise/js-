// 实现使用 js 原生实现的类似与 jQuery 的链式调用第二次
// 借助于递归实现的类似于 jQuery 的 class 链式调用
```javascript
function $(context, fnode) {
    context = context.trim();
    let strArr = context.split(' ');
    let len = strArr.length;
    let node = null;
    if (len > 1) {
         node = strArr.reduce((pev, next) => {
            // 在递归的过程中, 递归过程一直是在这个过程中实现的
            return $(next, pev);
        }, '');

    }
    // 如果递归结束， 使用 return 进行返回
    if (node) return node;
    switch (context.slice(0,1)) {
        case '.':
            if (fnode) {
                fnode = [].slice.call(fnode).filter((node) => {
                    if (node.getElementsByClassName(context.slice(1))) {
                        return node.getElementsByClassName(context.slice(1))[0];
                    }
                })
            }
            return document.getElementsByClassName(context.slice(1));
            break;
        case '#':
            return  document.getElementById(context.slice(1));
            break;
    }
}

```
注意:
使用递归实现的函数，需要有一个判断，用来判断递归在哪里结束, 使用 return 语句可以随时实现退出操作
