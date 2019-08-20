## LinkedList 


```Java
class Node {
    Node next; // 다음 요소의 주소를 저장
    Object obj; // 데이터를 저장
}
```

### 삭제    

LinkedList는 next로 다음 lnekedList 정보를 갖고 있다. 만약 삭제를 원한다면 
현재 LinkedList에서 next를 next LinkedList에서 next를 참조하게 만들면 된다.    
1Node  -> 2Node -> 3Node 처럼 연결된 list에서 1Node -> 3Node를 바라보게 하면 2Node는 삭제 된 것이다.




