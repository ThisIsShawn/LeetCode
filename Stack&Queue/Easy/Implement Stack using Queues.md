  # Solution: push:O(n) pop(), top(),empty(): O(1)  Run time:  0 ms,
  
  ```Java
  class MyStack {
    Queue<Integer> queue;
    /** Initialize your data structure here. */
    public MyStack() {
        queue = new LinkedList<>();
    }
    
    /** Push element x onto stack. */
    public void push(int x) {
        queue.add(x);
        for(int i = 0 ; i< queue.size() - 1; i++){
            queue.add(queue.remove());  
        }
        
    }
    
    /** Removes the element on top of the stack and returns that element. */
    public int pop() {
        return queue.remove();
    }
    
    /** Get the top element. */
    public int top() {
        return queue.peek();
        
    }
    
    /** Returns whether the stack is empty. */
    public boolean empty() {
        return queue.size() == 0;
        
    }
}

/**
 * Your MyStack object will be instantiated and called as such:
 * MyStack obj = new MyStack();
 * obj.push(x);
 * int param_2 = obj.pop();
 * int param_3 = obj.top();
 * boolean param_4 = obj.empty();
 */
  ```