let array=[]
for (let i=0; i<100; i++) {
    array.push(Math.floor(Math.random() * 50) + 1)
}
let oddArray=[]
let genapArray=[]
for (let j=0; j<array.length; j++){
    if(j%2===0)
    {
        genapArray.push(array[j])
    }
    else
    {
        oddArray.push(array[j])
    }
}

console.log("array:");
console.log(array);

console.log("odd array:");
console.log(oddArray);

console.log("genap array:");
console.log(genapArray);

let oddArrayMin = findMin(oddArray);
let oddArrayMax = findMax(oddArray);
let oddArrayTotal = getTotal(oddArray);
let oddArrayAverage = getAvg(oddArray);

let genapArrayMin = findMin(genapArray);
let genapArrayMax = findMax(genapArray);
let genapArrayTotal = getTotal(genapArray);
let genapArrayAverage = getAvg(genapArray);

console.log("odd")
console.log("Min:"+oddArrayMin + ",Max:" + oddArrayMax + ",Total:"+oddArrayTotal+",Average:"+oddArrayAverage)

console.log("genap")
console.log("Min:"+genapArrayMin + ",Max:" + genapArrayMax + ",Total:"+genapArrayTotal+",Average:"+genapArrayAverage)

if(oddArrayMin > genapArrayMin)
{
    console.log("Min lebih besar array ganjil");
}
else if(oddArrayMin < genapArrayMin){
    console.log("Min lebih besar array genap");
}
else{
    console.log("Nilai Min genap dan Min ganjil sama");
}

if(oddArrayMax > genapArrayMax)
{
    console.log("Max lebih besar array ganjil");
}
else if(oddArrayMax < genapArrayMax)
{
    console.log("Max lebih besar array genap");
}
else{
    console.log("Nilai Max genap dan Max ganjil sama");
}

if(oddArrayTotal > genapArrayTotal)
{
    console.log("total lebih be")
}

//saya tidak tahu apakah metode sort diperbolehkan, jika boleh pakai fastMin
/*function fastMin(array)
{
    array.sort((a,b)=>{
        return a-b
    })
    
    return array[0];
}*/

//sama juga untuk function tersebut
/*function fastMax(array)
{
    array.sort((a,b)=>{
        return a-b
    })
    
    return array[array.length-1];
}*/

function findMin(array)
{
    //return the first value if the value is 0, since 0 is the smallest possible value
    let min = array[0];
    if(min == 1)
    {
        return min;
    }
    //loop through the oddArray
    for(let i = 0 ; i < array.length-1;i++)
    {
        if(array[i] == 0)
        {
            return array[i];
        }
        
        if(min > array[i+1])
        {
            min = array[i+1];
        }
    }
    return min;
}

function findMax(array)
{
    let max = array[0];
    //return the first value if 50, since 50 is the largest possible value
    if(max == 50)
    {
        return max;
    }
    //loop through the oddArray
    for(let i = 0 ; i < array.length-1;i++)
    {
        if(array[i] == 0)
        {
            return array[i];
        }
        
        if(max < array[i+1])
        {
            max = array[i+1];
        }
    }
    return max;
}

function getTotal(array)
{
    let total = 0;
    for(let i = 0; i < array.length; i++)
    {
        total+=array[i];
    }
    return total;
}

function getAvg(array)
{
    return getTotal(array)/array.length;
}







