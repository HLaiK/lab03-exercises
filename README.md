## Find All Duplicates
# Write a function (in python) or method (in Java) that accepts a list of integers and returns a list of only those integers that appear more than once.
**In Python**
def find_duplicates(nums):
    counts = {}
    duplicates = []

    for n in nums:
        counts[n] = counts.get(n, 0) + 1
    
    for n, count in counts.items():
        if count > 1:
            duplicates.append(n)
    
    return duplicates

## Describe Different Approaches to Solving This Problem
# Describe the two different ways to figure out all of the duplicate values of a list of integers in english. 
**The first solution is the nested loop solution.**
How a nest loop solution works is by starting at the first element in the list. Then compare that element to every element that comes after it in the list. If any element that is after the first element is equal to the current element, then you have found a duplicate value. Record that value in your output but only record it once. Then move on to the second element and repeat this until every element is complete. 

**The second solution is to use a dictionary or a map (similar to the containsPair method we wrote in class.)**
Using a dictionary or a map is like counting first then collecting that data. First create an empty map that will asociate each integer with a count. Then walk through the whole list once. For each value, look it up in the map and increase its count. After the first pass you have a map of value. Then make a second pass over the original list and collect every value whose value is greater than one. 

**Describe the trade-offs between the two solutions.**
The difference between the two is that the nested-loop is really simple but slow ( O(n^2) ) time. So the bigger the list the worst it gets. Dictionary/map is much faster ( O(n) ).Both barely use any extra memory but nested loops are easiest to understand while dictionary/maps take a little more to grasp. 
