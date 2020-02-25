###  选择排序
```
let sort=(numbers)=>{
 for(let i=0;i<numbers.length-1;i++){
   let index=minIndex(numbers.slice(i))+i
   if(index !== i){swap(numbers,index,i)}
 }
 return numbers
}
////////////////////////////////////////////
let minIndex=(numbers)=>{
 let index=0
 for(let i=1;i<numbers.length;i++){
  if(numbers[i]<numbers[index]){
   index=i
  }
 }
return index
}
///////////////////////////////////////////
let swap=(array,i,j)=>{
 let temp=array[i]
 array[i]=array[j]
 array[j]=temp 
}
```
### 快速排序
```
let quickSort=arr=>{
 if(arr.length<=1){return arr}
 let pivotIndex=Math.floor(arr.length/2)
 let pivot=arr.splice(pivotIndex,1)[0]
 let left=[]
 let right=[]
 for(let i=0;i<arr.length;i++){
  if(arr[i]<pivot){
   left.push(arr[i])
  }else{
    right.push(arr[i])
   }
 }
return quickSort(left).concat([pivot],quickSort(right))
}
```
### 归并排序
```
let mergeSort=arr=>{
 let k=arr.length
 if(k===1){return arr}
 let left=arr.slice(0,Math.floor(k/2))
 let right=arr.slice(Math.floor(k/2))
 return merge(mergeSort(left),mergeSort(right))
}
///////////////////////////////////////////////
let merge=(a,b)=>{
 if(a.length===0){return b}
 if(b.length===0){return a}
 return a[0]>b[0]?
    [b[0]].concat(merge(a,b.slice(1))):
    [a[0]].concat(merge(a.slice(1),b))
}
```
### 计数排序
```
let countSort=arr=>{
 let hashTable={}
 max=0
 result=[]
 for(let i=0;i<arr.length;i++){
  if(!(arr[i] in hashTable)){
   hashTable[arr[i]]=1
  }else{
    hashTable[arr[i]] +=1
  }
if(arr[i]>max){max=arr[i]}
 }
for(let j=0;j<=max;j++){
 if(j in hashTable){
   for(let i=0;i<hashTable[j];i++){
    result.push(j)
   }
  }
 }
return result
}
```
