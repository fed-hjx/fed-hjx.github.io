---
title: 记录一次setState执行过程，结果让我很惊讶
summary: 记录一次setState执行过程
desc: 记录一次setState执行过程
---

#### 测试代码 
```
componentDidMount() {

    this.setState({ count: 1 }, function(){
        console.log(`banana`)
    })
    console.log(`lemen`)

    setTimeout(() => {
        console.log(`grape`)
    }, 0)

    this.setState({ count: 2 }, () => {
        console.log(`strawberry`)
    })

    console.log(`pear`)
}
```
结果很简单：

![](https://user-gold-cdn.xitu.io/2018/3/1/161df968db4c0940?w=766&h=114&f=png&s=3403)
这似乎没什么难度，然而...
如果这段代码改成这样：
```
componentDidMount() {
   setTimeout(() => { 
        this.setState({ count: 1 }, function(){
            console.log(`banana`)
        })
        console.log(`lemen`)

        setTimeout(() => {
            console.log(`grape`)
        }, 0)

        this.setState({ count: 2 }, () => {
            console.log(`strawberry`)
        })

        console.log(`pear`)
     }, 0)
}
```
打印结果又是怎样，天真的我以为结果和上面代码一样，然而却被啪啪打脸了：

![](https://user-gold-cdn.xitu.io/2018/3/1/161df9a65a73bf5f?w=512&h=97&f=png&s=1861)

为什么在setTimeout里面的setState会是同步的？请各位大佬解答

在react上提了个issues [地址](https://github.com/facebook/react/issues/12312)