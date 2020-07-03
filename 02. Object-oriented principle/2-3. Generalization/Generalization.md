# **Generalization(일반화(상속) 관계)**

- **일반화 관계**는 객체지향 프로그래밍 관점에서는 **상속 관계**라고 합니다.  

- 일반화는 여러 개체들이 가진 공통된 특성을 부각시켜 **하나의 개념이나 법칙**으로 성립 시키는 과정이라 할 수 있습니다. 

위의 말이 어렵다면 아래의 예제를 보고 이해하실 수 있습니다. 

![일반화 관계](https://leetaehyun94.github.io/assets/Java/32.PNG)

위의 사진에서 바나나, 사과, 배, 오렌지의 공통된 특성이라 하면 대부분의 사람들은 **과일**이라 답할 것입니다.   

이렇게 **과일은** 바나나, 사과, 배, 오렌지가 가진 공통된 특성을 **일반화** 한 개념, 바나나, 사과, 배, 오렌지는 과일을 **특수화**한 개념이라 생각하면 쉬울 것입니다. 


다른 예제를 살펴보겠습니다. 

```java
가격 총합 = 0
while(내 주차장에 차가 있다){
    switch(차의 종류){
        case 벤츠:
            가격 총합 = 가격총합 + 벤츠 가격
        case BMW :
            가격 총합 = 가격총합 + BMW 가격
        //case 아우디:
        //  가격총합 =  가격총합 + BMW 가격
    }
}
```

위의 코드에서 주석을 지우고 만약 아우디 차량이나 다른 차량들을 추가해야하는 상황이 온다면 코드를 항상 수정해야 하므로 유연하지 못한 코드가 됩니다. 

따라서 우리는 아래와 같이 코드를 수정해야 합니다. 

```java
int addPrice(LinkedList<Car> car){

        int total = 0;
        Iterator<Car> itr = car.iterator();

        System.out.println(itr.hasNext());
        while (itr.hasNext()){
            Car curCar = itr.next();
            total = total + curCar.caculatePrice();
        }
        return total;
    }
```

여기서 addPrice는 차의 종류에 따라 다르게 실행됩니다.   
이는 **다형성**에 따른 것입니다. 

정리를 하자면 ,서브 클래스 캡슐화는 외부 클라이언트가 개별적인 클래스들과 무관하게 프로그래밍을 할 수 있게 합니다. 

