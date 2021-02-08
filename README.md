# DSAproject

# Priority Queue

Queue is a data type which depends on FIFO order. Its time complexity is O(1). Priority Queue is an advance version of Queue in which elements are arranged by priority.
We can use list and can insert elements in O(N) time and can sort them to maintain a priority queue in O(N logN ) time. Efficient Approach: We can use heaps to implement the priority queue. It will take O(log N) time to insert and delete each element in the priority queue.

## Python Code For Priority Queue



```python
class heapTree:
    
    def __init__(self, queue):
        # it will take a queue from priority queue class
        self.queue = queue
    
    def __sortQueue(self):
        # use selection sort method
        for j in range(len(self.queue)):
            minVal = self.queue[j]
            a = j
            for i in range(j, len(self.queue)):
                if minVal < self.queue[i]:
                    minVal = self.queue[i]
                    a=i
            self.queue[j],self.queue[a] = minVal, self.queue[j]
        return self.queue
    
    def pushItem(self, item):
        # add item in the queue
        self.queue = self.queue + [item]
        # return the sort method which return the sorted queue
        return self.__sortQueue()
    
    def popItem(self):
        # pop item from queue
        self.queue = self.queue[:-1]
        # return sort method which return sorted queue
        return self.__sortQueue()

class priorityQueue:
    
    def __init__(self, queue = []):
        # compose class heapTree
        self.heap = heapTree(queue)

    def put(self, item):
        # return pushItem method
        return self.heap.pushItem(item)
    
    def delt(self):
        # return popItem method
        return self.heap.popItem()

    def printQueue(self):
        # print the queue
        print(self.heap.queue)

    def minItem(self):
        # find out minimum value of queue
        self.minVal = self.heap.queue[0]
        for i in range(len(self.heap.queue)):
            if self.minVal > self.heap.queue[i]:
                self.minVal = self.heap.queue[i]
        return self.minVal

    def maxItem(self):
        # find out maximum value of queue
        self.maxVal = self.heap.queue[0]
        for i in range(len(self.heap.queue)):
            if self.maxVal < self.heap.queue[i]:
                self.maxVal = self.heap.queue[i]
        return self.maxVal

# making class instance
a= priorityQueue()

print(a.put(4))
print(a.put(1))
print(a.put(10))
print(a.put(7))

print(a.delt())
a.printQueue()
print(a.minItem())
```
