# HR-max-subarray


```
static int maxSubarray(int[] arr) {
       
        BigInteger max_here = BigInteger.valueOf(arr[0]);
        BigInteger max_so_far = BigInteger.valueOf(arr[0]);
        
        
        
        for(int a : Arrays.copyOfRange(arr, 1, arr.length)){
            // max_here + a > a
            // max_here > a - a
            // max_here > 0
            max_here = max_here.compareTo(BigInteger.ZERO) > 0  ? max_here.add(BigInteger.valueOf(a)) : BigInteger.valueOf(a);
            
            max_so_far = max_here.compareTo(max_so_far) > 0 ? max_here : max_so_far;
            
           
        }
        
        return max_so_far.intValue();
    }
```
