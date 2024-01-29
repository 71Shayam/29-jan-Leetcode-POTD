class MyQueue {
public:
stack<int>s1,s2 ;
    MyQueue() {
        
    }
    
    void push(int x) {
        s1.push(x) ;
        
    }
    
    int pop() {
        int popele=-1 ;
        if(!s2.empty()){
            popele=s2.top() ;
        }
       else{
            while(!s1.empty()){
                s2.push(s1.top()) ;
                s1.pop() ;
           }
           popele=s2.top() ;
           
       }
       s2.pop() ;
       return popele;
    }
    
    int peek() {
        int frontele=-1 ;
        if(!s2.empty()){
            frontele=s2.top() ;
        }
        else{
            while(!s1.empty()){
                s2.push(s1.top()) ;
                s1.pop() ;
            }
            frontele=s2.top() ;
        }
        return frontele ;
    }
    
    bool empty() {
        return s1.empty() && s2.empty() ;
        
    }
};
