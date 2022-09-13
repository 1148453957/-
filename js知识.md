# 1. 使用策略模式，在if-else或者switch-case情况比较多的时候
```
// ==================重构前==================
function getPrice(tag, originPrice) {
    // 新人价格
    if(tag === 'newUser') {
        return originPrice > 50.1 ? originPrice - 50 : originPrice
    }
    // 返场价格
    if(tag === 'back') {
         return originPrice > 200 ? originPrice - 50 : originPrice
    }
    // 活动价格
    if(tag === 'activity') {
        return originPrice > 300 ? originPrice - 100 : originPrice
    }
}

// ==================重构后==================
const priceHandler = {
    newUser(originPrice){
        return originPrice > 50.1 ? originPrice - 50 : originPrice
    },
    back(originPrice){
        return originPrice > 200 ? originPrice - 50 : originPrice
    },
    activity(originPrice){
         return originPrice > 300 ? originPrice - 100 : originPrice
    }
}

function getPrice(tag, originPrice){
    return priceHandler[tag](originPrice)
}
```
