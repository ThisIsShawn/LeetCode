

#  Solution 1 Brute Force
This is the most time-intensive but intuitive solution. Traverse the whole array of the given size. For each element in an array, 
check if any of the two elements add up to the given number n. 
Use a nested for-loop for this purpose and iterate over the entire array for each element
Time Complexity O(n^2)

# Solution2 Use HashSet 
Sort array use quick sort then we keep a start pointer at 0 and end pointer at n -1,If the sum of the elements on these indexes of the array is smaller than given value n then increment index from the start else decrement index from the end, until the given value n is equal to the sum. Store the elements on these indexes in result array and return it.
Time Complexity O(nlogn)

# Solution3 Use HashSet , best solution 
THe Code works in O(n) as the whole array is iterated over once.
```
class Solution {
public int[] twoSum(int[] nums, int target) {
   Map <Integer,Integer> map = new HashMap<>();
    for(int i = 0;i< nums.length;i++){
        int complement = target  -nums[i];
        if(map.containsKey(complement)){
            return new int[]{map.get(complement),i};
        }
        map.put(nums[i],i);
        
    }
    throw new IllegalArgumentException("No two sum solution");
}
}
```
