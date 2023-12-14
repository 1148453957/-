# js问题
### 1. 懒加载问题
使用新的浏览器api IntersectionObserver，监听一个dom，滚动到视口的时候，执行函数
```
<div class="conainer" ref="containerRef" @scroll="setScrollTop">
    <div
      class="contentItem"
      v-for="(item, index) in contentList"
      :key="index"
      ref="contentItems">
    </div>
</div>

const containerRef = ref(),
contentItems = ref([]),
observer = ref()

function initObserver() {
  observer.value = new IntersectionObserver(handleIntersection, {
    root: containerRef.value,
  })
  // 监听最后一个元素出现的时候
  observer.value.observe(contentItems.value.at(-1))
}
function handleIntersection(entries: any) {
  const lastEntry = entries[0]
  if (lastEntry.isIntersecting) {
    doSomething()
  }
}
function doSomething() {
  //移除旧的监听
  observer.value.unobserve(contentItems.value.at(-1))
  nextTick(async () => {
    //然后新增元素
    contentList.push()
// 新增元素后，最后一个元素加上监听
    observer.value.observe(contentItems.value.at(-1))
  })
}
```
### 2. 文件下载
```
export function resourceDownload(FilePath: string, FileName?: string) {
  let link = document.createElement('a')
  link.style.display = 'none'
  link.href = FilePath
  link.download = FileName || ''
  link.target = '_blank'
  document.body.appendChild(link)
  link.click()
  document.body.removeChild(link)
}
```
### 3. [ ].at(-1)报错，有的浏览器低版本没有这个方法
npm i -s array.prototype.at  
在main.js引入  
import * as at from 'array.prototype.at';  
at.shim()  
### 4. 
