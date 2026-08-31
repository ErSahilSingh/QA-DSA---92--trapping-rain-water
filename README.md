# QA-DSA---92--trapping-rain-water

var trap = function(arr) {

    let n = arr.length
    let maxL =[]
    maxL[0]= arr[0]
    let maxR = []
    maxR[n-1]= arr[n-1]

    for(let i =1 ; i<n ; i++){
        maxL[i]= Math.max(maxL[i-1], arr[i])
        maxR[n-1-i]=Math.max(arr[n-1-i], maxR[n-i])
    }

    let ans =0
    for(let i=0 ; i<n;i++){
        let watertap = (Math.min(maxR[i],maxL[i]))-arr[i]
        ans=ans+Math.max(watertap,0)

    }
    return ans
};
